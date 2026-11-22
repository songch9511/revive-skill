# Phase 2 — Verdict

The interview was exploratory and full of guesses. The verdict is the opposite. Assume the user does not know what they want; that is why the project is sitting abandoned. A verdict full of "it depends" hands the decision back to someone who has already failed to make it.

## The three options

Recommend exactly one.

- **Ship as it is.** The decisive cause is not about demand, and what stands between the project and a payment is small and known.
- **Shrink or pivot.** Something in the project is worth selling, but the scope is too big to finish or it is aimed at the wrong people. Name the smaller thing or the different customer.
- **Kill it.** Nobody can be named who would pay for it, or the user does not want to work on it and nothing found in the interview changes that.

These are guides for your judgment, not a formula. Decide from the facts in `state.md`. Two rules always apply:

- Many competitors is not evidence of demand for this product. Do not use it as a reason to continue.
- Working code is not a reason to continue. Sunk effort is the most common reason people keep a dead project half alive.

## Format

Write it in this order, in the user's language, and save it to `.revive/verdict.md`.

1. **Facts.** Only what was confirmed in the code, the history or the interview. Cite the evidence.
2. **Reasons.** What those facts mean: why this will work, or why it will not.
3. **What is worth keeping.** Reusable code (name the nodes from `architecture.md`), lessons, and assumptions that were actually tested.
4. **Recommendation.** One of the three options, with a one-line reason.

Then ask the user to choose among the three. They decide; you have already said what you would do.

## Style

- No hedging. Do not write "might", "maybe", "perhaps", "it could be that", "in some ways", "it depends", or their equivalents in the user's language.
- If you do not know something, say "not confirmed" and say what would confirm it. That is a fact about your evidence, not a hedge.
- If the project should be killed, say so in the first sentence of the recommendation and say why it will not work.
- Do not soften a kill verdict with praise for the effort. Put what is worth keeping in section 3, where it is useful.
- Keep it short. A verdict the user has to dig through is another way of not deciding.

### Example

```markdown
## Facts
- Last commit 2026-03-12 on `payments`; the webhook handler throws on every request (`app/api/webhook/route.ts`).
- No landing page. No deployment. The app has never been shown to anyone outside your team (interview).
- You could not name one person who has this problem (interview, question 4).

## Reasons
The webhook is a two-hour fix. It is not why this stopped. It stopped because there is no one to sell it to, and finishing payments would not change that.

## What is worth keeping
- The report generator (`lib/report/`) works and has no dependency on the rest of the app.
- You learned that you can build a full auth and billing skeleton in a weekend.

## Recommendation
Kill it. There is no customer, and eight months have not produced one.
```

## After the choice

Record the choice and the date in `state.md` and in `verdict.md`.

- **Ship as it is**, or **shrink or pivot:** go to Phase 3. For a pivot, write the new target in one sentence before leaving this phase.
- **Kill it:** write `.revive/retro.md` and end.
- **The user chooses against your recommendation:** that is their right. Record both the recommendation and the choice, and go on with their choice without arguing it again.

## Gate

The user's choice is recorded in `state.md`.
