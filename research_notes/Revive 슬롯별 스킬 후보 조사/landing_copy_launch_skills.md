# Landing page, copywriting and launch-marketing skills for the Revive "first paid customer" slot (state as of 2026-11-22)

Method notes for the report writer:

- All repo facts (stars, licence, last commit, file layout, SKILL.md contents) were read from the GitHub API on 2026-11-22. Star counts are a snapshot of that day.
- Social evidence is marked **READ DIRECTLY** (I opened the page or API record) or **SEARCH SNIPPET ONLY** (seen only in a search-engine summary; not opened).
- Reddit could not be read at all (see Gaps in the social-evidence question). X returned HTTP 402. No Threads post surfaced in any search. This is the weakest part of these notes.

## Key Question 1: Which marketing/copywriting skills do real users recommend, and which individual skills matter for a first-payment goal?

### Takeaway
`coreyhaines31/marketingskills` is the only marketing pack with broad, repeated third-party recommendation, and about 8 of its 53 skills map to the first-payment scope. The best scope fit is a much smaller pack, `whawkinsiv/solo-founder-skills`, which is written for exactly "first 10 paying customers" but has almost no independent social proof.

### Cited Findings

**coreyhaines31/marketingskills (the dominant pack)**

- 61,910 stars, 9,034 forks, MIT, not archived, last push 2026-11-20, 53 skill folders, release v2.14.25 on 2026-11-20 — [GitHub repo](https://github.com/coreyhaines31/marketingskills)
- Skills present on 2026-11-22: ab-testing, ad-creative, ads, ai-seo, analytics, aso, attribution, churn-prevention, co-marketing, cold-email, community-marketing, competitor-profiling, competitors, content-strategy, conversion-tracking, copy-editing, copywriting, cro, customer-research, directory-submissions, emails, events, free-tools, image, influencer-marketing, launch, lead-magnets, link-building, marketing-council, marketing-ideas, marketing-loops, marketing-plan, marketing-psychology, offers, onboarding, paywalls, popups, pricing, product-marketing, programmatic-seo, prospecting, public-relations, referrals, reverse-engineer-marketing, revops, sales-enablement, schema, seo-audit, signup, site-architecture, sms, social, video — [skills directory](https://github.com/coreyhaines31/marketingskills/tree/main/skills)
- Names changed in v2.0: 17 skills were renamed and `page-cro` + `form-cro` were merged into `cro`. The names in the brief map as follows: `page-cro` → `cro`, `pricing-strategy` → `pricing`, `launch-strategy` → `launch`, `product-marketing-context` → `product-marketing` — [README](https://github.com/coreyhaines31/marketingskills/blob/main/README.md)
- Skills relevant to first payment, with what the SKILL.md actually contains:
  - `copywriting` (343 lines): homepage, landing, pricing and feature page copy; a hero built as "current discomfort → better vision → path to action"; an AI-tells blacklist and self-check in `references/ai-tells.md` — [copywriting/SKILL.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/copywriting/SKILL.md)
  - `pricing` (295 lines): has an "Initial Pricing — Pick a Price You Can Learn From" section with a $10/$100/$1,000 rule of thumb and a warning against "the $9 trap". The rest (value metrics, tiers, Van Westendorp, when to raise prices, pricing-page teardown) is for optimising an existing price — [pricing/SKILL.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/pricing/SKILL.md)
  - `launch` (385 lines): ORB (owned/rented/borrowed channels) framework, a readiness gate based on "Simple, Lovable, Complete", a five-phase launch (internal → alpha → beta → early access → full), a Product Hunt section, post-launch and ongoing-announcement sections — [launch/SKILL.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/launch/SKILL.md)
  - `cold-email` (215 lines + 10 reference files): frameworks, personalisation, follow-ups, deliverability, LinkedIn outreach, EU/UK consent rules — [cold-email/SKILL.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/cold-email/SKILL.md)
  - `prospecting` (277 lines): has a "Demand-signal" branch explicitly for "your first customers, design partners, or beta users", detailed in `references/demand-signals.md` (aim: "your first ten real conversations"; 10 evidence-backed matches over a long list) — [prospecting/SKILL.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/prospecting/SKILL.md), [demand-signals.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/prospecting/references/demand-signals.md)
  - `offers` (155 lines + 8 references): value equation, guarantees, real vs fake scarcity, and a warning against discounting to acquire customers — [offers/SKILL.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/offers/SKILL.md)
  - `product-marketing` (320 lines): creates `.agents/product-marketing.md` (product, ICP, positioning, competitors, customer language, brand voice) that every other skill reads — [product-marketing/SKILL.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/product-marketing/SKILL.md)
  - `directory-submissions` (439 lines): Product Hunt, G2, Capterra, AlternativeTo, MCP registries, a listing kit and a tracker CSV — [directory-submissions/SKILL.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/directory-submissions/SKILL.md)
  - `customer-research` (308 lines): interviews, surveys, JTBD, mining Reddit and reviews — [customer-research/SKILL.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/customer-research/SKILL.md)
  - `cro` (198 lines) and `copy-editing` (491 lines) are optimisation and editing passes — [cro/SKILL.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/cro/SKILL.md), [copy-editing/SKILL.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/copy-editing/SKILL.md)
- `community-marketing` is about building and running your own community (Discord, Slack, forums), not about finding first customers in existing communities — [community-marketing/SKILL.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/community-marketing/SKILL.md)
- `social` covers LinkedIn, X, Instagram, TikTok and Facebook — [social/SKILL.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/social/SKILL.md)
- The directory catalogue contains no Korean entries (grep for Korea/한국/Disquiet/Naver/Kakao/GeekNews returned nothing) — [directory-list.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/directory-submissions/references/directory-list.md)

**whawkinsiv/solo-founder-skills (best scope fit, low adoption)**

- 269 stars, 45 forks, MIT ("Copyright (c) 2025 Will Hawkins"), created 2026-01-13, last commit 2026-10-16, 76 commits. The older names `whawkinsiv/claude-code-skills` and `whawkinsiv/solo-founder-superpowers` seen in directories now redirect to this repo — [GitHub repo](https://github.com/whawkinsiv/solo-founder-skills)
- 21 skills: about-me, beautify, build, content, domain-name, email, finances, first-customers, focus, go-live, humanize, is-this-an-app, journey, landing-page, legal, payments, pricing, retention, secure, seo, validate — [skills directory](https://github.com/whawkinsiv/solo-founder-skills/tree/main/skills)
- `landing-page` (62 lines): "Early on, its job is to get a stranger to pay, pre-order, or book a call"; one offer, one price, one action; uses the customer's words and only real proof; tells the model to run `humanize` on the final copy — [landing-page/SKILL.md](https://github.com/whawkinsiv/solo-founder-skills/blob/main/skills/landing-page/SKILL.md)
- `first-customers` (79 lines): first 10 paying customers by hand, in the order people you know → communities you belong to → strangers with a pain signal; a prospect sheet with a "pain signal" column; problem-first messages under 150 words; three follow-ups then stop; a launch only after the first 10 — [first-customers/SKILL.md](https://github.com/whawkinsiv/solo-founder-skills/blob/main/skills/first-customers/SKILL.md)
- `pricing` (63 lines): "Before 10 paying customers it sets one simple price and works out how many customers the founder needs. After 10 it designs tiers" — [pricing/SKILL.md](https://github.com/whawkinsiv/solo-founder-skills/blob/main/skills/pricing/SKILL.md)
- `humanize` (138 lines): 35 AI-writing patterns, English — [humanize/SKILL.md](https://github.com/whawkinsiv/solo-founder-skills/blob/main/skills/humanize/SKILL.md)

**blader/humanizer (anti-AI-tone, English)**

- 72,039 stars, 5,640 forks, MIT ("Copyright (c) 2025 Siqi Chen"), last commit 2026-11-19; checks 26 patterns — [GitHub repo](https://github.com/blader/humanizer)
- Independent recommendations exist (see Key Question 4): Tony Lee's "4 that survived" list, Frank Andrade's newsletter, and several Hacker News comments.

**Other packs that surfaced (lower priority)**

- `anthropics/knowledge-work-plugins`: 36,658 stars, Apache-2.0, last commit 2026-11-19. Marketing plugin skills: brand-review, campaign-plan, competitive-brief, content-creation, draft-content, email-sequence, performance-report, seo-audit. Sales plugin has draft-outreach. Oriented to teams in Claude Cowork, and the marketing plugin ships a `.mcp.json` and CONNECTORS.md — [GitHub repo](https://github.com/anthropics/knowledge-work-plugins)
- `alirezarezvani/claude-skills`: 30,257 stars, MIT, last push 2026-11-21, 410+ skills across all domains — [GitHub repo](https://github.com/alirezarezvani/claude-skills)
- `kostja94/marketing-skills`: 1,129 stars, MIT, last push 2026-11-06, 160+ skills weighted to SEO and paid ads — [GitHub repo](https://github.com/kostja94/marketing-skills)
- `zubair-trabzada/ai-marketing-claude`: 2,938 stars, MIT, last push 2026-03-02 (stale for 8+ months) — [GitHub repo](https://github.com/zubair-trabzada/ai-marketing-claude)
- `BrianRWagner/ai-marketing-claude-code-skills`: 461 stars, MIT, last commit 2026-11-14; includes cold-outreach-sequence, homepage-audit, positioning-basics, brand-voice-extractor — [GitHub repo](https://github.com/BrianRWagner/ai-marketing-claude-code-skills)
- `ognjengt/founder-skills`: 695 stars, MIT, last commit 2026-05-18 — [GitHub repo](https://github.com/ognjengt/founder-skills)
- `OneWave-AI/claude-skills` (includes a landing-page-copywriter skill per a search summary): 440 stars, MIT, last push 2026-10-20 — [GitHub repo](https://github.com/OneWave-AI/claude-skills)

### Inferences
- Popularity and scope fit point in different directions. marketingskills has the recommendations and the maintenance (daily releases, ~90 contributors), but it is written for "technical marketers and founders" across the whole funnel. solo-founder-skills is written for the pre-revenue founder and stops at roughly the right place, but 269 stars and one author make it a maintenance risk.
- A reasonable bundle is a hand-picked subset of marketingskills (`product-marketing`, `copywriting`, `pricing`, `offers`, `launch`, `prospecting` with its demand-signals reference, `cold-email`, `directory-submissions`), with solo-founder-skills' `landing-page`, `first-customers` and `pricing` as the alternate or as the model for Revive's own thinner wrappers. Both are MIT, so mixing is legally possible.
- Nothing found covers Korean launch channels or Korean community posting. That part will have to be written inside Revive.
- No dedicated, well-adopted "Product Hunt launch" or "Reddit launch post" skill surfaced. Product Hunt is covered only as a section inside marketingskills' `launch` and `directory-submissions`.

### Gaps
- I did not test any skill's output quality. All quality statements here come from reading SKILL.md files or from third parties.
- Composio's "Top 29 marketing skills" and Snyk's "Top 8 skills for founders" lists appeared in search but were not opened; they are vendor blogs, so I did not use them as evidence — [Composio](https://composio.dev/content/best-marketing-skills), [Snyk](https://snyk.io/articles/top-8-claude-skills-entrepreneurs-startup-founders-solopreneurs/)
- Install counts quoted by directories (for example "6.2M skills.sh installs") are third-party figures and NOT VERIFIED.

## Key Question 2: Are there Korean-language writing or de-AI-ifying skills that Korean users recommend? Canonical repo and licence?

### Takeaway
Yes, several, all MIT. The de facto Korean standard is `epoko77-ai/im-not-ai` (6,707 stars); the repo literally named `humanizer-kr` is `hjongc/humanizer-kr` (27 stars), which is lighter and genre-aware but barely adopted.

### Cited Findings

| Repo | Stars | Licence (from LICENSE file) | Last commit | Install | Dependencies |
|---|---|---|---|---|---|
| [epoko77-ai/im-not-ai](https://github.com/epoko77-ai/im-not-ai) (plugin name `humanize-korean`, v2.4.7) | 6,707 (735 forks) | MIT, "Copyright (c) 2026 epoko77-ai" | 2026-11-17 | `/plugin marketplace add epoko77-ai/im-not-ai` then `/plugin install humanize-korean@im-not-ai`; or clone + `install.sh` | python3 scripts for metrics (degrades gracefully if they fail), and sub-agents called through the Agent tool on standard/heavy routes. No API keys |
| [NomaDamas/k-skill](https://github.com/NomaDamas/k-skill) → `korean-humanizer` | 8,488 for the whole Korean-skills collection (1,019 forks) | MIT | 2026-11-16 | part of the k-skill collection and its CLI | None: "추가 설치·API 키 없음 … 외부 호출이나 스크립트가 없다" |
| [hjongc/humanizer-kr](https://github.com/hjongc/humanizer-kr) | 27 | MIT, "Copyright (c) 2026 humanizer-kr contributors" | 2026-11-19 | `claude plugin marketplace add https://github.com/hjongc/humanizer-kr.git` then `claude plugin install humanizer-kr@humanizer-kr-marketplace` | Optional python3 audit script. No API keys |
| [IsaacEryn/humanizer-ko](https://github.com/IsaacEryn/humanizer-ko) | 49 | MIT | 2026-10-21 | NOT VERIFIED | NOT VERIFIED |
| [DaleSeo/korean-skills](https://github.com/DaleSeo/korean-skills) → `humanizer` | 291 | MIT | 2026-05-05 (stale 6+ months) | `npx skills add daleseo/korean-skills@humanizer` (per skills.sh listing) | NOT VERIFIED |
| [monologg/humanizer-kr](https://github.com/monologg/humanizer-kr) | 4 | MIT | 2026-03-21 | NOT VERIFIED | NOT VERIFIED |

- im-not-ai rewrites Korean AI text "사실 · 주장 · 수치는 바꾸지 않고", using 10 categories × 85 sub-patterns graded S1/S2/S3, plus a v2.4 vocabulary layer of 111 translation-born words chosen by blind evaluation. It supports Claude Code, Copilot CLI, Codex CLI and Gemini CLI — [im-not-ai README](https://github.com/epoko77-ai/im-not-ai/blob/main/README.md)
- im-not-ai's skill folder contains three skills (`humanize-korean`, `humanize-redo`, `humanize-scan`), nine agent definitions, and reference files including `metrics.py`, `lexicon.json` and a taxonomy — [im-not-ai skills tree](https://github.com/epoko77-ai/im-not-ai/tree/main/skills)
- k-skill's `korean-humanizer` states that its v2 was rebuilt around im-not-ai's methodology, has a change-rate guard (warn at 30%, stop at 50%), and can rewrite in the user's voice from a sample — [korean-humanizer.md](https://raw.githubusercontent.com/NomaDamas/k-skill/main/docs/features/korean-humanizer.md)
- hjongc/humanizer-kr is genre-aware (product copy, public notice, email, essay, documentation, proposal, social post, spoken script), builds a saved voice profile (`voice.md`), has commands `analyze`, `feedback`, `rewrite`, `write`, and ships before/after examples for product copy and social posts. Its rules cite 법제처 「알기 쉬운 법령 정비기준」 and 국립국어원 public-language guides, and it credits blader/humanizer for README structure. One contributor, 38 commits, created 2026-06-30 — [humanizer-kr README](https://github.com/hjongc/humanizer-kr/blob/main/README.md), [SKILL.md](https://github.com/hjongc/humanizer-kr/blob/main/skills/humanizer-kr/SKILL.md)
- hjongc/humanizer-kr's own README says its voice-matching quality is not validated ("문체 재현 품질이 검증됐다는 뜻은 아니며") — [humanizer-kr README](https://github.com/hjongc/humanizer-kr/blob/main/README.md)
- An "awesome" list of humanizer skills also lists `leeandev/stop-slop-ko` (84 stars), `evergreentree97/K-Humanizer` (23) and `dotoridot/korean-humanizer` (19); those three were NOT VERIFIED against their repos — [zhuyansen/awesome-humanizer-skills](https://github.com/zhuyansen/awesome-humanizer-skills)
- Korean third-party coverage of im-not-ai: a PyTorchKR community post by 9bow dated 2026-06-27 (2 likes, no comments, flagged as GPT-summarised) describes it neutrally and notes the full multi-agent pipeline is Claude Code only. READ DIRECTLY — [PyTorchKR](https://discuss.pytorch.kr/t/im-not-ai-ai-claude-code/10666)
- A Korean news article reports im-not-ai passing 6,000 GitHub stars. SEARCH SNIPPET ONLY — [koreancenter.or.kr](https://www.koreancenter.or.kr/news/articleView.html?idxno=1431238)
- A user-filed issue on 2026-04-25 said the one inconvenience after using im-not-ai was the lack of a slash command (since added; issue closed with 5 comments). Another issue the same day asked for a licence to be added (closed; LICENSE now present). READ DIRECTLY (issue list via API) — [issue #6](https://github.com/epoko77-ai/im-not-ai/issues/6), [issue #5](https://github.com/epoko77-ai/im-not-ai/issues/5)
- blader/humanizer is described by a reviewer as tuned for English. READ DIRECTLY — [tonylee.im, 2026-02-08](https://tonylee.im/en/blog/claude-code-skills-that-survived/)

### Inferences
- "humanizer-kr" as a name most plausibly means hjongc/humanizer-kr (the most-starred repo with that exact name). It is not what Korean users broadly recommend; im-not-ai is.
- For bundling, the trade-off is weight versus adoption. im-not-ai has the adoption and maintenance but brings python scripts, nine agents and a workspace directory. k-skill's `korean-humanizer` is prompt-only and derived from the same method, so it is the easiest to vendor. hjongc/humanizer-kr is the only one with explicit product-copy and social-post genres and a voice profile, which fits landing and launch copy, but it has a bus factor of one.
- All three are MIT, so any of them can be redistributed with the copyright and licence notice kept.
- These tools clean up Korean text; none of them writes Korean marketing copy from a positioning brief. Korean landing-copy generation would still come from an English-language copywriting skill plus a Korean clean-up pass, or from Revive's own prompt.

### Gaps
- No Korean user review comparing these tools on real copy was found. The search summaries explicitly reported finding introductions and install guides rather than usage reviews.
- No Threads post about any Korean humanizer surfaced, despite two targeted searches.
- I did not verify whether k-skill's `korean-humanizer` folder can be installed alone without the k-skill CLI.

## Key Question 3: Are there skills for demand validation to learn from and credit?

### Takeaway
There is good material but no single adopted standard. The most reusable sources are MIT-licensed (`whawkinsiv` validate, marketingskills customer-research and demand-signals, `phuryn/pm-skills` discovery skills); the best-known one, `slavingia/skills`, has no licence file and can only be learned from.

### Cited Findings
- `slavingia/skills` (The Minimalist Entrepreneur): 11,197 stars, 1,126 forks, last commit 2026-04-14. **No LICENSE file exists**; the repo root contains only `.claude-plugin`, `README.md` and `skills`. Ten skills: company-values, find-community, first-customers, grow-sustainably, marketing-plan, minimalist-review, mvp, pricing, processize, validate-idea. Install: `/plugin marketplace add slavingia/skills` then `/plugin install minimalist-entrepreneur` — [GitHub repo](https://github.com/slavingia/skills)
- `whawkinsiv/solo-founder-skills` `validate` (119 lines, MIT): "Designs the cheapest test, scores the evidence with a script, and returns a dated verdict"; covers concierge MVP and go/no-go. References: `experiments.md`, `interview-guide.md`, `pressure-test-questions.md`, `scorecard.md`, plus `scripts/score.py` — [validate skill](https://github.com/whawkinsiv/solo-founder-skills/tree/main/skills/validate)
- marketingskills `customer-research` has `references/interviews-and-surveys.md` (PMF survey, 5-why laddering, outreach templates, incentives, a confirmation-bias guardrail) and `references/source-guides.md` (per-platform mining playbooks) — [customer-research](https://github.com/coreyhaines31/marketingskills/tree/main/skills/customer-research)
- marketingskills `prospecting/references/demand-signals.md` requires a cited pain, need or timing signal for every prospect ("Evidence is the entry ticket") and credits its pattern to the open-source `first-customer-finder` Codex skill by Kappaemme (MIT, per that file; NOT VERIFIED at the source repo) — [demand-signals.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/prospecting/references/demand-signals.md)
- `phuryn/pm-skills`: 28,210 stars, MIT ("Copyright (c) 2026 Pawel Huryn"), last commit 2026-11-08. Relevant skills: `interview-script`, `summarize-interview`, `identify-assumptions-new`, `prioritize-assumptions`, `brainstorm-experiments-new` (pm-product-discovery); `beachhead-segment`, `ideal-customer-profile` (pm-go-to-market); `positioning-ideas`, `value-prop-statements` (pm-marketing-growth); `competitor-analysis` (pm-market-research) — [GitHub repo](https://github.com/phuryn/pm-skills)
- `garrytan/gstack` `office-hours`: repo has 142,296 stars, MIT ("Copyright (c) 2026 Garry Tan"), last commit 2026-11-22. The skill is described as "YC Office Hours — two modes. Use for: brainstorm this, is this worth building." Its SKILL.md is 672 lines and mentions "gstack" 70 times — [office-hours/SKILL.md](https://github.com/garrytan/gstack/blob/main/office-hours/SKILL.md)
- `NadavGrossman/the-mom-test-skills`: 1 star, MIT, last commit 2026-10-21. Three skills (prepare interviews, analyze interviews, choose the next experiment) based on the book *The Mom Test*; includes with-skill and without-skill eval outputs; install `npx skills add NadavGrossman/the-mom-test-skills --agent claude-code --yes` — [GitHub repo](https://github.com/NadavGrossman/the-mom-test-skills)
- `deanpeters/Product-Manager-Skills`: 8,116 stars, last commit 2026-11-13, licensed **CC BY-NC-SA 4.0**. Its LICENSING.md says selling the skills or repackaging them into a paid product needs written permission — [LICENSING.md](https://github.com/deanpeters/Product-Manager-Skills/blob/main/LICENSING.md)
- A GitHub search for "customer interview skill claude", "idea validation skill claude code", "product hunt launch skill claude", "cold email skill claude" and "landing page skill claude" returned nothing with meaningful stars (best hit: `ThunderShadows/validate-idea`, 1 star, no licence) — [GitHub search](https://github.com/search?q=idea+validation+skill+claude+code&type=repositories)

### Inferences
- Since Revive keeps validation logic in-house, the practical question is what can be credited and adapted. MIT sources (whawkinsiv, marketingskills, pm-skills, gstack, the-mom-test-skills) can be adapted with attribution. slavingia/skills has no licence, so default copyright applies and its text should not be copied; it is also a derivative of a commercial book.
- deanpeters' pack is share-alike and non-commercial, so adapting it would constrain Revive's own licence. Treat it as reading material only.
- gstack's `office-hours` is tightly coupled to gstack's own runtime (preamble, binaries), judging by 70 self-references in one file. It is a model for question design, not something to lift.
- Book-derived skills (Mom Test, Minimalist Entrepreneur) carry a second copyright layer beyond the repo licence. Crediting the books and writing original prompts is the safer path.
- I found no skill that implements a fake-door or pre-sale test end to end (page + payment link + threshold). whawkinsiv's `validate` and `landing-page` (which names "pre-order" as a valid action) come closest.

### Gaps
- I did not read the full bodies of slavingia's `validate-idea`, pm-skills' `interview-script` or gstack's `office-hours`, so I cannot rank their question quality.
- No user reports of any validation skill changing a build/no-build decision were found.

## Key Question 4: What do people on Reddit, X, Threads and YouTube actually say?

### Takeaway
Independent, first-hand evidence is thin. What exists is positive for marketingskills and blader/humanizer but comes mostly from bloggers and newsletter authors; I found no first-hand account of anyone getting a first paying customer using these skills, and could not read Reddit, X or Threads at all.

### Cited Findings

**Independent or mostly independent (READ DIRECTLY)**

- Keanan Koppenhaver, claudecodeformarketers.com, 2026-05-27: calls marketingskills "the best single collection built for marketers" and the `copywriting` + `copy-editing` pair "opinionated in a good way". States no drawbacks. He promotes his own skills and a free email course; no affiliation with Haines is disclosed — [article](https://claudecodeformarketers.com/blog/claude-code-skills-for-marketers/)
- Furkan Aktaş, missiongrowth.io, 2026-10-15: lists marketingskills first for solo founders and technical marketers. Cons he names: installing all 50 skills adds every name and description to the skill listing; upgrading from v1 leaves stale folders; the CLI wrappers need your own vendor API keys. Advice: write the product-marketing context file first, then install only "the handful you repeat" by name (he names cro, seo-audit, cold-email). Published by his own company; no prices or affiliate links on the page — [article](https://missiongrowth.io/blog/claude-skills-for-marketing)
- Tony Lee, tonylee.im, 2026-02-08 (updated 2026-02-18): of the skills he installed, "About 90% of those skills sat unused after the first day". blader/humanizer is one of four that survived; he notes it is tuned for English. Does not mention marketing packs — [article](https://tonylee.im/en/blog/claude-code-skills-that-survived/)
- Frank Andrade, Artificial Corner newsletter, 2026-11-01: recommends "Humanizer if your writing sounds like AI", suggests it for a cold email, LinkedIn post or website copy, and says it cannot "make the text sound like you". Newsletter with a paywall and self-promotion — [article](https://artificialcorner.com/p/viral-claude-skills)
- Hacker News, user jamesponddotco, 2026-10-19: built personal voice skills from his own writing and incorporated the humanizer skill; "Worked like a charm" — [HN comment](https://news.ycombinator.com/item?id=50153144)
- Hacker News, user anentropic, 2026-11-17: tells another user "you don't have to do it by hand", recommending blader/humanizer or etodanik/deslop — [HN comment](https://news.ycombinator.com/item?id=50535873)
- Hacker News, user Dodaios, 2026-11-10 (author of a derivative tool): "It removes AI tics and makes text clearer. It does not add a voice, and it does not try to fool a detector" — [HN comment](https://news.ycombinator.com/item?id=50437257)
- Hacker News submissions of marketingskills got almost no traction: "Marketing Skills for Claude Code" (2026-01-22, 1 point), "Claude Code Skills for Marketing" (2026-01-27, 1 point), "Show HN: AI Marketing Skills for Claude Code" (2026-02-25, 4 points) — [HN item 46720299](https://news.ycombinator.com/item?id=46720299), [HN item 46780666](https://news.ycombinator.com/item?id=46780666), [HN item 47154377](https://news.ycombinator.com/item?id=47154377)
- slavingia/skills on Hacker News: the author's own submission on 2026-03-24 got 1 point — [HN item 47502073](https://news.ycombinator.com/item?id=47502073)
- PyTorchKR post on im-not-ai, 2026-06-27: neutral third-party introduction, 2 likes, no comments — [PyTorchKR](https://discuss.pytorch.kr/t/im-not-ai-ai-claude-code/10666)

**Author self-promotion (do not count as user recommendation)**

- Corey Haines's X posts announce each skill ("This might be the most valuable thing I've ever released", `/copywriting`, `/product-marketing-context`, `/marketing-ideas`, v1.5.0 with `/customer-research`). SEARCH SNIPPET ONLY; X returned HTTP 402 when opened — [X post](https://x.com/coreyhainesco/status/2013272998191812906), [X post](https://x.com/coreyhainesco/status/2035847250761666944), [X post](https://x.com/coreyhainesco/status/2038624102156783922)
- YouTube and podcast coverage of marketingskills that surfaced consists of Haines appearing as a guest or presenter (Exit Five podcast, Growth Boss, a Flint webinar in May 2026, a TripleDart session). SEARCH SNIPPET ONLY — [Exit Five](https://exitfive.com/?p=273), [Flint webinar](https://www.flint.com/webinar/may-2026-claude-code-marketing-skills), [TripleDart](https://www.tripledart.com/playbooks/corey-haines-claude-skills-marketing)
- dev.to "10 Claude Code Skills I Wish I Had When I Launched My First Product" (Nex Tools, April 2026) names no repos and sells its own $39 and $69 skill bundles; zero comments. READ DIRECTLY; discard as evidence — [dev.to](https://dev.to/nextools/10-claude-code-skills-i-wish-i-had-when-i-launched-my-first-product-272f)

**Critical or cautionary (weak sourcing)**

- A search summary reported a reply under one of Haines's posts saying the skills have little practical value and are mostly basic instructions Claude Code wrote itself and refined in a few prompts. SEARCH SNIPPET ONLY; author and date unknown; I could not open the thread — [X post](https://x.com/coreyhainesco/status/2013272998191812906)
- claudefa.st, a vendor selling a competing kit, says founders who install packs like marketingskills find the skills disagree on positioning and copy voice and must bring their own strategy. SEARCH SNIPPET ONLY; competitor marketing — [claudefa.st](https://claudefa.st/blog/tools/skills/claude-code-marketing-skills)
- A Joao Queiros write-up of a Haines demo notes it shows work in progress, not independently verified acquisition results. SEARCH SNIPPET ONLY — [article](https://www.ai.joaoqueiros.com/blog/corey-haines-claude-marketing-skills-seo-email-analytics)
- A Skool community post about the library has 16 comments and its author mentions planning to audit the skills after installing. SEARCH SNIPPET ONLY — [Skool](https://www.skool.com/ai-marketing-insiders/marketing-skills-library-for-claude-code)

**Korean-language**

- A Korean wikidocs guidebook ("클로드 스킬 코덱스 스킬 추천 모음 57선") lists humanizer with marketers, writers and 1인 사업자 as the audience. SEARCH SNIPPET ONLY — [wikidocs](https://wikidocs.net/446636)
- A GeekNews "Ask GN" thread from 2026-02-24 asks where Korean Claude Code users share information; the one reply points to the official Discord's Korean channel. It mentions no marketing or humanizer skill. READ DIRECTLY — [GeekNews](https://news.hada.io/topic?id=26955)

### Inferences
- marketingskills' reputation rests on star count, the author's distribution, and roundup articles. That is real adoption signal, but it is not the same as users reporting results. Nobody I could read claims a first customer came from it.
- blader/humanizer has the most genuine, unprompted user endorsement of anything in this slot. The consistent caveat is that it removes tells but does not supply a voice.
- The pattern "install the pack, use a handful" appears in two independent sources (Tony Lee's 90% unused; Mission Growth's install-by-name advice). That supports bundling a small subset rather than a whole pack.

### Gaps
- **Reddit: not read.** The search tool refuses the reddit.com domain, Reddit's JSON endpoint returned no data, and a retry with a browser user-agent was blocked by the session's permission system (I did not work around it). Four general searches surfaced zero Reddit threads. Claims about r/ClaudeAI, r/ClaudeCode, r/vibecoding, r/SaaS, r/indiehackers or r/Entrepreneur sentiment are therefore NOT VERIFIED.
- **Threads: nothing found**, in Korean or English, across three targeted searches.
- **X: not readable** (HTTP 402). Everything from X is snippet-level.
- **Indie Hackers:** the post "I tested 200 Claude Code skills … the 20 that actually changed how I work" returned HTTP 403; its content is NOT VERIFIED — [Indie Hackers](https://www.indiehackers.com/post/i-tested-200-claude-code-skills-so-you-dont-have-to-here-are-the-20-that-actually-changed-how-i-work-b383a23ce3)
- No independent YouTube review or ranking video was opened or confirmed.
- If the owner can open Reddit and Threads in a normal browser, searching the repo names there would close the biggest hole in these notes.

## Key Question 5: Verified repo facts for each candidate (licence, maintenance, install, dependencies, redistribution)

### Takeaway
Every serious candidate except `slavingia/skills` (no licence) and `deanpeters/Product-Manager-Skills` (CC BY-NC-SA) is MIT or Apache-2.0 and can be redistributed inside another plugin if the copyright and licence notices are kept.

### Cited Findings

| Candidate | Author | Licence file | Stars | Last commit | Install | Dependencies | Redistribution inside Revive |
|---|---|---|---|---|---|---|---|
| [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills) | Corey Haines | LICENSE: MIT, "Copyright (c) 2025 Corey Haines" | 61,910 | 2026-11-20 | `npx skills add coreyhaines31/marketingskills [--skill a b]`; or `/plugin marketplace add coreyhaines31/marketingskills` + `/plugin install marketing-skills`; Codex plugin; SkillKit | Core skills are markdown + references. Optional `tools/` (CLIs, Composio, vendor integrations) need the user's own API keys. demand-signals reference mentions Firecrawl, Exa, last30days, social-fetch as optional tooling | Yes (MIT; keep notice) |
| [whawkinsiv/solo-founder-skills](https://github.com/whawkinsiv/solo-founder-skills) | Will Hawkins | LICENSE: MIT, "Copyright (c) 2025 Will Hawkins" | 269 | 2026-10-16 | `/plugin marketplace add whawkinsiv/solo-founder-skills` + `/plugin install solo-founder@solo-founder-skills-marketplace` | `validate` uses a python script (`scripts/score.py`); skills read an optional `ABOUT-ME.md` | Yes (MIT) |
| [blader/humanizer](https://github.com/blader/humanizer) | Siqi Chen | LICENSE: MIT, "Copyright (c) 2025 Siqi Chen" | 72,039 | 2026-11-19 | `/plugin marketplace add blader/humanizer` + `/plugin install humanizer@humanizer` (needs Claude Code 2.1.142+); or `npx skills add blader/humanizer --global --agent claude-code` | None seen in README; single root SKILL.md | Yes (MIT) |
| [epoko77-ai/im-not-ai](https://github.com/epoko77-ai/im-not-ai) | epoko77-ai | LICENSE: MIT, "Copyright (c) 2026 epoko77-ai" | 6,707 | 2026-11-17 | plugin marketplace, or clone + `install.sh` | python3; Agent tool sub-agents; writes a `_workspace/` run directory | Yes (MIT) |
| [NomaDamas/k-skill](https://github.com/NomaDamas/k-skill) (`korean-humanizer`) | NomaDamas | LICENSE: MIT | 8,488 | 2026-11-16 | k-skill plugin/CLI | None for this skill | Yes (MIT) |
| [hjongc/humanizer-kr](https://github.com/hjongc/humanizer-kr) | hjongc ("humanizer-kr contributors") | LICENSE: MIT | 27 | 2026-11-19 | plugin marketplace (Claude Code and Codex) | Optional python3 audit script | Yes (MIT) |
| [slavingia/skills](https://github.com/slavingia/skills) | Sahil Lavingia | **NO LICENSE FILE** | 11,197 | 2026-04-14 | `/plugin marketplace add slavingia/skills` + `/plugin install minimalist-entrepreneur` | None seen | **No.** Without a licence, default copyright applies |
| [phuryn/pm-skills](https://github.com/phuryn/pm-skills) | Pawel Huryn | LICENSE: MIT, "Copyright (c) 2026 Pawel Huryn" | 28,210 | 2026-11-08 | Claude Code plugin marketplace (multiple plugins: pm-product-discovery, pm-go-to-market, …) | NOT VERIFIED | Yes (MIT) |
| [garrytan/gstack](https://github.com/garrytan/gstack) (`office-hours`) | Garry Tan | LICENSE: MIT; also NOTICE.md and a `licenses/` folder | 142,296 | 2026-11-22 | gstack's own installer | Coupled to gstack runtime (bun, bin scripts, preamble) | Legally yes (MIT), practically hard to extract |
| [anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins) | Anthropic | LICENSE: Apache-2.0 | 36,658 | 2026-11-19 | Claude plugin marketplace | Marketing plugin ships `.mcp.json` connectors | Yes (Apache-2.0; keep licence and notices, state changes) |
| [deanpeters/Product-Manager-Skills](https://github.com/deanpeters/Product-Manager-Skills) | Dean Peters | LICENSE: CC BY-NC-SA 4.0 (+ LICENSING.md) | 8,116 | 2026-11-13 | plugin marketplace | NOT VERIFIED | Not in a paid or differently-licensed product without written permission |
| [NadavGrossman/the-mom-test-skills](https://github.com/NadavGrossman/the-mom-test-skills) | Nadav Grossman | LICENSE: MIT | 1 | 2026-10-21 | `npx skills add NadavGrossman/the-mom-test-skills --agent claude-code --yes` | None seen | Yes for the repo text; the underlying book is separately copyrighted |

- `anthropics/skills` (198,565 stars, last commit 2026-11-16) has no root LICENSE file, only THIRD_PARTY_NOTICES.md; per-skill licence terms were NOT VERIFIED. It has no marketing skills relevant to this slot — [GitHub repo](https://github.com/anthropics/skills)
- marketingskills funds itself through "Verified Partners": the README says partner integrations are "vetted, disclosed … and never influencing what the core skills recommend", and `partners.json` lists vendors such as Converly, Ploy, AIsa and Omnia — [README](https://github.com/coreyhaines31/marketingskills/blob/main/README.md), [partners.json](https://github.com/coreyhaines31/marketingskills/blob/main/partners.json)
- Despite that statement, the `launch` SKILL.md itself links a partner integration inline: "for channel partner launches, use Introw … to manage deal registration and commissions" — [launch/SKILL.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/launch/SKILL.md)

### Inferences
- MIT requires the copyright notice and permission notice to travel with "all copies or substantial portions". A bundled skill folder should carry the upstream LICENSE text and an attribution line; this is my reading of the standard MIT terms, not legal advice.
- Bundling marketingskills files verbatim would also bundle its sponsor mentions. Either strip them (allowed under MIT) or accept them knowingly.
- marketingskills ships multiple releases per day (three tags on 2026-11-20). A vendored copy will go stale fast, so pin a version and record it.

### Gaps
- Dependency checks were done by grepping SKILL.md and README files, not by running the skills. Hidden runtime needs are possible.
- pm-skills and deanpeters dependency details were not checked.

## Key Question 6: Can individual skills be extracted from a larger pack?

### Takeaway
Yes for marketingskills and solo-founder-skills, with soft dependencies only: each skill is a self-contained folder plus a shared, optional context file. im-not-ai and gstack are multi-part systems and do not extract cleanly.

### Cited Findings
- marketingskills' README states: "Skills reference each other and build on shared context. The `product-marketing` skill is the foundation — every other skill checks it first" — [README](https://github.com/coreyhaines31/marketingskills/blob/main/README.md)
- The actual coupling is conditional. Each skill says: "If `.agents/product-marketing.md` exists (or `.claude/product-marketing.md` …), read it before asking questions"; if absent, the skill asks the user instead — [copywriting/SKILL.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/copywriting/SKILL.md)
- Each skill keeps its own `references/` folder (for example copywriting has `ai-tells.md`, `copy-frameworks.md`, `natural-transitions.md`; cold-email has 10 reference files), so a skill must be copied as a whole folder — [skills tree](https://github.com/coreyhaines31/marketingskills/tree/main/skills)
- Cross-skill pointers exist and would dangle in a subset: `cold-email` sends the reader to "the prospecting skill's compliance reference" and to `sales-enablement` for call scripts; `launch` lists marketing-ideas, emails, cro, marketing-psychology, programmatic-seo and sales-enablement as related; `cro` links a `revops` reference by absolute GitHub URL — [cold-email/SKILL.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/cold-email/SKILL.md), [launch/SKILL.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/launch/SKILL.md), [cro/SKILL.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/cro/SKILL.md)
- The upstream installer supports subsets directly: `npx skills add coreyhaines31/marketingskills --skill cro copywriting` — [README](https://github.com/coreyhaines31/marketingskills/blob/main/README.md)
- The Claude Code plugin route installs all 53 skills as one plugin (`"source": "./"`), with no per-skill selection — [marketplace.json](https://github.com/coreyhaines31/marketingskills/blob/main/.claude-plugin/marketplace.json)
- solo-founder-skills' skills are single short SKILL.md files; they refer to an optional `ABOUT-ME.md` ("Read ABOUT-ME.md first, if it exists") and name sibling skills (`landing-page` tells the model to run `humanize`; `first-customers` defers page writing to `landing-page`) — [first-customers/SKILL.md](https://github.com/whawkinsiv/solo-founder-skills/blob/main/skills/first-customers/SKILL.md), [landing-page/SKILL.md](https://github.com/whawkinsiv/solo-founder-skills/blob/main/skills/landing-page/SKILL.md)
- im-not-ai's main skill calls named agents (`humanize-monolith`, `humanize-diagnostician`, …) and python scripts, and notes a known problem with `CLAUDE_PLUGIN_ROOT` being empty inside Bash (#84) — [humanize-korean/SKILL.md](https://github.com/epoko77-ai/im-not-ai/blob/main/skills/humanize-korean/SKILL.md)

### Inferences
- If Revive bundles a marketingskills subset, it should either include `product-marketing` or have Revive write `.agents/product-marketing.md` itself from the context it already gathers. The second option turns the pack's shared-context design into an advantage: Revive fills the file once and every bundled skill picks it up.
- Dangling cross-references should be edited out of vendored copies, or Revive's orchestrator should tell the model which sibling skills are absent.
- im-not-ai is better consumed as a whole plugin (dependency or recommended install) than as a vendored fragment. For a vendored Korean pass, k-skill's prompt-only `korean-humanizer` or hjongc/humanizer-kr is simpler.

### Gaps
- Whether Claude Code's plugin system lets one plugin declare another plugin as a dependency, as an alternative to vendoring, was not researched here.

## Key Question 7: Known complaints (generic output, too growth-stage, bloated)

### Takeaway
The verifiable complaints are about size and stage fit, not about bad advice. marketingskills is large (53 skills, long files, several releases a day) and much of it assumes an existing funnel; complaints about generic output exist only as unverified snippets or competitor marketing.

### Cited Findings
- Size: installing the whole pack adds about 50 skill names and descriptions to Claude Code's listing, and Claude Code drops descriptions of least-used skills once the listing exceeds its budget, so some skills may stop being matched. Reviewer's advice is to install by name. READ DIRECTLY — [missiongrowth.io, 2026-10-15](https://missiongrowth.io/blog/claude-skills-for-marketing)
- Size, measured: the 13 SKILL.md files I downloaded for this slot total 191,666 bytes before any reference files (range 155 to 491 lines each) — [skills tree](https://github.com/coreyhaines31/marketingskills/tree/main/skills)
- Upgrade friction: v2.0 renamed 17 skills, and upgraders are left with stale old-name folders that must be removed by hand — [README](https://github.com/coreyhaines31/marketingskills/blob/main/README.md)
- Stage fit, from the files themselves: `launch` spends most of its length on a five-phase rollout, influencer and affiliate channels, and ongoing feature announcements; `prospecting`'s three main branches assume contact databases (Apollo, ZoomInfo, Clay) and email verification, with first-customer discovery as a fourth branch; `pricing` is mostly tiers, research methods and price increases — [launch/SKILL.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/launch/SKILL.md), [demand-signals.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/prospecting/references/demand-signals.md), [pricing/SKILL.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/pricing/SKILL.md)
- Counterpoint: the pack has added early-stage material (the pricing "Initial Pricing" section, the launch readiness gate, the demand-signal branch), so it is not purely growth-stage — [pricing/SKILL.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/pricing/SKILL.md), [launch/SKILL.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/launch/SKILL.md)
- Generic or shallow output: one unattributed reply to Haines on X (SEARCH SNIPPET ONLY) and one competitor's blog (SEARCH SNIPPET ONLY) make this claim; see Key Question 4 — [X post](https://x.com/coreyhainesco/status/2013272998191812906), [claudefa.st](https://claudefa.st/blog/tools/skills/claude-code-marketing-skills)
- The repo's own issue tracker shows no user complaints about generic output, bloat, early-stage fit or Korean/i18n: searches for those terms returned only maintainer-style improvement issues (40 open issues total) — [issues](https://github.com/coreyhaines31/marketingskills/issues)
- Humanizer limits: reviewers and users agree it removes AI tells but does not add a personal voice, and it is tuned for English — [Artificial Corner, 2026-11-01](https://artificialcorner.com/p/viral-claude-skills), [tonylee.im, 2026-02-08](https://tonylee.im/en/blog/claude-code-skills-that-survived/)
- General skill fatigue: "About 90% of those skills sat unused after the first day" — [tonylee.im, 2026-02-08](https://tonylee.im/en/blog/claude-code-skills-that-survived/)
- Sponsor content sits inside at least one core skill file (Introw in `launch`) — [launch/SKILL.md](https://github.com/coreyhaines31/marketingskills/blob/main/skills/launch/SKILL.md)
- solo-founder-skills: no complaints found, but also almost no discussion found; no Hacker News mentions at all — [HN search](https://hn.algolia.com/?q=solo-founder-skills)

### Inferences
- **Bottom line for the slot: no single candidate is clearly right as shipped.** marketingskills is trustworthy and maintained but oversized and partly aimed past the first payment. solo-founder-skills is aimed correctly but unproven. A curated subset, pinned to a version, with Revive supplying the shared context file and the stage discipline ("one offer, one price, one action; first 10 by hand"), is the defensible choice.
- Parts Revive most likely has to write itself: (1) Korean launch channels and community etiquette, (2) launch-post drafting for specific venues (Show HN, Reddit, Product Hunt, Threads, Korean communities), (3) the glue that stops at first payment instead of continuing into growth work, and (4) Korean copy generation from a positioning brief, with a Korean humanizer as the final pass.
- Suggested picks, to be confirmed by a hands-on test:
  - Landing copy and pricing: marketingskills `copywriting` + `pricing` + `offers` (primary); solo-founder-skills `landing-page` + `pricing` (alternate, or the template for Revive's own thin version).
  - First customers and outreach: marketingskills `prospecting` (demand-signals branch) + `cold-email`; solo-founder-skills `first-customers` as alternate.
  - Launch platforms: marketingskills `launch` + `directory-submissions`, trimmed.
  - English de-AI pass: blader/humanizer.
  - Korean de-AI pass: im-not-ai as the recommended external plugin; k-skill `korean-humanizer` or hjongc/humanizer-kr as the vendorable alternate.

### Gaps
- The absence of complaints may reflect my inability to read Reddit, X and Threads rather than an absence of criticism.
- No side-by-side output test was run. Before bundling, run the shortlisted skills on one real abandoned project, in English and Korean, and compare against plain Claude without a skill.
