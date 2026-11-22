# Phase 1 — Diagnostic interview

> Adapted from the `interview-me` skill by Addy Osmani ([addyosmani/agent-skills](https://github.com/addyosmani/agent-skills), MIT License). The original extracts what a user wants before any work starts. This version is narrowed to one question: why did this project stop?

The goal is the **decisive cause**: the one or two reasons that, if removed, would have let the project ship. People give several reasons for abandoning a project and most of them are excuses, true but not decisive. Fixing an excuse changes nothing, which is why this phase exists before any fixing.

## Cause categories

A project can have more than one.

- **Lost belief in demand.** Stopped being sure anyone would pay.
- **Technical wall.** Hit something they could not build or fix.
- **Unhappy with the UI/UX.** It worked but looked or felt wrong, and they would not show it.
- **Motivation or priority.** Something else took over, or the energy ran out.
- **Other.** Name it specifically.

## How to run it

### 1. State a hypothesis with a confidence number

Before the first question, write one sentence on why you think the project stopped, based only on recon, and an honest confidence from 0 to 100%.

```
HYPOTHESIS: You stopped when the Stripe webhook would not verify, and never came back.
CONFIDENCE: ~40% — the last branch is payments work, but I can't tell if that was the reason or just the last thing you touched.
```

Below about 70%, say what is missing on the same line. It tells the user what the interview needs to find.

### 2. One question at a time, each with a guess

```
Q: The last commit is on March 12, on a branch called `payments`, and nothing after. Is that where you got stuck?
GUESS: Yes — the webhook handler is half written and throws on every request.
CONFIDENCE: ~55%
```

Give the confidence in your overall hypothesis with every question, so the user can see whether the interview is getting anywhere.

- Ask one question per message and wait. The next question usually depends on the answer.
- Ground every question in a recon fact or a node in `architecture.md`. "Why did you stop?" gets a rehearsed story; a dated commit gets a memory.
- Attach your guess. Reacting to a wrong guess is faster than answering from scratch, and it keeps your own assumptions visible.
- Be visibly willing to be wrong. Some users agree with any guess to be polite, so now and then guess in a direction you expect them to reject.

### 3. Separate the decisive cause from the excuses

For each cause the user names, ask the test question:

> "If that were solved today, would you launch tomorrow?"

- **Yes** means it is a candidate for the decisive cause.
- **No**, or "well, I'd also need to…", means it is not decisive. Ask what else is in the way, and test that.

Watch for answers that sound like what a sensible founder should say rather than what happened: "I wanted to make it more scalable first", "the architecture wasn't clean", "I needed to do more research". When you hear one, ask:

> "If you didn't have to justify it to anyone, what actually made you stop opening this project?"

Demand doubt and loss of motivation often hide behind a technical story, because a technical problem feels more respectable.

### 4. Restate and confirm

When you can predict how the user would answer your next three questions, stop asking and write it back:

```
Here's what I think happened:

- Decisive cause:  <one line>
- Second cause:    <one line, or "none">
- Excuses:         <things that were true but would not have stopped you>
- Where it stopped: <the node or file from architecture.md>

Is that right?
```

Only an explicit yes counts. "Sounds about right" or "sure" is not confirmation; ask what they would change. If they correct you, fold it in and restate.

## When confidence will not rise

If you have asked about eight questions and still cannot predict the user's answers, do not keep going. Past that point more questions rarely help, and the user's patience is part of what keeps the project alive. Say so: "I've asked N questions and I still can't tell what stopped this. That itself tells me something." Record it as a fact and carry it into the verdict. An owner who cannot say why they stopped is a finding.

## Re-diagnosis after a re-stall

When Phase 5 sends you back here, keep it short. Start from the previous diagnosis in `state.md` and ask what was different this time. Three or four questions is normal. The usual result is that the first decisive cause was an excuse and the real one is still there.

- If the decisive causes are unchanged, record that and return to Phase 4.
- If they changed, set the execution layer to off in `state.md` and go to Phase 2 for a new verdict.

## Record

Write to `state.md`: the decisive causes, the excuses, and the place the project stopped. Add a line to `log.md`.

## Gate

The user has explicitly agreed to one or two decisive causes, or you have recorded that confidence did not rise. On a first diagnosis, move to Phase 2. On a re-diagnosis, follow the two cases above.
