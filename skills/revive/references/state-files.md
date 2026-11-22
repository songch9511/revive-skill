# State files

All files live in `.revive/` at the root of the target repo. They are how a later session, possibly on another machine, knows where things stand. Write them in the user's language; keep customer quotes exactly as they were said.

Fields a later session needs to read mechanically go in the frontmatter of `state.md`. Everything else is plain Markdown that the user can read and edit.

Ask once whether `.revive/` should be committed to git. The default is yes.

## `state.md`

```markdown
---
phase: 0                      # 0–4, or "ended". Phase 5 is the check-in at session start and is never stored
choice: null                  # ship | shrink-or-pivot | kill
execution_layer: "off"        # "off" | "on" (quoted so YAML does not read it as a boolean)
last_progress: <today>        # date of the last completed task; set to today's date when the file is created
next_task: null
unfinished_streak: 0          # sessions in a row that ended with the current task unfinished (see execution.md)
payment_path: null            # stripe | merchant-of-record:<provider> | other:<name>
waiting_on: []                # e.g. [{what: "Stripe account review", since: 2026-01-20}]
sources: []                   # material outside the repo the user allowed Revive to read
---

# Revive state

## Confirmed facts
<!-- One fact per line, each with its evidence: file path, commit hash or command output. No guesses. -->

## Decisive causes
<!-- One or two, agreed by the user in Phase 1. -->

## Excuses
<!-- True, but would not have stopped the project. -->

## Choice
<!-- The user's choice from Phase 2 and its date. Note it if it differs from the recommendation. -->

## First payment path
- What is sold:
- Customer:
- Price:
- Payment method:
- Minimum scope:
- Cut list:
- First customer candidates:

## Milestones
<!-- 3–5. Each: name, finish condition, target date, status. -->

## Customer quotes
<!-- Word for word, with who said it and when. -->

## Voice profile
<!-- Only if the user has their own English writing to base it on. -->

## Payment
<!-- Can the user open a Stripe account? Chosen path. Application date, approval date, first payout date. -->

## Declined installs
<!-- Skills the user said no to. Do not offer these again. -->
```

## `architecture.md`

```markdown
# Architecture

Last updated: <date>

## System overview
<!-- Mermaid diagram -->

## Code structure
<!-- Mermaid diagram -->

## Core flow
<!-- Mermaid diagram: visit → sign up → core feature → payment, with the break marked -->

## Nodes
| Node | Files | Status | Evidence |
|---|---|---|---|

## Improvement candidates
| Candidate | Files | Evidence | Needed for first payment? |
|---|---|---|---|
```

Status is one of `WORKING`, `PARTIAL`, `BROKEN`, `UNUSED`.

## `verdict.md`

```markdown
# Verdict — <date>

## Facts
## Reasons
## What is worth keeping
## Recommendation
<!-- One of: ship as it is / shrink or pivot / kill it. One-line reason. -->

## Choice
<!-- What the user chose, and the date. -->
```

## `log.md`

One line per session, newest last. Add a line per task for the skill used.

```markdown
# Log

- 2026-01-15 — Recon and interview. Decisive cause: no customer in mind. Blocked: nothing.
- 2026-01-16 — Task: payment link. Skill: none (official docs). Result: verified in test mode.
```

## `checks.md`

```markdown
# Pre-launch checks

| # | Check | Result | Date | Checked by | Notes |
|---|---|---|---|---|---|
| 1 | No secrets in client bundle | pass / fail / not run | | command | |
| 2 | No secrets in commit history | | | command | |
| 3 | Protected routes reject requests without a session | | | command | |
| 4 | One user cannot read another user's data | | | command | |
| 5 | Supabase: service-role key and RLS | | | command | |
| 6 | Spend caps set | | | user | |
| 7 | Paid routes require sign-in and are rate limited | | | user | |

## Other checks
- Independent reviewer:
- /security-review:
- Screen regression (360px, tab order):
- Policy pages (Terms, Privacy, Refund):
```

## `retro.md`

Written once, at the end.

```markdown
# Retro — <date>

## Outcome
<!-- First payment on <date>, or killed on <date>. -->

## What actually stopped it
## What resolved it
<!-- Or, for a killed project: why it would not have worked. -->

## What is worth keeping
<!-- Reusable code, lessons, assumptions that were tested. -->

## What I would do differently
```
