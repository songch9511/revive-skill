# Reddit direct reading — supplement to the Revive slot research (read 2026-11-22)

All items below were read first-hand on reddit.com through the Aside browser (`aside repl`, logged-out, read-only). This file replaces the "Reddit is second-hand" gap in the other five notes. Nothing here was taken from search-engine snippets or third-party summaries.

## 0. Method, coverage, and limits

**Threads opened and read: 41.** Search result pages loaded: 35.

How to read the metadata:
- "Age" is Reddit's relative age as displayed on 2026-11-22 ("4d ago", "2mo ago").
- "Votes / comments" are the figures shown on the search listing (logged-out view). Thread pages did not expose per-comment vote counts in the page text, so comment popularity is unknown unless the subreddit's auto-summary bot stated it.
- Only the comments Reddit rendered by default were read. "View more comments" and collapsed replies were NOT expanded (that would require clicking). Large threads are therefore sampled, not exhaustive.
- **POST READ** = thread opened, post body and default-loaded comments read. **SEARCH LISTING ONLY** = only title/age/votes seen in search results.
- Model/product names (Opus 5.5, Fable 5.2, "Mythos", "Astra", GPT-6 Pro) are reproduced as posters wrote them, not verified.
- Everything is anecdote from pseudonymous users. Several "benchmark" posts are n=1 to n=3 runs by a single person.

**Queries run** (all on `reddit.com/search`, time filter = past year unless noted):

| # | Query | Scope |
|---|---|---|
| 1 | impeccable claude skill | all |
| 2 | impeccable vs taste skill vs frontend-design | all |
| 3 | ui-ux-pro-max skill | all |
| 4 | design skill impeccable | r/ClaudeCode, top |
| 5 | superpowers systematic-debugging skill | all |
| 6 | superpowers worth it | r/ClaudeCode |
| 7 | matt pocock skills diagnose bugs | all |
| 8 | stopped using superpowers skills too many tokens | all |
| 9 | lemon squeezy shutting down alternative | all |
| 10 | Polar vs Creem vs Dodo Payments merchant of record | all |
| 11 | merchant of record without company solo founder | r/SaaS |
| 12 | polar.sh payout account review withheld | all |
| 13 | South Korea Stripe not available indie developer payments | all |
| 14 | Korean developer Polar Paddle Lemon Squeezy payout Korea | all |
| 15 | creem.io review payout | all |
| 16 | polar.sh experience account suspended | all |
| 17 | vercel plugin claude code telemetry | all |
| 18 | claude code deploy skill vercel railway cloudflare | all |
| 19 | where to deploy vibe coded app vercel railway cloudflare | r/vibecoding |
| 20 | Korea solo developer Stripe Paddle Polar payout | all |
| 21 | marketingskills corey haines claude | all |
| 22 | claude marketing skills landing page copy solo founder | all |
| 23 | humanizer skill claude AI writing | all |
| 24 | solo-founder-skills claude | all |
| 25 | vibe security skill claude code | all |
| 26 | vibe coded app hacked exposed supabase RLS API key leaked | all, top (useless — returned unrelated viral posts) |
| 27 | security review before launch vibe coded app claude /security-review | all |
| 28 | cloudflare security-audit skill | all |
| 29 | revive abandoned side project claude code finish | all |
| 30 | first paying customer vibe coded app what worked | all |
| 31 | vibe coded app got hacked users data exposed | r/vibecoding, top (useless — unrelated viral posts) |
| 32 | too many skills context bloat claude code | all |
| 33 | Are people here actually using skills | r/ClaudeAI, past month |
| 34 | claude code plugin idea to first paying customer launch coach solo founder skill | all |
| 35 | unfinished side projects graveyard finally shipped got first customer | r/SideProject |

**Access problems**
- One HTTP 429 (rate limit) on a thread page after ~30 page loads at ~5 s spacing. Waited 45 s, retried once, it loaded. Spacing was then raised to 10–14 s and no further 429 occurred.
- `sort=top` on broad queries returns unrelated viral posts; relevance sort is the usable one.
- No CAPTCHA, no login wall on search or thread pages. JSON endpoints were not attempted (known blocked).
- **Korea: zero usable results.** Three Korea-specific queries (13, 14, 20) returned no thread by or about a Korea-based seller. The closest analogues read are founders in Egypt, India, Morocco, Kazakhstan, UK (section 3).
- No post or comment containing instructions aimed at AI agents was encountered. One commenter (r/claudeskills, humanizer thread) explicitly advised auditing a third-party skill repo for prompt injection before installing.

**Recurring self-promotion to discount**
- `u/vinishkapoor` — four of the "I tested skill X" posts read here (design x3, deploy x1) all link to the poster's own blog aiparabellum.com. Useful measurements, but one author, one run each, low votes (0–7).
- `u/skillselion` — runs a skills-ranking site; posts install-count leaderboards and recommends skills in comments.
- `u/rizeCapital` — weekly "top skills" posts link to own directory alyn.dev (a commenter called this out).
- `u/Hydronix2731` — debugging benchmark post promotes own eval framework (terum-skills).
- `u/DeadCEO` — repeatedly plugs own OpenDesigner in design threads ("shameless but on-topic").
- `u/DutyOnly4308` — sells a paid SEO skill pack; disclosed.
- Vendor staff appear in payment threads: Paddle (`u/heymcgovern`), Stripe (`u/stripe_sofia`), Nexway, ToHuman, IntelliBreach, LicenseSpring, a chargeback firm. All self-disclosed.

---

## 1. Design slot (UI/UX)

**1.1 "Best skill for UI/UX designing"** — r/claudeskills, 7d ago, 49 votes / 32 comments — POST READ
https://www.reddit.com/r/claudeskills/comments/1xwwree/best_skill_for_uiux_designing/
- Backend-heavy dev asks for a skill that avoids the "same AI template UI". First and most-echoed answer: Impeccable ("worked pretty well for me"; "very powerful when used correctly, read through the docs").
- Caveat from a commenter: Impeccable "requires that you at least somewhat know what visual direction you aim for" — suggests running Matt Pocock's `grill-me` first to define who you are designing for.
- Dissent: one commenter finds Impeccable "still produces common design issues and feels pretty generic" and recommends `vercel-labs/agent-skills` `web-design-guidelines` as an audit pass on an existing design.
- Additional names: `emilkowalski/skills` (`find-animation-opportunities`, `animate`) for motion — recommended by u/skillselion (ranking-site owner; cites ~258K installs); OpenDesigner (author self-promo); "screenshots of 2–3 sites you like as the brief, before picking a skill".
- Not mentioned at all in this thread: `ui-ux-pro-max`, Taste skill, Anthropic `frontend-design`.

