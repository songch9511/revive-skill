# Phase 4 — Execution loop

Work through the milestones from Phase 3, one task at a time.

```
pick task → route to a skill → execute → verify yourself → update state
```

## Contents

- [Pick the task](#pick-the-task)
- [Route to a skill](#route-to-a-skill)
- [Execute](#execute)
- [Verify](#verify)
- [Update state](#update-state)
- [Build and dependency recovery](#build-and-dependency-recovery)
- [Debugging](#debugging)

## Pick the task

Break the current milestone into tasks small enough to verify in one step. Take the next one that is not waiting on someone else.

- If recon recorded a failed build, recovery is the first task of the first milestone.
- If a task is waiting on an outside approval (a payment account review, for example), record the reason and start date in `state.md` and pick another task. Waiting is not a stall.
- If a task turns out not to be needed for the first payment, move it to the cut list instead of doing it.

## Route to a skill

Revive is the only process in charge. Skills are parts it calls for one task.

### Order

For the task's slot, use everything that applies, in this order. Do not skip ahead.

1. If Revive has its own procedure for the slot, run it first.
2. If a skill bundled with Revive covers the slot, use it.
3. If an optional skill for the slot is installed, use it. If it is not installed, offer it.
   - When you offer, tell the user what comes with it: hooks, network requests, extra cost.
   - If the user declines, record it in `state.md` and do not offer that skill again.
   - Never install anything without a yes.
4. If steps 2 and 3 produce no skill, read the official documentation and implement without one.

A skill counts as available only if it appears in the session's skill list. It may be listed with a plugin prefix; match on the skill's own name and prefer the copy that ships with Revive. If a bundled skill is missing from the list, carry on down the order: step 3, then step 4.

You do the detecting and the offering. The execution layer only receives the name of the skill to use.

### Slots

| Slot | Revive's own part | Bundled with Revive | Optional (offer only) |
|---|---|---|---|
| Build and dependency recovery | Procedure below | — | — |
| Design (UI/UX) | Write a brief, collect references | `frontend-design` | `impeccable` (`pbakaus/impeccable`), for its `critique` command on the result |
| Getting unstuck (debugging) | Procedure below | — | — |
| Payment integration | Payment rules in `payment-path.md` | — | Stripe's official skills (`stripe/ai`), Polar's `setup-polar` (`polarsource/agent-toolkit`) |
| Deployment | Make sure only one deploy platform is enabled for the repo | — | `deploy-to-vercel` (`vercel-labs/agent-skills`); then `cloudflare/skills`; then Railway or Netlify |
| Landing page, copy, launch posts | Customer quotes and voice profile from `state.md` | `copywriting`, `pricing`, `offers`, `prospecting`, `launch` | `humanizer` (`blader/humanizer`) |
| Pre-launch checks | `prelaunch-checks.md` | — | Anthropic's `security-guidance` plugin; the built-in `/security-review` command is called, never installed |

Demand checks and the diagnostic interview are never routed. They are Revive's own (Phases 3 and 1).

### Notes per slot

- **Design.** Write the brief before calling any design skill: who the customer is, what the one action on the page is, and two or three reference sites the user likes. `impeccable` comes with three hooks and downloads a native binary, and one user reported it using 1.6 to 5 times the tokens. Say so when you offer it.
- **Payment.** Stripe's full plugin includes a usage-reporting hook. Offer the skill folder only, not the whole plugin. A skill can name an API version that has since moved on, so check the provider's current documentation for the version before implementing.
- **Deployment.**
  - Enable one deploy platform per repo. Several at once add competing skills and hooks.
  - Cloudflare Workers does not run an ordinary Node server. Check the project type before offering it.
  - Railway's plugin includes a hook that auto-approves shell commands. Say so when you offer it, and offer the skill folder without the hook.
- **Landing page and copy.**
  - The raw material is what the first customers actually said. Pass the customer quotes from `state.md` to the copy skill.
  - Use `prospecting` only for finding demand signals.
  - Build a voice profile only if the user has English writing of their own to base it on. If not, skip it. A general humanizer comes after that, not before.
  - Everything a customer sees is written in English.
- **Pre-launch checks.** `security-guidance` needs Python 3.8 or later and makes an LLM call on every turn. Say so when you offer it.

Record which skill was used for which task in `log.md`.

## Execute

### With the execution layer on

Hand the task to a subagent on the model one tier below yours, with a brief like this:

```
Task: <one sentence>
Finish condition: <what must be true, and how it will be checked>
Scope: <files or area it may change> — do not change anything else
Out of scope: <the relevant items from the cut list>
Skill to use: <skill name, or "none — follow the official docs at <url>">
Context: <the nodes from .revive/architecture.md that matter, with file paths>
Report back: what changed, what you ran to check it, and anything left undone
```

- The finish condition and scope go first because a skill may push for more. Revive's gate and minimum scope win over a skill's own rules.
- The subagent does not talk to the user. If it needs a decision, it reports back and you ask.
- If the subagent reports that it cannot load the named skill, run that task yourself with the skill instead.

### With the execution layer off

Do the task yourself with the same routing and the same finish condition.

### Things only the user does

Prepare these and hand them over: opening a payment account, identity checks, connecting a payout account, buying a domain, posting anything publicly, installing plugins. Tell the user exactly what to do and what to bring back.

## Verify

Check the result yourself before marking a task done.

- Build it and run it.
- For a deployment, open the URL.
- For payments, make a test-mode payment end to end, including the webhook.
- For a UI change, look at it at a 360px mobile width as well as desktop.

A subagent's report is a claim. If you could not verify something, record it as not verified. Do not mark it done.

## Update state

After every task:

- update milestone progress, the last progress date and the next task in `state.md`
- add a line to `log.md` with the task and the skill used
- if the task added or removed a module or an external service, update `architecture.md`

Keep `unfinished_streak` in `state.md` current. It counts how many sessions in a row ended with the current task unfinished.

- When a task is verified and done, set it to 0.
- When a session ends with the current task unfinished, add 1. Do not count a task that is waiting on an outside approval.
- At 2, it is a re-stall. Go to Phase 5's re-stall step.

## Build and dependency recovery

Use this when recon recorded that the project does not build or run. Old projects usually fail because the toolchain moved, not because the code is wrong.

1. Start from the failure recorded in recon: the command and the error message.
2. Match the runtime and package manager versions to what the project used when it stopped (lockfile, version files, engine fields).
3. If it still fails, upgrade only the dependency named in the error. Do not upgrade everything at once; that turns one error into twenty.
4. Stop when it builds and runs. Do not make improvements that recovery does not need.

## Debugging

Revive uses its own short procedure and bundles no debugging skill.

1. Find the break on the core flow in `.revive/architecture.md` and read the files on that node.
2. Reproduce the problem.
3. Confirm the cause. Do not fix on a guess.
4. Make the smallest change that fixes it.
5. Verify independently: you check it, not the session that made the fix.

If you cannot confirm the cause after three attempts on the same problem, stop and tell the user what you tried. Technical walls are one of the reasons these projects died the first time, so decide with the user instead of digging on:

- If the first payment does not need the feature, move it to the cut list and adjust the milestone.
- If the feature is the product, set the execution layer to off and return to Phase 2 for a new verdict.
