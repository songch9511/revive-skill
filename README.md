# Revive

A Claude Code skill that revives an abandoned vibe-coded project and drives it to its first payment from a stranger.

Revive reads the repo first, interviews the owner to find the decisive reason the project stopped, gives a blunt verdict (ship now, shrink or pivot, or kill), and then plans and executes the shortest path to a first paying customer. Progress is kept in a `.revive/` folder inside the target repo so the work continues across sessions.

## Status

Draft. The skill has not been run against a real project yet.

Not done yet:

- test runs on real stalled projects
- copying the six bundled third-party skills (`frontend-design` and five from `coreyhaines31/marketingskills`)
- plugin packaging (`plugin.json`, `BUNDLED_SKILLS.md`)
- a license for this repository

## Layout

| Path | What it is |
|---|---|
| `skills/revive/SKILL.md` | The skill: ground rules, roles, phases 0 to 5 |
| `skills/revive/references/` | Per-phase instructions, loaded when a phase starts |
| `skills/revive/THIRD_PARTY_NOTICES.md` | License notices for adapted work |
| `docs/specs/revive-skill.md` | The spec the skill was written from (Korean) |
| `reports/` | Research report on third-party skills per slot (Korean) |
| `research_notes/` | Notes behind the report (Korean) |

## Phases

```
0 Recon → 1 Diagnostic interview → 2 Verdict → 3 First payment path → 4 Execution loop ⇄ 5 Check-in → End
```

## Credits

The diagnostic interview is adapted from the `interview-me` skill by Addy Osmani ([addyosmani/agent-skills](https://github.com/addyosmani/agent-skills), MIT License). See `skills/revive/THIRD_PARTY_NOTICES.md`.