**1.2 "Same dashboard brief built 3 times: no skill, frontend-design and Impeccable"** — r/ClaudeCode, 16d ago, 0 votes / 5 comments — POST READ (author blog self-promo)
https://www.reddit.com/r/ClaudeCode/comments/1xp9mtq/same_dashboard_brief_built_3_times_no_skill/
- Same detailed prompt, one run each. All three passed the same overflow/keyboard/contrast checks. Reported: no skill 4m0s / 28,025 output tokens; `frontend-design` 3m2s / 20,763; Impeccable 5m1s / 33,494 ("about 60% more output tokens than frontend-design for a result that passed the same checks"). `frontend-design` judged "most distinct look" and cheapest.
- Poster's own caveats: brief spelled out every tested state; Impeccable's launcher/hooks did not run; one run each. Side finding: first "no skill" run silently loaded Claude Code's built-in `dataviz` skill.
- Commenter: skills "mostly changed the look", stable look needs 3+ reference images.

**1.3 "Tested Hallmark and Impeccable in Claude Code this week"** — r/claudeskills, 23d ago, 7 votes / 0 comments — POST READ (same author, blog self-promo)
https://www.reddit.com/r/claudeskills/comments/1xjghnu/tested_hallmark_and_impeccable_in_claude_code/
- Hallmark (`nutlope/hallmark`, MIT per poster): plain build 44 s / $0.16 vs Hallmark 3m32s / $0.87; "genuinely finished" page, leaves unknown facts as visible empty slots; idle context cost "about 90 tokens".
- Impeccable (`pbakaus/impeccable`, Apache 2.0 per poster): plain 55 s / $0.19 vs 305 s / $0.91; bolder result; "`/impeccable critique` was the best thing in either test" (found a real form bug); `polish` changed little; free detector gave false positives.
- **Install footprint claim:** Impeccable "installs a lot more than a skill folder: 4 agents, 3 hooks, a ~/.impeccable folder even on a project install, and telemetry on by default". Single-source; verify against the repo before bundling.
- "Both cost about 5x a plain build". Poster's landing: Hallmark for building, Impeccable mainly for critique.

**1.4 "Tried the Taste skill on the same landing page brief"** — r/claudeskills, 16d ago, 1 vote / 1 comment — POST READ (same author)
https://www.reddit.com/r/claudeskills/comments/1xp1uzk/tried_the_taste_skill_on_the_same_landing_page/
- "A clear step up" over no skill (left-aligned headline, real photos) but not perfect. Skill's real name is `design-taste-frontend`, "not taste-skill". Two runs looked different. Claude skipped the palette/layout helper steps and browser check, and invented address/hours/prices. The skill's helper scripts were blocked by Claude Code's permission check as external code.

**1.5 "Best Claude Frontend/Design/UX-UI Skill Set"** — r/ClaudeDesign, 2mo ago, 71 votes / 16 comments — POST READ
https://www.reddit.com/r/ClaudeDesign/comments/1wvfgec/best_claude_frontenddesignuxui_skill_set/
- Answers are mostly not skills: 21st.dev, React Bits, Magic UI, Aceternity UI, styles.refero.design, generate a reference image then extract a spec.
- One detailed workflow report: Mobbin MCP + Opus 5.5 xhigh + Impeccable — "first approach I've gotten to work the way I want"; also uses a humanize skill for first-draft copy.

**1.6 "Best current skills for Landing Page development?"** — r/ClaudeAI, 25d ago, 4 votes / 15 comments — POST READ
https://www.reddit.com/r/ClaudeAI/comments/1xhhjjf/best_current_skills_for_landing_page_development/
- Top answer: "Skills matter less than the brief"; Anthropic `frontend-design` is "a good starting point"; give a real reference, the audience, the one action, check at mobile width, keep a short style file.
- Another: "+1 on frontend-design and also impeccable … but the brief and a real reference site still do most of the work".
- OP's reply: admits falling for "you just need these three skills" videos.

**1.7 Cross-thread mentions**
- "My favorite Claude skills this week" (r/claudeskills, 2d, 424/37 — POST READ, directory self-promo) lists Impeccable, Design Taste Frontend (Leonxlnx), Hallmark in its top 10. A commenter: "impeccable is good but i swear on everything it uses so much tokens."
- "Drop your best Claude skills" (r/ClaudeAI, 28d, 513/108 — POST READ): a commenter uses `manish-uxai/design-review` after major changes to catch hardcoded hex values and duplicated components (likely author).

**Search listing only (design)**
- "Taste Skill: The Anti-Slop Frontend Framework for AI Agents (93k stars)" — r/BestGitHubRepos, 2mo, 178/9.
- "Impeccable is a design language that actually makes AI-generated UIs look good (73k stars)" — r/BestGitHubRepos, 2mo, 41/0.
- "Best skill for UX/UI? Impeccable vs. UX/UI Pro Max vs. others" — r/ClaudeCode, 7mo, 11/9; cross-post in r/UXDesign, 7mo, 24/33.
- "What is the best model and skill for ui/ux?" — r/ClaudeAI, 1mo, 19/11.
- `ui-ux-pro-max`: no 2026 thread with real discussion surfaced; only the 7-month-old comparison title and low-vote promo posts.

---

## 2. Getting-unstuck slot (debugging, stale codebase)

This is where Reddit most clearly diverges from the non-Reddit evidence.

**2.1 "Matt Pocock and Superpowers are overrated (for debugging)"** — r/claudeskills, 2mo ago, 86 votes / 40 comments — POST READ (author promotes own eval framework)
https://www.reddit.com/r/claudeskills/comments/1wv6eoq/matt_pocock_and_superpowers_are_overratedfor/
- Direct test of exactly our two front-runners: `mattpocock` `diagnosing-bugs` and Superpowers `systematic-debugging` vs a plain prompt, on 15 real bugs from the poster's own repo, 3 runs each, graded by hidden tests from the real fix.
- Result: all three fixed 9/15. Skills added "~3 extra minutes per bug to get to the same place for no uplift". Different bugs were missed by each (plain gave up on one both skills solved; Superpowers missed a 12-line fix plain did in 6 min).
- Small Pocock advantage: "the only one that never broke another test" and smallest diffs (median 32 lines vs 41 and 48).
- Poster's advice: keep the packs if you like them but "consider uninstalling the debugging portion".
- Comments largely agree ("cargo cult", "bloating the context with stuff that is already in the training data", "no longer relevant with newer models"); several still value `grill-me` / `to-spec` / `to-tickets`. One comment suggests a `deep-why-debugging` skill; another says "just use CodeRabbit".

**2.2 "What is your opinion on the Superpowers skill?"** — r/ClaudeCode, 4d ago, 39 votes / 64 comments — POST READ
https://www.reddit.com/r/ClaudeCode/comments/1xz7w0k/what_is_your_opinion_on_the_superpowers_skill/
- Triggered by a YouTube video calling popular skills "useless bloatware" (several commenters note the YouTuber is selling a course and the comparison was weak).
- Dominant sentiment in loaded comments: "great 9 months ago. Mostly unnecessary now"; "obsolete and bloated"; "Fable 5.2 doesn't play nice with Superpowers"; "stopped using it".
- What survives: `brainstorming` and `writing-plans` are repeatedly singled out as still worth it ("the rest mostly repeats what the model already does"). A minority still uses it heavily for process consistency ("pilots still use checklists").
- Advice repeated: re-evaluate every skill at each model release; take the parts you like and write your own leaner skill.

