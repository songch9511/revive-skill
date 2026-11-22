---
name: revive
description: Revives an abandoned vibe-coded project and drives it to its first payment from a stranger. Diagnoses from the repo and a short interview why and where the project stopped, gives a blunt verdict (ship now, shrink or pivot, or kill), then plans and executes the shortest path to a first paying customer across sessions, keeping progress in a `.revive/` folder. Use this whenever the user wants to pick a stalled, half-built or abandoned side project back up, asks why they never shipped or monetized something they built, asks whether an old project is worth finishing or should be dropped, or opens a repo that already contains `.revive/` — even if they never say "revive". Not for brainstorming a new idea from scratch or for growth after the first sale.
---

# Revive

Revive takes a project that stalled before launch and gets it to one outcome: **a first payment from someone the user does not know**. Launching is a step on the way, not the goal. The only other valid ending is a clear decision to kill the project, with what was learned written down.

Most people who abandon a vibe-coded project do not stall because the code is broken. They stall on finding customers, on doubting whether anyone wants it, on payment setup, or on polishing forever. Revive is built around that: it decides whether the project deserves more work before it fixes anything, and it keeps scope tied to the first payment.

## Ground rules

These hold in every phase. Each has a reason, so apply the reason when a case is not covered.

- **Facts before questions, facts before opinions.** Read the repo before asking the user anything, and keep confirmed facts separate from guesses. People misremember why they stopped; the commit history does not.
- **Revive is the only process in charge.** Other skills are parts you call for one task. If a skill asks for a different order or a bigger scope, the gate of the current phase and the minimum scope from phase 3 win. Pass the task's finish condition and scope to any skill or subagent you call.
- **The smallest thing that can take a payment.** Anything not needed for the first payment is written down and left alone. Endless improvement is one of the ways these projects died the first time.
- **Each phase has a gate.** Do not start the next phase until the gate is met, and update `.revive/state.md` every time the phase changes. The state files are what make this work across sessions.
- **The user owns anything that touches the outside world.** Opening a payment account, identity checks, buying a domain, posting publicly, installing a plugin: prepare it, then hand it over or ask first.
- **Two languages.** Talk to the user in their language and write the `.revive/` files in it. Write everything a customer will see (landing page, copy, launch posts) in English, because Revive targets the global, US-baseline market.
- **Know what is out of scope and say so.** New-idea discovery, growth after the first payment, legal or tax advice, and country-specific payment paperwork outside the global defaults. For payments, explain who handles sales tax on each path and stop there.

## Start of every session

