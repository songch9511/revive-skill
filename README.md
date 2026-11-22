<div align="center">

# Revive

**Pick your abandoned project back up and take it to its first paying customer.**

An agent skill for projects you vibe-coded, meant to launch, and quietly stopped opening. Revive reads the repo, works out with you why it really stopped, tells you plainly whether to ship it, shrink it or kill it, and then works with you until a stranger pays for it.

[Is this for you?](#is-this-for-you) | [Install](#install) | [Quick start](#quick-start) | [How it works](#how-it-works)

</div>

## Is this for you?

Revive is for you if:

- you built something with an AI coding agent and it never launched
- it launched in your head, but nobody has ever paid for it
- you are not sure whether it is worth finishing, and you would like a straight answer

Most of these projects did not stall because the code broke. They stalled on finding customers, on doubting that anyone wants it, on payment setup, or on polishing forever. So Revive does not start by fixing things. It starts by deciding whether the project deserves more work.

Revive is not for coming up with a new idea from scratch, and it stops at the first payment. Growth after that is a different job.

## Install

With the [skills CLI](https://github.com/vercel-labs/skills):

```text
npx skills add songch9511/revive-skill
```

Or by hand: clone this repo and copy the `skills/revive` folder to where your agent keeps skills.

```text
Claude Code:  ~/.claude/skills/revive
```

Everything in the skill is plain Markdown. It works best with:

- **git history** in the project you want to revive. Revive reads it to find where the work stopped.
- **an agent that can run subagents** on a cheaper model. Revive uses them to implement tasks while the main session keeps the judgment. Without them it does the work itself.
- **a secret scanner** such as gitleaks, for one of the pre-launch checks. Revive asks before installing anything.

## Quick start

Open your agent in the root of the stalled project and run:

```text
/revive
```

Or just say what happened:

```text
I built this last spring and never launched it. Is it worth finishing?
```

What happens next:

1. Revive reads the repo before asking you anything, and draws the architecture so both of you can see what exists and what is broken.
2. It asks you questions one at a time, each with its own guess, until you agree on the real reason the project stopped.
3. It gives you a verdict and a recommendation. You choose.
4. If you go on, it plans the shortest path to one payment and works through it with you, session after session.

Come back any time. Revive keeps its notes in a `.revive/` folder in your project and picks up where you left off.

## How it works

```text
0 Recon → 1 Interview → 2 Verdict → 3 First payment path → 4 Execution ⇄ 5 Check-in → End
```

0. **Recon.** Facts first. Last commit, where the commits dried up, half-built features, whether it even builds. Then diagrams of the whole codebase with every part marked working, partial, broken or unused.
1. **Interview.** One question at a time, each grounded in something from the repo. The test for every reason you give: *"If that were solved today, would you launch tomorrow?"* If the answer is no, it was an excuse, not the cause.
2. **Verdict.** No hedging. Facts, reasons, what is worth keeping, and one recommendation: ship as it is, shrink or pivot, or kill it. If it should be killed, Revive says so and says why. The choice is still yours.
3. **First payment path.** What you sell, to whom, for how much, and what gets cut. Demand is checked before more is built: a payment link shown to real people beats another month of features.
4. **Execution.** One task at a time. Revive hands implementation to a subagent, then checks the result itself by building it, running it and making a test payment. Before launch, a fixed set of security checks has to pass.
5. **Check-in.** Every new session starts with where things stand. If a week passes with no progress, Revive stops and asks why again, because a second stall means the first diagnosis missed something.

It ends in one of two ways: a first payment from someone you do not know, or a clear decision to kill the project with the lessons written down. Both count as finishing.

## What it leaves in your project

Everything Revive knows lives in `.revive/`, as Markdown you can read and edit.

```text
.revive/state.md          current phase, facts, causes, milestones, customer quotes
.revive/architecture.md   diagrams of the codebase and what is broken
.revive/verdict.md        the verdict and what you chose
.revive/log.md            one line per session
.revive/checks.md         pre-launch check results
.revive/retro.md          written once, at the end
```

## Good to know

- **It is blunt on purpose.** If you want encouragement, this is the wrong tool.
- **It keeps scope small.** Anything the first payment does not need is written down and left alone.
- **You stay in charge of the outside world.** Opening a payment account, identity checks, buying a domain, posting publicly and installing plugins are yours to do or approve.
- **Payments assume a global, US-baseline seller.** Stripe by default, a merchant of record such as Polar as the alternative. Country-specific paperwork is outside what Revive covers.
- **Customer-facing text is written in English.** Revive talks to you in your own language.
- **No legal or tax advice.**

## What's inside

```text
skills/revive/SKILL.md                         ground rules, roles, the phases
skills/revive/references/recon.md              repo checks, architecture diagrams
skills/revive/references/interview.md          the diagnostic interview
skills/revive/references/verdict.md            verdict format and style
skills/revive/references/payment-path.md       the plan, demand check, payment rules
skills/revive/references/execution.md          skill routing, task briefs, debugging
skills/revive/references/prelaunch-checks.md   security checks before launch
skills/revive/references/state-files.md        templates for .revive/
```

## Works well with

Revive runs on its own. When one of these is installed it uses it for the matching task. It may suggest one, and it never installs anything without asking.

- [frontend-design](https://github.com/anthropics/skills/tree/main/skills/frontend-design) for UI work
- [marketingskills](https://github.com/coreyhaines31/marketingskills) (`copywriting`, `pricing`, `offers`, `prospecting`, `launch`) for the landing page and launch posts
- The official [Stripe](https://github.com/stripe/ai) and [Polar](https://github.com/polarsource/agent-toolkit) skills for payment integration
- [deploy-to-vercel](https://github.com/vercel-labs/agent-skills) for deployment

## Credits

The diagnostic interview is adapted from the `interview-me` skill by Addy Osmani ([addyosmani/agent-skills](https://github.com/addyosmani/agent-skills), MIT License). See [THIRD_PARTY_NOTICES.md](skills/revive/THIRD_PARTY_NOTICES.md).

## License

MIT. See [LICENSE](LICENSE). Third-party work keeps its own license.