**2.3 "PSA: Superpowers skill with opus ruined my codebase"** — r/ClaudeCode, 7d ago, 255 votes / 128 comments — POST READ
https://www.reddit.com/r/ClaudeCode/comments/1xwmeln/psa_superpowers_skill_with_opus_ruined_my_codebase/
- Test count went from 1,400 to nearly 4,000 in two weeks; poster says over 70% tested implementation, not behaviour. Cause identified as Superpowers' TDD rules; own "write useful tests" instructions were overpowered by the skill on long unsupervised runs.
- Comments: "removed superpowers months ago — fully obsolete"; "Loading any one of the Obra skills seems to poison the entire session's reasoning"; again "I only use brainstorming and writing-plans". Counter-voices: "never had an issue", and the over-testing also happens without Superpowers.
- Practical remedy several people give: mutation testing (Stryker, mutmut) to prune tests; rule "a new test only stays if it fails when the code it covers is broken".

**2.4 "Are Superpowers, skills and SDD still worth it on top of Opus 5.5, or is a single good prompt enough?"** — r/ClaudeAI, 1mo ago, 154 votes / 81 comments — POST READ
https://www.reddit.com/r/ClaudeAI/comments/1xckkpr/are_superpowers_skills_and_sdd_still_worth_it_on/
- Four-arm single-run benchmark (plain prompt / SDD / SDD + Pocock + Ponytail / Superpowers) with spec already fixed. Poster stresses it is not conclusive.
- The subreddit's auto-summary: consensus is a single well-crafted prompt beats large generic packs once a spec exists; packs may still help brainstorming from a vague idea.
- Most concrete data point (u/Physical-Economist27, 3 months, "a few thousand runs"): Superpowers as mandatory flow vs lean setup on one greenfield project — after correcting cost accounting, "$361 per merged ticket under Superpowers vs. $143 lean, with 6x more tickets merged". Review loops under the heavy flow "kept spawning new tickets for minor findings".
- **What did not go away:** real bugs the agent's own reviews miss. An independent, read-only adversarial reviewer over the whole diff still blocks ~1 in 10 runs; in-run review skills "had often looked at the exact spot and still missed it".
- Recurring advice: keep only narrow procedures you would otherwise retype (review loop, release checklist, "smallest correct change" mode); tie each skill to a failure you hit more than twice; ask whether a skill "changes the artifact or only the transcript".

**2.5 "Superpowers vs Agent Skills vs Matt Pocock, which one should you install?"** — r/AgentSkills, 3mo ago, 109 votes / 38 comments — POST READ (post body in French; author promotes own `skillpack` CLI)
https://www.reddit.com/r/AgentSkills/comments/1w7zmqf/superpowers_vs_agent_skills_vs_matt_pocock_which/
- Only thread found that discusses `addyosmani/agent-skills` (as "full lifecycle") — and only in the post body; no commenter reports using it.
- Post's warning: installing two packs as active routers causes slash-command name clashes, competing session-start hooks, and skills competing for the same intent.
- Comments: "None, frontier models are already smart enough so it's just token burn" vs "Pocock skills aren't bloat, they are just useful saved prompts"; several run Pocock + Cursor's `pstack`; one prefers Pocock over Superpowers because Superpowers "burn my token fastly". `/wayfinder`, `/handoff`, `/grill-with-docs` praised. Ponytail endorsed; "caveman" called bloat citing a JetBrains test.

**2.6 "Are there any best skills to install for solo developers?"** — r/claudeskills, 2mo ago, 39 votes / 22 comments — POST READ
https://www.reddit.com/r/claudeskills/comments/1wqg6mj/are_there_any_best_skills_to_install_for_solo/
- First answer recommends Superpowers but adds "consider all skills transient unless they add context for your codebase". Replies: "pretty outdated when using latest models"; "drains my limit very quick if you spawn subagents".
- Others: Ponytail; "the best skills are usually the ones you make yourself"; "I just go with the model at this point"; "the more skills you have the more your initial context gets big".

**Search listing only (debugging / frameworks)** — titles alone show the trend
- "Are you guys still using the superpowers skill?" — r/ClaudeCode, 5mo, 188/130.
- "Is Superpowers still relevant?" — r/ClaudeCode, 3mo, 159/71.
- "Superpowers skill is so bad now" — r/ClaudeCode, 2mo, 4/68.
- "My weekly usage limit was being burned almost daily. Then I deleted the Superpowers plugin…" — r/OpenaiCodex, 4mo, 146/63.
- "Has anyone actually benchmarked whether superpowers improves performance?" — r/ClaudeCode, 21/31.
- "Matt Pocock's skills vs plain Claude Code on 3 small tasks. /grill-me was the useful one" — r/claudeskills, 19d, 216/12.
- "A scientific take on Matt Pocock's skills" — r/claudeskills, 7d, 218/13.
- "GSD vs Superpowers vs BMAD?" — r/ClaudeCode, 2mo, 6/12.

**Candidates we missed that recur:** Ponytail (`DietrichGebert/ponytail` — "laziest senior dev", write less code; named in at least 6 of the threads read), Matt Pocock's `grill-me` / `grill-with-docs` / `wayfinder` / `handoff` (praised far more than his `diagnosing-bugs`), GSD ("Get Shit Done"), Cursor `pstack`, BMAD, OpenSpec. None of these is a debugging skill; Reddit has no agreed "debugging skill" at all.

---

## 3. Payment slot

**3.1 Lemon Squeezy shutdown — confirmed first-hand, reactions**

"Lemon Squeeze shutting down" — r/SaaS, 6d ago, 97 votes / 86 comments — POST READ
https://www.reddit.com/r/SaaS/comments/1xxsrn7/lemon_squeeze_shutting_down/
- Sellers received a shutdown notice; "March 2027 is a decent runway". Common reading: "stripe bought it to shut it down".
- Where people say they are going: Polar most often ("working pretty well", "approved me in 3 minutes", "support can be a little slow", "integrating it went great"); Paddle ("store got approved in 40 minutes" vs "paddle will ban your account with no explanation"); plain Stripe; FastSpring (10-year user, fees negotiable, slow feature pace).
- One seller had waited 11 days for LS store approval when the notice arrived.
- A chargeback-firm commenter (disclosed): on migration, check the card-statement descriptor and email customers before the first renewal.