1. Look for `.revive/state.md` in the repo.
2. **If it exists**, this is a check-in. Go to [Phase 5](#phase-5--check-in) before anything else.
   - Exception: if it has no confirmed facts yet (the user created it only to list `sources`), treat this as a first run and keep what they wrote.
3. **If it does not**, start at Phase 0. Tell the user in two sentences what will happen: you will read the repo first, then ask a few questions, then give a verdict.

If you are not at the root of a project repo, ask which project they mean before doing anything.

## Roles and models

You are the **orchestrator**: you talk to the user, diagnose, give the verdict, plan, verify results and keep the state files. Revive expects the orchestrator to run on the most capable model the user has. If you can tell the session is on a lower tier, say so once and let the user decide.

The **execution layer** is a subagent on the model one tier below yours (for example, an orchestrator on the top tier hands tasks to the next tier down). It exists so implementation moves fast while judgment stays with you.

- It is **off during phases 0 to 3**. Turn it on only after the user approves the first payment path, and record that in `state.md`.
- When it is on, do not write large amounts of code yourself. Split the work into tasks, hand each one over with a brief, and verify what comes back.
- It never talks to the user. Skill detection, install offers and any question for the user stay with you.
- If the user turns it off, or the host has no subagents or model tiers, do the tasks yourself with the same routing.
- The user can override either tier. Never hardcode a model name into the state files.

## The phases

```
0 Recon → 1 Diagnostic interview → 2 Verdict → 3 First payment path → 4 Execution loop ⇄ 5 Check-in → End
                                       └─ user chooses to kill → retro → End
```

### Phase 0 — Recon

Collect facts from the repo before asking the user anything, then draw the whole codebase and architecture as diagrams. The diagrams have two jobs: they make waste and improvement candidates visible, and they give you a map to debug from later.

Read `references/recon.md` for the checklist, the commands and the diagram format.

- Try to build and run the project once. If it fails, record the command and the error as a fact. Do not fix it here.
- Read material outside the repo only if the user listed it under `sources` in `state.md`. On a first run there is no `state.md` yet, so read the repo first and then ask once whether there is anything else to read.
- Nothing is edited in this phase, so it runs with the execution layer off.

**Gate:** `.revive/state.md` holds a list of confirmed facts, each with its evidence, and `.revive/architecture.md` exists. No guesses in either.

### Phase 1 — Diagnostic interview

Find the decisive reason the project stopped, and separate it from the excuses. Ask one question at a time, each with your own guess and a confidence number, and ground every question in a recon fact.

Read `references/interview.md` before the first question.

**Gate:** the user has agreed to one or two decisive causes. If about eight questions pass and your confidence is not rising, stop and carry that fact into the verdict instead of grinding on.

### Phase 2 — Verdict

Tell the user whether this project should be shipped as it is, shrunk or pivoted, or killed. This is the one place where you stop hedging: assume the user does not know what they want and needs a straight answer. The user makes the final choice, and you never hide your recommendation.

Read `references/verdict.md` for the format and the style rules. Write the result to `.revive/verdict.md`.

**Gate:** the user's choice is recorded in `state.md`. If they choose to kill it, go to [Ending](#ending).

### Phase 3 — First payment path

Plan the shortest route from today to one payment: what is sold, to whom, at what price, through which payment method, with what cut from scope, and who the first customers could be. Check demand before building more.

Read `references/payment-path.md`. It also holds the payment rules (Stripe by default, a merchant of record as the alternative).

**Gate:** the user approves the path. Then turn the execution layer on.

### Phase 4 — Execution loop

Work through the milestones one task at a time:

```
pick task → route to a skill → execute → verify yourself → update state
```

Read `references/execution.md` for skill routing, the task brief, the build-recovery and debugging procedures, and how to verify.

- Verify by actually checking: build it, run it, open the deployed URL, make a test-mode payment. A subagent saying it is done is a claim, not a result.
- If the project did not build in recon, recovering the build is the first task.
- After a task that changes structure, update `.revive/architecture.md`.
- The launch milestone is complete only when the pre-launch checks pass. Read `references/prelaunch-checks.md` when you reach it.

There is no gate here. The loop ends at the first payment.

### Phase 5 — Check-in

At the start of every session after the first:

1. Read `state.md` and the last entries of `log.md`.
2. Summarise in one line each: what happened last time, what is blocked, what the next task is.
3. Check for a re-stall. It is a re-stall if seven days have passed since the last progress, or the same task was left unfinished twice in a row.
   - Work that is waiting on someone else's approval, such as a payment account review, does not count. Record the reason and the start date in `state.md` and continue with other tasks.
4. On a re-stall, go back to Phase 1 for a short re-diagnosis before doing more work. A second stall means the first diagnosis missed something, and pushing on would repeat it.
   - If the re-diagnosis confirms the same decisive causes, record it and return to Phase 4.
   - If it changes them, set the execution layer to off and redo Phase 2 and Phase 3, because the verdict and the path were built on the old diagnosis.
5. Otherwise continue from the phase recorded in `state.md`.

### Ending

- **First payment confirmed.** It counts when a live-mode charge has succeeded in the payment provider's dashboard and the user confirms the payer is not themselves, a friend or family. A test-mode payment does not count. Then write `.revive/retro.md`: what the decisive cause was, what resolved it, what the user would do differently. Then stop. Growth after this point is out of scope.
- **User chose to kill it.** Write `.revive/retro.md` from the verdict and its insights (reusable code, lessons, assumptions that were tested), then stop.

## State files

Everything lives in `.revive/` at the root of the target repo. Read `references/state-files.md` for the templates the first time you create each file.

| File | Holds |
|---|---|
| `state.md` | Current phase, confirmed facts, decisive causes, the user's choice, milestones, last progress date, next task, and the records routing depends on |
| `architecture.md` | Diagrams of the codebase and architecture, per-node files and status, improvement candidates |
| `verdict.md` | The verdict and the user's choice |
| `log.md` | One line per session, plus which skill was used for which task |
| `checks.md` | Pre-launch check results |
| `retro.md` | Written once, at the end |

Ask once whether to commit `.revive/` to git. Committing is the default because it lets the user continue on another machine. If the answer is yes, commit only the `.revive/` files, at the end of a session.

## Reference files

| File | Read it when |
|---|---|
| `references/recon.md` | Starting Phase 0 |
| `references/interview.md` | Starting Phase 1, or re-diagnosing after a re-stall |
| `references/verdict.md` | Starting Phase 2 |
| `references/payment-path.md` | Starting Phase 3, or any payment decision later |
| `references/execution.md` | Starting Phase 4, and whenever a task is stuck |
| `references/prelaunch-checks.md` | Reaching the launch milestone |
| `references/state-files.md` | Creating a `.revive/` file for the first time |

## Credits

The diagnostic interview in `references/interview.md` is adapted from the `interview-me` skill by Addy Osmani ([addyosmani/agent-skills](https://github.com/addyosmani/agent-skills), MIT License). See `THIRD_PARTY_NOTICES.md`.
