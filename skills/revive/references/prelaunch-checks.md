# Pre-launch checks

The launch milestone is complete only when every check below has passed. Record each result in `.revive/checks.md` (template in `state-files.md`).

These are the checks builders actually run before launching, turned into steps. For the first five, the result comes from a command's output, not from your reading of the code. A model reviewing code tends to report "looks fine" on exactly the code that later turns out not to be.

Each check ends in one of these results:

- **pass**
- **fail** — fix it, then run the check again
- **not run** — say why. "Not run" is not a pass. It blocks the milestone until the user explicitly accepts it, and the acceptance is recorded.
- **not applicable** — only where a check says so.

A command that could not run is "not run", never "pass". An empty output only counts when the command had something to look at, so do the precondition step of each check first.

Run the checks against a local or preview deployment of the user's own app, with test accounts and test data.

## Checks decided by command output

### 1. No secrets in the client bundle

**Precondition.** Build the project and set `BUNDLE_DIR` to the client-side output: the files a browser downloads (for example `.next/static`, `dist`, `build`), not the server output. Confirm it exists and is not empty:

```bash
[ -d "$BUNDLE_DIR" ] && [ -n "$(ls -A "$BUNDLE_DIR")" ] && echo ready || echo "not run"
```

**a. Known key formats.**

```bash
grep -rEl 'sk_live_|sk_test_|rk_live_|whsec_|sb_secret_|sk-ant-|sk-proj-|ghp_[A-Za-z0-9]{20,}|xox[baprs]-|AKIA[0-9A-Z]{16}|-----BEGIN [A-Z ]*PRIVATE KEY-----' "$BUNDLE_DIR"
```

**b. Private env values.** This compares the values of secret-looking variables in every env file of the repo against the bundle. It prints file names only, never the values.

```bash
find . -name '.env*' -type f -not -path '*/node_modules/*' -not -path '*/.git/*' -print0 \
  | xargs -0 grep -hE '^[[:space:]]*(export[[:space:]]+)?[A-Za-z0-9_]*(KEY|SECRET|TOKEN|PASSWORD|PRIVATE|DATABASE_URL)[A-Za-z0-9_]*=' \
  | grep -vE '^[[:space:]]*(export[[:space:]]+)?(NEXT_PUBLIC_|VITE_|PUBLIC_|EXPO_PUBLIC_)' \
  | tr -d '\r' \
  | sed -E "s/^[^=]+=//; s/[[:space:]]+#.*$//; s/^[\"']//; s/[\"']$//" \
  | awk 'length($0) >= 12' | sort -u \
  | while IFS= read -r v; do grep -rlF -- "$v" "$BUNDLE_DIR"; done
```

Variables with a public prefix are skipped because they are meant to be in the bundle. If the project names its secrets differently, add those names to the pattern. If the repo has no env file, this part is "not run"; say so.

**c. Service-role tokens.** A Supabase service-role key in the older format is a JWT and matches none of the patterns in (a), so decode every JWT in the bundle and look at its role:

```bash
grep -rEoh 'eyJ[A-Za-z0-9_-]{10,}\.eyJ[A-Za-z0-9_-]{10,}' "$BUNDLE_DIR" | sort -u | while IFS= read -r t; do
  p=$(printf '%s' "${t#*.}" | tr '_-' '/+'); while [ $(( ${#p} % 4 )) -ne 0 ]; do p="$p="; done
  printf '%s' "$p" | base64 -d 2>/dev/null | grep -q '"role":[[:space:]]*"service_role"' && echo "FAIL: service-role JWT in bundle"
done
```

Any file name printed by (a) or (b), or a FAIL line from (c), is a fail.

### 2. No secrets in the commit history

Run a secret scanner over the whole history, not just the current files. With gitleaks, that is `gitleaks git --redact` on current versions and `gitleaks detect --redact` on older ones (check `gitleaks --help`). TruffleHog is an alternative.

- Any finding is a fail. A key that was ever committed is rotated, even if a later commit removed it. Rotation is done by the user in the provider's dashboard.
- If no scanner is installed, ask before installing one. If the user declines, the result is "not run".

### 3. Protected routes reject requests without a session

**Precondition.** Set `BASE_URL` to the running local or preview deployment and confirm it answers. List every API route from `architecture.md` with the HTTP methods it accepts, and mark which ones should require a signed-in user.

For each protected route, and for each method it accepts, send a request with no cookies and no auth header:

```bash
curl -s -o /dev/null -w '%{http_code}\n' -X POST "$BASE_URL/api/<route>"
```

- A 2xx response is a fail.
- A 401 or 403 is a pass for that method.
- A 404 or 405 means you did not reach the handler. Fix the path or the method and try again; it is not a pass.

This covers API routes. Server-rendered pages and server actions that read private data are not reached by it: list them from `architecture.md` and request each one without a session as well.

### 4. One user cannot read another user's data

1. Create two test accounts, A and B, through the app's own sign-up.
2. As B, create one record and note its ID.
3. Sign in as A and capture A's session (the cookie or bearer token the app issues).
4. With A's session, request B's record by ID, on every route that takes a record ID or a user ID:

```bash
curl -s -w '\n%{http_code}\n' -H "Cookie: $A_SESSION" "$BASE_URL/api/<route>/$B_RECORD_ID"
```

A 2xx response that contains B's data is a fail. A 403 or 404 is a pass for that route. Repeat for write methods: A must not be able to change or delete B's record.

If the app has no accounts or no per-user data, record "not applicable" and why.

### 5. Supabase projects only

Record "not applicable" if the project does not use Supabase.

- **Service-role key.** Check 1 (b) and (c) cover the key's value. Also search the client-side source for the variable that holds it; a client file that references it is a fail.
- **Row level security.** Run these against the project's database. Use a database tool you already have for this project, or ask the user to run them in the Supabase SQL editor and paste the output. If neither is possible, the result is "not run".

```sql
select tablename, rowsecurity from pg_tables where schemaname = 'public';
select tablename, policyname, cmd, qual from pg_policies where schemaname = 'public';
```

A table with `rowsecurity = false` is a fail unless the user confirms it holds only public data. A policy whose `qual` is `true` lets everyone through; on a table with private data that is a fail too.

## Checks confirmed by the user

You cannot see these from the repo. Ask, and record what the user answers and when.

### 6. Spend caps

Every paid API provider the app calls has a spending limit set in its dashboard.

### 7. Paid routes are limited

Every route that calls a paid API requires a signed-in user and has a per-user rate limit. Check what you can in the code first, then ask the user to confirm the rest.

## Other checks

- **Independent reviewer.** Have a fresh, read-only subagent review the whole change set since Revive started. It should not be a session that wrote any of the code.
- **`/security-review`.** Use it as a floor, not as the gate. It only looks at uncommitted changes, so it sees nothing in the code the project already had. Run it on new work before committing, and for a large change run it area by area (auth, input handling, database).
- **Screen regression.** Before and after a design change, record the 360px mobile layout and the keyboard tab order, and compare.
- **Policy pages.** Check that Terms, Privacy Policy and Refund Policy pages exist. Payment providers may look at them when reviewing an account. Do not review their legal content; that is out of scope.

## Gate

Checks 1 to 5 are pass or not applicable, checks 6 and 7 are confirmed by the user, and the other checks are recorded. Then the launch milestone can be marked complete.