"Lemon Squeezy Shutdown" — r/macapps, 6d ago, 35 votes / 75 comments — POST READ
https://www.reddit.com/r/macapps/comments/1xxs6ek/lemon_squeezy_shutdown/
- LS is steering sellers to **Stripe Managed Payments** (Stripe's own merchant-of-record product). Several are "very happy" with it, but: it "handles the payment and the VAT, not the rest" — no licence keys, no file hosting; and "some countries don't support" it.
- Polar is called "the closest 1:1 to what LS did" (MoR + licence keys with per-device limits + hosted downloads). Many say they are moving to Polar. Others: Paddle (long-time happy users), Dodo (two users happy so far), Freemius (two), Kelviq, Zylvie, FastSpring + LicenseSpring (vendor post), Gumroad.
- Advice: export LS customers and licence keys before the deadline — "that part does not migrate by itself".
- One: "never stripe if you're non us."

Search listing only: "Lemon Squeezy shutting down March 2027" (r/SaaS, 4/9); "Best Lemon Squeezy Alternatives (it's shutting down!)" (r/DigitalProductSellers, 4d, 10/6); "Lemon Squeezy shutting down — what are other developers using…" (r/softwaredevelopment, 2d, 4/5); "Lemonsqueezy is stopping service" (r/Bangalorestartups, 5d, 1/11).

**3.2 Choosing a provider**

"PAYMENT PLATFORMS??? WHICH ONEEE" — r/SaaS, 6d ago, 8 votes / 48 comments — POST READ
https://www.reddit.com/r/SaaS/comments/1xx6d79/payment_platforms_which_oneee/
- OP (US LLC) found Dodo support "very slow and not helping". Majority answer: Stripe if you are in a supported country and can turn on Stripe Tax; Paddle or Polar if you want tax off your plate. The first question everyone asks: where is the business registered.
- Repeated practical advice: send each provider a pre-sales question to test support speed; compare payout schedule/minimums/holds for new accounts, not just fees; apply to Paddle days before launch because it reviews site, pricing and refund policy. Freemius recommended twice.

"What's the most solo-founder-friendly Merchant of Record right now…" — r/SaaS, 7mo ago, 6 votes / 23 comments — POST READ
https://www.reddit.com/r/SaaS/comments/1sqfvcu/whats_the_most_solofounderfriendly_merchant_of/
- Closest match to our user: **solo founder, no registered company, country where Stripe is not an option** (Egypt). Went with Lemon Squeezy; approved in 3 days after submitting a demo video. (Now moot given the shutdown.)
- LS KYC questions reported by an India-based seller: government ID, product demo video, personal social-media URLs, description of what is sold.
- Creem: "quick and easy process" for a UK user, but support told the Egyptian OP it was **invite-only** (possibly country-dependent).
- Polar: a UK user could not pass Stripe-powered selfie/passport verification after "dozens of attempts" and Polar "said they couldn't help".
- MoR-industry commenter (Nexway, disclosed): prefer a provider that does KYC before you sell; "instant" signups are followed by 90-day freezes at the first 100 subscribers.

"Got rejected by Lemon Squeezy, Paddle, and Polar as a Moroccan founder. Here's what actually worked" — r/SaaS, 2mo ago, 1 vote / 3 comments — POST READ
https://www.reddit.com/r/SaaS/comments/1wj23y1/got_rejected_by_lemon_squeezy_paddle_and_polar_as/
- 18-year-old solo founder, no entity. Product done in June, first able to charge in August — "not because of anything technical". Polar "auto-rejected me before a human looked at it". Freemius accepted (case-by-case review, built for individuals). Stripe Connect wanted a W-8BEN before payouts. Lesson: sort out your local sole-proprietor regime early. Still at zero paying users.

**3.3 Per-provider experiences**

Polar
- "Polar.sh in 2026: real experience with reviews and payouts outside the US/EU?" — r/SaaS, 2mo ago, 2 votes / 5 comments — POST READ
  https://www.reddit.com/r/SaaS/comments/1wmbv4o/polarsh_in_2026_real_experience_with_reviews_and/
  Kazakhstan founder's question set (payouts via Stripe Connect Express in local currency; 7-day settlement delay for new orgs). Only substantive reply: payouts "stuck in 'Review' for 2 months now"; another user asked 9 days ago whether it was ever resolved — no answer.
- "Thinking about moving from Polar to Stripe. Has anyone here done it?" — r/SaaS, 4mo ago, 9 votes / 12 comments — POST READ
  https://www.reddit.com/r/SaaS/comments/1v9pr0m/thinking_about_moving_from_polar_to_stripe_has/
  Multiple customers hit errors on Polar's hosted checkout; nothing the seller could debug; waiting on support. Another commenter "couldn't even get things set up" on Polar. Stripe employee (disclosed) points to Stripe Managed Payments as MoR in 80+ countries, with the caveat that imported subscriptions do not get MoR coverage.
- Positive Polar mentions are numerous but short (sections 3.1, and "Polar.sh all the way!" in the Paddle thread).
- Search listing only: "Update: Polar approved my solo SaaS after Lemon Squeezy and Paddle rejected me" (r/SaaS, 3/12); "Paddle is slow and Polar.sh is non-responsive" (r/SaaS, 9mo, 1/5); "Need help with Polar.sh Identity Verification in India" (r/stripe, 7mo, 2/8); "Any Sri Lankan solo devs using Polar.sh?" (r/srilanka, 5mo, 13/8).

Paddle
- "DO NOT USE PADDLE AS YOUR PAYMENT PROCESSOR" — r/SaaS, 2mo ago, 59 votes / 58 comments — POST READ
  https://www.reddit.com/r/SaaS/comments/1whzvnu/do_not_use_paddle_as_your_payment_processor/
  B2B review-page SaaS, approved, 3 months of use; checkout disabled "the day after I wanted a payout", vague policy reason. Four other commenters report the same pattern (approved, migrated, then offboarded within days/weeks). One counter: 13-day domain verification then stuck. Polar and Freemius suggested as alternatives.
- "Dodo Payments vs Paddle…" — r/SaaS, 3mo ago, 9 votes / 31 comments — POST READ
  https://www.reddit.com/r/SaaS/comments/1w3k97d/dodo_payments_vs_paddle_which_is_the_best/
  "Avoid paddle at any and all costs" (account locked after months with paying customers, no appeal, 5 months wasted) vs "Using Paddle for 5 years, 0 issues". A Paddle employee answers questions in-thread. Dodo: "easy to implement" but OP hit a bug where a user with an incomplete payment was locked out of upgrading.
- Search listing only: "If you're planning to use paddle, STOP" (r/SaaS, 6mo, 44/78).

Dodo Payments
- "Dodo Payments held my money for 120 days, then decided to keep ALL of it" — r/PaymentProcessing, 1mo ago, 4 votes / 10 comments — POST READ
  https://www.reddit.com/r/PaymentProcessing/comments/1x0to6o/dodo_payments_held_my_money_for_120_days_then/
  Solo founder, AI fitness-coach app, under $500. Account closed after compliance review; balance held 120 days, then fully retained, "final, not subject to appeal". Another commenter: blocked after ~6 months with no warning or migration time.
- In the Paddle thread: "Same with dodopayments… especially if you're in India".
- Mixed: two r/macapps users and one r/SaaS user report Dodo working fine; OP of 3.2 found support slow.

Creem
- No dedicated thread found. Only the two mentions in 3.2 (easy for a UK user; invite-only for an Egyptian user, 7 months ago).

Other names that recur and are not on our list: **Stripe Managed Payments**, **Freemius** (most consistently positive for individuals without a company), FastSpring, PayPro Global, Gumroad, Kelviq.

**3.4 Korea**
- No Reddit thread found on selling from Korea via any of these providers. Treat the Korea question as still unanswered by Reddit; the transferable pattern from Egypt/India/Morocco/Kazakhstan is: (a) MoR approval and payout review, not integration, is the blocker; (b) automated risk scoring on country + no entity; (c) payout holds surface only at first withdrawal.

---

## 4. Deployment slot

**4.1 "Loaded 14 deploy plugins into Claude Code…"** — r/ClaudeCode, 14d ago, 2 votes / 4 comments — POST READ (author blog self-promo)
https://www.reddit.com/r/ClaudeCode/comments/1xqxg43/loaded_14_deploy_plugins_into_claude_code_vercel/
- Official marketplace reportedly has deploy plugins for 14 platforms; loading all adds **165 skills and 11 MCP connections**.
- Hooks: "Vercel's sends a daily activity ping and the skill names you use to its telemetry by default, and writes state under ~/.claude. `VERCEL_PLUGIN_TELEMETRY=off` turns that off." "Railway's hook auto-approves single Railway commands that pass its safety checks." Nine of 14 have no hooks.
- Plan-only comparison (nothing deployed): Cloudflare flagged that `server.js` won't run on Workers and proposed a dry run; Netlify gave a two-line config and warned about Git push overwriting manual deploys; Render admitted unverified assumptions; Railway `railway up` then `railway domain`; Vercel explained rollback limits.
- Top comment: the Railway auto-approve hook "is the bigger deal than Vercel's telemetry" because `railway up` / `railway variables set` can run unprompted against a linked production environment. Recommended: install at user level, enable exactly one per repo in `.claude/settings.json`.

**4.2 "Vibe coders (especially if you're not very technical): where do you deploy your apps and how has it gone?"** — r/vibecoding, 3mo ago, 44 votes / 68 comments — POST READ
https://www.reddit.com/r/vibecoding/comments/1vt6kkl/vibe_coders_especially_if_youre_not_very/
- Most frequent answers in loaded comments: Cloudflare Pages/Workers (free tier "gives you much more"; "just ask Codex to help you configure it"), Vercel (+ Supabase + GitHub; env vars "a little bit tricky"; "uses your credit every time you deploy"), Railway ("could get something live without needing to become a DevOps engineer"), Netlify, Render, Fly.io, Hetzner/self-host with Coolify.
- Cost shock: one user on Render was "on pace to cost me $1300/month" in egress and moved to a Hetzner box.
- Useful framing from a non-infra user: "Deployment itself has usually been the easy part. The harder part is everything you don't know to worry about" — env vars, auth, exposed data, AI changes that quietly open something up.
- A developer says they now choose "whatever has a great agentic/MCP/skill solution".

**Search listing only (deploy)**
- "Never host your app on Vercel or Railway" — r/SaaS, 6mo, 83/120.
- "Claude code autonomously installing 3rd party app — Desktop Commander without consent and enabling telemetry…" — r/ClaudeCode, 2mo, 41/29 (telemetry-sensitivity signal, not Vercel).
- "Follow-up to my migrating to Cloudflare post: made an agent skill that lets Claude Code / Codex do the whole migration…" — r/lovable, 6mo, 56/28.
- No Reddit thread specifically about `vercel-labs/agent-skills` `deploy-to-vercel` or a "vercel-plugin telemetry backlash" surfaced; the telemetry fact appears only inside 4.1.

---

## 5. Landing page, copy, launch slot

**5.1 "Top 7 Claude skills for marketing and SEO, by install count. One author holds four of them."** — r/Agentic_SEO, 3mo ago, 39 votes / 14 comments — POST READ (poster runs a ranking site)
https://www.reddit.com/r/Agentic_SEO/comments/1vpgr1w/top_7_claude_skills_for_marketing_and_seo_by/
- Six of the top seven by installs are from `coreyhaines31/marketingskills` (seo-audit ~188K, copywriting ~179K, marketing-psychology, content-strategy, programmatic-seo, marketing-ideas). Poster's reading: people pull individual skills rather than the whole repo.
- Only first-hand quality comment: Corey Haines "was one of the first to put something out… they are OK but have some glaring holes for anyone who knows what they are doing."
- Others: installs show what was found first, not what was kept; check whether a skill says where each number comes from.

**5.2 "What's the best humanizer skill out there?"** — r/claudeskills, 4mo ago, 98 votes / 52 comments — POST READ
https://www.reddit.com/r/claudeskills/comments/1v8wa5r/whats_the_best_humanizer_skill_out_there/
- `blader/humanizer` is not named in the loaded comments. Named instead: `petergyang/no-ai-slop` (with "audit the repo first" warning; another calls its ban list "pretty random"), a self-made skill from Wikipedia's "Signs of AI writing" page, `rephrasyai/rephrasy-skills`, an Orwell-rules skill.
- Strongest consensus: a **personal voice profile** (built from ~100 answered questions, or from 20+ before/after edits of your own prose) beats any generic humanizer; "I still hand edit everything".
- Generic humanizers do not reliably pass detectors (Copyleaks, GPTZero, Turnitin, Pangram) — several report the skill made scores worse. Not relevant to landing copy, but shows what users expect from the name.

**5.3 Humanizer mentions in general threads**
- "Drop your best Claude skills" (r/ClaudeAI, 28d, 513/108 — POST READ): the mod-bot summary lists a "humanizer" skill among honourable mentions; a commenter built one from the Wikipedia guideline.
- "Are people here actually using skills?" (r/ClaudeAI, 8d, 57/71 — POST READ): a solo SaaS builder's daily list includes both `humanizer` and a personal-voice skill; another uses `/unslop`.
- Search listing only: "The most useful Claude skill I ever created: humanizer" — r/ClaudeCode, 7mo, 623/118 (likely the `blader/humanizer` author's post; not opened). "Humanizer: Agent skill that removes signs of AI-generated writing (63k stars)" — r/BestGitHubRepos, 21d, 1.2K/30. "ste80-humanizer claude skill" — r/claudeskills, 12d, 116/4.

**5.4 Landing pages:** see 1.6 — the brief, a reference site, and "one action the page should drive" matter more than the skill; `frontend-design` + one copywriting skill is the suggested minimum.

**Search listing only (marketing packs — mostly author launches)**
- "I built 12 marketing skills into one Claude Code plugin…" — r/claudeskills, 2mo, 233/25.
- "I just made the most insane marketing skill" — r/claudeskills, 5mo, 219/24.
- "46 marketing skills for founders and product marketers" — r/claudeskills, 4mo, 68/3.
- "I built 14 free marketing skills for Claude Code…" — r/claudeskills, 27d, 76/7.
- "Claude is my entire SEO team. 1.5M+ impressions in 3 months as a solo founder." — r/ClaudeAI, 6mo, 325/90.
- `whawkinsiv/solo-founder-skills`: no Reddit mention found under queries 22, 24, 34.

---

## 6. Pre-launch checks slot (verification, security)

**6.1 "I tried running the Cloudflare security-audit skill on Fable… that was a mistake"** — r/ClaudeAI, 21d ago, 3 votes / 22 comments — POST READ
https://www.reddit.com/r/ClaudeAI/comments/1xkrwiv/i_tried_running_the_cloudflare_securityaudit/
- Burned three 5-hour Max windows and 50% of weekly tokens for 11% of the audit. Another user: "even on Sonnet it took three 5hr sessions for a single run against a subset of our API… Cloudflare themselves are the only ones who can afford to use that skill."
- Explanation offered: fan-out to subagents with short prompt-cache lifetime re-reads context at full cost. OP later: dropping to Opus "worked out pretty well".

**6.2 "/security-review"** — r/ClaudeCode, 4d ago, 10 votes / 22 comments — POST READ (after one 429 retry)
https://www.reddit.com/r/ClaudeCode/comments/1xyrw11/securityreview/
- Built-in command returned "no issues" on a multi-day PR touching everything. Replies: "better than without it"; mixed — "caught a few major things" but also "clean passes on code I later found problems in", and it "gets quieter the bigger the diff is", so a clean pass on a huge diff "would make me more nervous, not less".
- Recommended use: split by area (auth, input parsing, DB) and run per chunk; run the reviewer as a separate agent with restricted reads; let a script, not the model, decide pass/fail.

**6.3 "Best Claude skills to secure vibe coded apps"** — r/vibecoding, 4mo ago, 42 votes / 7 comments — POST READ (reads like star-solicitation)
https://www.reddit.com/r/vibecoding/comments/1uve1hy/best_claude_skills_to_secure_vibe_coded_apps/
- Stack: `/plan`, Ponytail (less code = smaller attack surface), `/audit-codebase` (pentest swarm before prod), built-in `/security-review`, `/vibe-security`.
- On `/vibe-security` specifically: "this won't find much if you are already a half-decent vibe coder. Don't let it give you a false sense of security."
- Commenter tip: have a different vendor's model (Codex) run the security pass to remove bias.

**6.4 "did you actually check security before launching your vibe coded app?"** — r/startups, 9d ago, 0 votes / 32 comments (cross-posted to r/nocode, r/cursor, r/SaaS, r/Entrepreneurs) — POST READ
https://www.reddit.com/r/startups/comments/1xvcark/did_you_actually_check_security_before_launching/
- Almost no one names a skill. They name manual checks:
  1. Two test accounts; swap user B's ID into user A's request (object-level authorization).
  2. Search the built JS bundle for `sk_`, `service_role`, `secret`; run gitleaks/trufflehog on full history; rotate anything ever committed.
  3. Auth + per-user rate limit on every route that calls a paid API; hard spend caps on provider dashboards.
  4. `curl` each API route with no session.
  5. Supabase: anon key in client is expected, `service_role` never; RLS on.
  6. Lock public storage buckets; delete demo data.
- "Use the best model you can to do a security review… maybe even twice in different sessions." Enterprise users add Snyk/SonarQube.

**6.5 "Researchers scanned 380,000 vibe-coded apps"** — r/Information_Security, 4mo ago, 43 votes / 14 comments — POST READ (post itself criticised as AI-written; figures are the poster's retelling of press coverage)
https://www.reddit.com/r/Information_Security/comments/1v53bh3/researchers_scanned_380000_vibecoded_apps_heres/
- Claimed: ~40% of scanned Lovable/Replit/Base44/Netlify assets exposed sensitive data; five recurring causes — secrets in client bundle, missing RLS, authentication without authorization, open debug/admin routes, wildcard CORS. Cites a "Moltbook" database compromise.
- Commenter resource: `Arcanum-Sec/sec-context` (anti-pattern context docs). A scanner vendor (disclosed) notes all five are visible from outside without source access.

**6.6 Verification:** see 2.4 — the one thing practitioners say still pays is a fresh, independent, adversarial reviewer over the final diff; in-session review skills (Superpowers' included) miss bugs they looked straight at. No thread discussed Superpowers `verification-before-completion` by name.

**Search listing only (security)**
- "Cloudflare open-sourced the security-audit skill…" — r/pwnhub, 1mo, 106/5.
- "A massive Security Skill pack for Claude (29 Modules / OWASP Top 10)" — r/claudeskills, 7mo, 69/16.
- "I vibe-coded an app. What should I check in terms of security?" — r/SaaS, 1mo, 3/21.
- "Best Skills and Workflows for Vibe Coders" — r/claudeskills, 4mo, 72/21.
- `raroque/vibe-security-skill` by repo name: not found; only the `/vibe-security` mention in 6.3.

---

## 7. Cross-cutting

### 7.1 What people keep vs drop

"Are people here actually using skills?" — r/ClaudeAI, 8d ago, 57 votes / 71 comments — POST READ
https://www.reddit.com/r/ClaudeAI/comments/1xw4eoc/are_people_here_actually_using_skills/
- Mod-bot summary: "a resounding yes". But the kept skills are almost all **self-written**: skills that call deterministic scripts, repo/ERP knowledge, timesheet, PR follow-up loops, task parking, session handoff. "I never went on the internet looking up for a skills."
- Built-in `skill-creator` recommended for making them. Third-party names that do appear: Ponytail, `/unslop`, humanizer.

"What Claude skills have changed your entire workflow for the better?" — r/claude, 9d ago, 305 votes / 82 comments — POST READ
https://www.reddit.com/r/claude/comments/1xuknes/what_claude_skills_have_changed_your_entire/
- Kept: end-of-session "anything else?" sweep, daily summary, `grill-me` (several; one warns it treats every decision as final and makes automated runs rigid), Pocock's architecture skill, adversarial-critic loop, a skill for deleting/merging skills, GSD. One answer to "which skill?": "None. I would say gates."

"Drop your best Claude skills in here!" — r/ClaudeAI, 28d ago, 513 votes / 108 comments — POST READ
https://www.reddit.com/r/ClaudeAI/comments/1xevkyg/drop_your_best_claude_skills_in_here/
- Top comment "by a mile" (per mod-bot): a session-closure skill that logs corrections, decisions, to-dos and a session registry — with the design rule "if a closing dumps eight things on you every time, you stop using it. Ceremony kills the habit."
- Built-in `/skill-doctor` recommended to remove unused skills "you pay for on each session".
- Sales-coaching prior art: "AI Rob" (Rob Snyder's B2B founder playbooks as a skill).

"My favorite Claude skills this week" — r/claudeskills, 2d ago, 424 votes / 37 comments — POST READ
https://www.reddit.com/r/claudeskills/comments/1y0ikqe/my_favorite_claude_skills_this_week_drop_yours_in/
- Listed top 10: REA, Matt Pocock code-review, ECC, Superpowers, Impeccable, Ponytail, Design Taste Frontend, Anthropic skills, Hallmark, Cloudflare Security Audit.
- Sceptic: "I honestly don't like the idea of 'skills', it creates noise in your session… expect this to be obsoleted very soon."
- Unanswered user questions that Revive should answer for its users: "Do you keep all of these skills loaded… or selectively enable them?" and "do I need to update the skills I downloaded months ago?" (asked twice, nobody knew).

**Pattern across sections 2 and 7.** Kept: small, self-authored, procedure-encoding skills; `grill-me`-style interviewing; Ponytail; a session-end/handoff ritual; an independent reviewer. Dropped: full-process frameworks (Superpowers most of all), anything that re-teaches what the current model already does. Third-party skills are described as transient — to be re-tested at every model release.

### 7.2 "Too many skills", context bloat, bundles
- Two packs as simultaneous routers → name clashes, competing session-start hooks (2.5).
- 14 deploy plugins → 165 skills in context; advice is one platform plugin per repo, enforced in project settings (4.1).
- Heavy skills as token sinks: Cloudflare security-audit (6.1), Superpowers with subagents (2.6), Impeccable ~1.6x–5x a plain build (1.2, 1.3).
- "Loading any one of the Obra skills seems to poison the entire session's reasoning… even through completion or compaction" (2.3) — one user's claim, but it is the bundling worst case.
- Instructions get overridden: a user's own testing rules lost to the skill's TDD rules on long runs (2.3).
- Mega-pack sentiment: "Ditch the bloat, keep the essentials" (2.4 mod-bot); install counts suggest people cherry-pick single skills out of packs (5.1).
- Search listing only: "Skills list constantly repeating throughout context and triggering compaction" (r/ClaudeAI, 1mo, 3/23); "PSA: Your Claude Code plugins are probably loading every skill TWICE" (r/ClaudeAI, 9mo, 17/10); "Am I stupid for not using any skills" (r/ClaudeAI, 26d, 114/63); "68% of my Claude Code spend was a too-full context" (r/ClaudeCode, 28d, 7/8).

### 7.3 Prior art for Revive (revival / coaching to first customer)

- **`michael-ilic/solo-venturing`** — mentioned in a comment (author, edited link in) on the r/claudeskills weekly thread, 2d ago. Described as "shark tank for your app idea. Coaches you critically from idea to production app as your personal business angel… measurable results, tests" with "go, pivot, kill, park decisions". Asked whether it is tough-love: "Def not too nice." Closest thing to Revive's coaching stance found on Reddit. Not a revival tool.
- **`emotixco/claude-skills-founder`** — "13 claude code skills for the founder side of a project, and our evals say plain opus already does most of it" — r/ClaudeCode, 1mo ago, 1 vote / 5 comments — POST READ (author post)
  https://www.reddit.com/r/ClaudeCode/comments/1xcl0zp/13_claude_code_skills_for_the_founder_side_of_a/
  validate-idea, competitor-matrix, pricing-strategy, mvp-scope, landing-page, user-interviews, pitch-deck etc. Each writes to a `founder/` folder and reads earlier outputs; outside facts carry a source link or "not found"; the user's own metrics stay as `[placeholders]`. **Author's own eval with `claude plugin eval`: on Opus 5, 8 of 10 cases score the same with and without the plugin; the one clear win is updating `facts.md` when a new number contradicts a saved one.** Commenter: "The value is the state management. Prompt text is a commodity."
- **`Beakpoint-Insights/roost`** — comment (author) in the same weekly thread: takes a product idea to production — shapes the epic, builds slice by slice, reviews, QAs in a real browser, walks through rollout "one command at a time". Engineering pipeline, not customer acquisition.
- **Session continuity skills** (7.1) are the nearest thing to "revive": session-closure/registry, `/project-index` + `/project-pickup`, `context-bridge`, Pocock `/handoff`.
- **Demand evidence for the revival problem:** "I can't finish my vibe-coded projects, so I built a graveyard to bury them" — r/SideProject, 6d ago, 5 votes / 6 comments — POST READ
  https://www.reddit.com/r/SideProject/comments/1xxqq3p/i_cant_finish_my_vibecoded_projects_so_i_built_a/
  "Get a cool idea, really go deep into it and vibe code for days or sometimes weeks… and then? Nothing. My GitHub is full of projects that went exactly like this." Defines dead as 90 days without a commit. A joke product, but the framing is exactly Revive's user.
- Search listing only: "I revived my abandoned side project and rebuilt it from scratch" (r/BDDevs, 7d, 32/9); "i have 47 unfinished side projects and i finally figured out why" (r/SideProject, 19/24); "I built a Claude skill that validates startup ideas in 30 minutes" (r/ClaudeAI, 8mo, 6/2); "I used to burn a whole day validating each startup idea by hand. Built a Claude skill…" (r/claudeskills, 5mo, 25/16); "I built an open-source pack of Claude Skills that works like a GTM co-founder for technical founders" (r/ClaudeAI, 4mo, 1/2); "My Claude Code plugin has been selling my own product for 85 days. 1,097 emails, 11 human replies, 0 paid" (r/AI_Agents, 3mo, 0/18).
- **No skill or plugin for reviving an abandoned codebase and taking it to a first paid customer was found.**

### 7.4 First paying customer — what unblocked people

"My first vibe-coded app just hit 9 paying subscribers +200 on free trial after 3 weeks live" — r/vibecoding, 3mo ago, 237 votes / 49 comments — POST READ
https://www.reddit.com/r/vibecoding/comments/1vmmc3d/my_first_vibecoded_app_just_hit_9_paying/
- Productised a manual process the builder already ran (drug-testing location referral list) as a directory. Acquisition: pre-seeded 4,502 listings, cold email "claim your listing", value on day one with no credit card. A commenter hit a 500 error on first click.

"Six days ago I posted about my first customer. I have four now." — r/SideProject, 3mo ago, 67 votes / 78 comments — POST READ
https://www.reddit.com/r/SideProject/comments/1w3e8hh/six_days_ago_i_posted_about_my_first_customer_i/
- $5 product, months at $0, ~90 users, 4 paid. Channel: Reddit posts, then "ChatGPT started recommending it". Best advice in comments: write down exactly what those four customers said — "that wording is usually better landing-page copy than anything you'd invent"; ask what they were doing before they found you; Reddit-only buyers do not prove distribution.

"my first first paying customers!!!!" — r/vibecoding, 2mo ago, 112 votes / 69 comments — POST READ
https://www.reddit.com/r/vibecoding/comments/1wykdnu/my_first_first_paying_customers_thank_you/
- Two customers via Stripe after "months of work, hundreds if not thousands of $ spent on tokens". "A LOT of my traffic comes from Reddit."

"Has anyone here actually made serious money from a vibe-coded app?" — r/vibecoding, 3mo ago, 51 votes / 213 comments — POST READ (sampled)
https://www.reddit.com/r/vibecoding/comments/1vk6y8b/has_anyone_here_actually_made_serious_money_from/
- Heavy scepticism. Credible small numbers: ~$100 MRR after 3 months; ~$311 MRR with 10 subscribers (3 found via ChatGPT research, ~1000 hours, $2k+ spent); ~£200/month.
- Consistent lesson: products built to solve the builder's own real problem earn; products built "to turn a profit" crawl. "Building is easy with AI, it's actually finding clients, talking to them, and sales that takes time." "A perfectly coded app nobody needs still makes $0."
- One ex-backend engineer reports $0→$25k in 3 months by selling results to clients, with daily manual outreach (5 personal emails, ~100 automated, 5 DMs).

Search listing only: "My vibe coded app made its first $100. The customer told me ChatGPT recommended it" (r/vibecoding, 25d, 9/54); "How do you guys actually get your first users after vibe-coding an app?" (r/SaaSSales, 28d, 7/32); "after 3 year of failing I GOT a paying customer" (r/SideProject, 6mo, 19/23).

**What unblocked first payments, as stated:** an existing audience or list to email; direct outreach; a problem the builder personally had; posting where the users already are (Reddit); a working checkout (several payment-provider stories show this was the actual blocker for non-US founders, 3.2). Being surfaced by ChatGPT is mentioned in three separate stories. Nobody credits a skill.

---

## 8. Reddit vs the front-runner list

### CONFIRMS
- **Impeccable** is the most-recommended design skill by name in current threads (1.1, 1.5, 1.6, 1.7).
- **Anthropic `frontend-design`** is the safe, cheap default (1.2, 1.6).
- **Taste skill** (`design-taste-frontend`) is visible in weekly top-10s and gives a real step up in the one test read (1.4, 1.7).
- **Lemon Squeezy is shutting down** (March 2027 per sellers' notices) and sellers are actively migrating (3.1).
- **Polar** is the most common replacement choice and the closest feature match to LS (3.1).
- **`coreyhaines31/marketingskills`** dominates marketing installs, and people pick single skills from it (5.1).
- **Vercel plugin telemetry is on by default** and can be disabled with an env var (4.1).
- **Built-in `/security-review`** is considered worth running — as a floor, not a gate (6.2, 6.4).
- The common security failures are the well-known five (secrets in bundle, RLS, authz, debug routes, CORS) (6.4, 6.5).

### CONTRADICTS (or seriously weakens)
- **Superpowers `systematic-debugging` and `mattpocock` `diagnosing-bugs` as debugging front-runners.** The only head-to-head read found no uplift over a plain prompt and ~3 extra minutes per bug (2.1). Current r/ClaudeCode sentiment calls Superpowers outdated, bloated and occasionally harmful with the newest models (2.2, 2.3, 2.4, 2.6). If anything from those packs is kept, Reddit points at Superpowers `brainstorming`/`writing-plans` and Pocock `grill-me`, not the debugging skills.
- **Superpowers `verification-before-completion`** as a pre-launch check: practitioners report in-session review skills miss bugs they inspected; an independent adversarial reviewer in a fresh context is what works (2.4).
- **`cloudflare/security-audit-skill` for a solo builder on a subscription plan:** reported as unaffordable — multiple 5-hour windows for a partial run (6.1).
- **`raroque/vibe-security-skill`:** the one first-hand mention says it "won't find much" for a half-decent builder and risks false security (6.3).
- **Paddle and Dodo as safe choices:** multiple accounts of approval followed by sudden offboarding, and for Dodo a 120-day hold ending in full retention of funds (3.3).
- **Polar as a low-risk default outside the US/EU:** auto-rejection (Morocco), identity verification failure (UK), payouts stuck in review for 2 months, hosted-checkout errors, slow support (3.2, 3.3). Positive reports outnumber these but are one-liners.
- **Creem:** reported invite-only for at least one non-Western applicant; otherwise almost invisible on Reddit (3.2).
- **Impeccable as a lightweight install:** reported 4 agents, 3 hooks, a home-directory folder and telemetry on by default; 1.6x–5x cost of a plain build; one user finds output still generic (1.1, 1.2, 1.3). Its `critique` command is the part singled out as valuable.
- **Bundling many third-party skills at all:** the strongest cross-thread message is that large generic packs are a liability and that skills must be re-validated at each model release (2.4, 7.1, 7.2).

### ADDS
- **Design:** Hallmark (`nutlope/hallmark`) as a build-side alternative with ~90-token idle cost; `emilkowalski/skills` for motion; `vercel-labs/agent-skills` `web-design-guidelines` as an audit pass; "reference screenshots + a brief" beats skill choice.
- **Unstuck / process:** Ponytail (most cross-thread mentions of any skill not on our list); Pocock `grill-me`, `handoff`, `wayfinder`; GSD; an independent red-team reviewer agent; mutation testing to prune AI-written tests.
- **Payments:** Stripe Managed Payments (Stripe's own MoR, the official LS migration path; no licence keys; not all countries); Freemius (best-reported option for individuals with no company and for "unlisted" countries); FastSpring. Process advice: test provider support before committing, expect the first payout to be the real test, export customer data before any shutdown.
- **Deploy:** Railway plugin's auto-approve hook is a bigger risk than Vercel's telemetry; enable one deploy plugin per repo; Cloudflare Pages/Workers is the most-named free host among non-technical builders.
- **Copy:** a personal voice profile beats a generic humanizer; reuse the first customers' own words as landing copy.
- **Pre-launch:** a 30-minute manual checklist (two-account ID swap, bundle key search, gitleaks on history, unauthenticated `curl`, spend caps, RLS) is what people actually run; cross-vendor model review; split security review by area.
- **Prior art:** `michael-ilic/solo-venturing`, `emotixco/claude-skills-founder`, `Beakpoint-Insights/roost`. The founder-skills author's own eval (8/10 cases no better than plain Opus; the win is persisted state) is the most directly relevant design lesson for Revive: the durable value is the saved project state and the routing/gating, not the prompt text.
- **Unanswered by Reddit:** Korea-based sellers; `whawkinsiv/solo-founder-skills`; `addyosmani/agent-skills` usage reports; `ui-ux-pro-max` in 2026; `deploy-to-vercel` skill specifically.
