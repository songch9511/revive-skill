# Design slot (UI/UX) skill candidates for Revive — research notes (state as of 2026-11-22)

Evidence labels used throughout:
- **REPO-VERIFIED** = read from the GitHub repo itself on 2026-11-22 (GitHub REST API, raw files, or github.com HTML).
- **READ DIRECTLY** = the page/post itself was opened and read.
- **SEARCH SNIPPET ONLY** = only a search-engine snippet/summary was seen; the page could not be opened.
- **NOT VERIFIED** = could not be confirmed.

Access limits that shaped this research: Reddit could not be opened by any tool (search tool refuses the domain, direct fetch returns 403, browser pane blocks it). X returned HTTP 402. Threads posts never surfaced in search. Medium/UX Planet and wikidocs.net returned 403. So **no Reddit, X or Threads post was READ DIRECTLY**; first-hand user voices come from Hacker News comments (read via the HN Algolia API) and GitHub issue lists. Everything else is blogs/roundups, several with a commercial conflict of interest (flagged per item).

---

## 1. Which design/UI skills do real users actually recommend (Reddit, X, Threads, YouTube, HN)?

### Takeaway
The same four names recur everywhere: **Impeccable**, **taste-skill**, Anthropic's **frontend-design**, and **ui-ux-pro-max**, with Emil Kowalski's and Jakub Krehel's skills as "polish/motion add-ons". The only quantified Reddit evidence (second-hand, from a vendor blog) says Impeccable is by far the most-recommended; direct first-hand evidence I could actually read (HN) is thin but consistent with that, and frontend-design is the most *used* but also the most *recognisable/criticised*.

### Cited Findings

**Reddit (none read directly)**
- SECOND-HAND, vendor blog, READ DIRECTLY (the blog, not the threads). Subframe (sells a competing UI design product; article promotes its own MCP), by Irvin Zhan, dated 2026-10-24: coded 1,002 Reddit threads from Jul–Oct 2026, 511 substantive; **Impeccable appears in 78 of 511 threads, "often as the top answer"; taste-skill in 16 threads, 14 of them alongside Impeccable**. No subreddit names, thread URLs or usernames given, so not auditable. — [Subframe](https://www.subframe.com/tips/best-claude-code-skills-for-ui-design)
- SEARCH SNIPPET ONLY. A thread exists in r/UXDesign titled approximately "Best UX/UI skill for Claude Code: Impeccable vs UX/UI …" (URL slug `best_uxuiskill_for_claude_code_impeccable_vs_uxui`); content and date could not be read. — [Reddit r/UXDesign](https://www.reddit.com/r/UXDesign/comments/1syaen1/best_uxuiskill_for_claude_code_impeccable_vs_uxui/)
- Subframe paraphrases one Reddit designer saying that after teaching Claude several skills including Emil Kowalski's, the result "still fell flat" (no link/username). — [Subframe](https://www.subframe.com/tips/best-claude-code-skills-for-ui-design)

**Hacker News (READ DIRECTLY via HN Algolia API; genuine user comments, not authors)**
- 2026-08-14, user Wpnx330, in "Ask HN: How can you tell a site/app is vibe coded?": uses two open-source tools on own projects — Impeccable (as the detector: "59 deterministic anti-pattern rules") and Taste Skill ("preventive rather than detective"); calls them "actually pretty good". Genuine recommendation of both. — [HN 49294522](https://news.ycombinator.com/item?id=49294522)
- 2026-07-20, user cocoflunchy, replying to a YC launch whose landing page "has very strong AI-generated design vibes": recommends jakubkrehel/skills or emilkowalski/skills ("more around animations"), "maybe" leonxlnx/taste-skill "(didn't try it)". Weak/untested mention of taste-skill. — [HN 48984818](https://news.ycombinator.com/item?id=48984818)
- 2026-07-01, user ssalka lists tasteskill.dev, usehallmark.com, layers.jamiemill.com, impeccable.style as skills "that enhance Claude's design capability" (list, no evaluation). — [HN 48749971](https://news.ycombinator.com/item?id=48749971)
- 2026-09-02, user bargainbin: Claude is "eyebrow crazy"; "Even comprehensive design skills like impeccable miss filtering them out" (it only detects "eyebrow chips"). User actually uses Impeccable; mild criticism. — [HN 49533455](https://news.ycombinator.com/item?id=49533455)
- frontend-design, many 2026 comments (33 hits). Positive: 2026-02-19 sama004 "the frontend-design skill helps a lot" ([HN 47074167](https://news.ycombinator.com/item?id=47074167)); 2026-06-23 halfmatthalfcat "I've had more success with Claude Code and the frontend-design skill" ([HN 48649025](https://news.ycombinator.com/item?id=48649025)); 2026-01-24 julianpeters built a product UI with it ([HN 46743046](https://news.ycombinator.com/item?id=46743046)). Negative: 2026-06-11 efficax "it's remarkable how easy it is to identify websites built with the 'frontend-design' skill" ([HN 48497957](https://news.ycombinator.com/item?id=48497957)); 2026-05-26 freedomben "I see the tell-tale signs… I haven't yet had it give me something I actually like" ([HN 48278342](https://news.ycombinator.com/item?id=48278342)); 2026-05-26 mahmedalam "everyone is building the same tools slop with Claude frontend-design skill" ([HN 48280827](https://news.ycombinator.com/item?id=48280827)); 2026-05-14 skiing_crawling: the skill "basically just begs it to pick nice fonts… No specifics" ([HN 48140242](https://news.ycombinator.com/item?id=48140242)).
- ui-ux-pro-max: **0 HN comments** found for "ui-ux-pro-max" in 2026 despite ~152k GitHub stars. — [HN search](https://hn.algolia.com/?q=%22ui-ux-pro-max%22)
- "Impeccable Style" was an HN story on 2026-01-12 with 103 points; taste-skill's HN submission (2026-05-28) got 3 points. — [HN 46587284](https://news.ycombinator.com/item?id=46587284); [HN 48306196](https://news.ycombinator.com/item?id=48306196)

**X / Twitter**
- SEARCH SNIPPET ONLY (post returned HTTP 402). Nick Babich (@101babich, UX writer/influencer; date NOT VERIFIED) posted "Must-Have UX/UI Design Skills for Claude Code", 6 hand-picked skills; #1 is UI-UX-Pro-Max-Skill, taste-skill also listed. Influencer listicle, not a tested comparison. — [X post](https://x.com/101babich/status/2037561579714032116)
- No other X post could be surfaced or read. Author accounts (@pbakaus for Impeccable; tasteskill.dev for taste-skill) are self-promotion channels by definition. — [Impeccable README](https://github.com/pbakaus/impeccable)

**Threads (incl. Korean)**
- Nothing found. Two Korean-language searches returned only blogs/wikis, no Threads posts. Korean blog worpsense (author 제이원, 2026-07-20; promotes own courses) lists frontend-design, impeccable, taste-skill among "42 skills" with one-line descriptions and no testing; its "start here" pick is frontend-design. READ DIRECTLY, low evidential value. — [worpsense](https://worpsense.com/%ED%81%B4%EB%A1%9C%EB%93%9C-%EB%94%94%EC%9E%90%EC%9D%B8-%EA%B2%B0%EA%B3%BC%EB%AC%BC%EC%9D%B4-%EC%96%B4%EC%83%89%ED%95%9C-%EC%9D%B4%EC%9C%A0-%ED%80%84%EB%A6%AC%ED%8B%B0-%EB%86%92%EC%9D%B4%EB%8A%94-42/)
- Korean wikidocs pages exist for Impeccable and taste-skill (403 on fetch; SEARCH SNIPPET ONLY): describe taste-skill as MIT, and warn that using taste-skill and Impeccable together causes conflicts (different banned-font lists and motion rules). — [wikidocs 340964](https://wikidocs.net/340964); [wikidocs 431830](https://wikidocs.net/431830)

**YouTube**
- SECOND-HAND summary page READ DIRECTLY (not the video). Chase AI, "Top 10 Claude Code Frontend Design Skills, Plugins, & CLIs" (20 min; "added May 3", year not shown): covers Impeccable first (~0:28), UI UX Pro Max (~11:49, "better starting point when you don't yet know which design reference you want"), Taste Skill (~15:49, "higher-level art direction"). Creator promotes own paid course; no third-party sponsor shown. — [video summary](https://vids-ao8.pages.dev/videos/Q9ty3eopOPs)
- SEARCH SNIPPET ONLY: a Flux Academy video "I Tested Claude Skills for Web Design" reportedly tests Impeccable and UI UX Pro Max. Not opened. — [search result page](https://sales.communityimpact.com/i-tested-claude-skills-for-web-design.html)

**Blog head-to-head tests (all READ DIRECTLY unless noted; each has a conflict of interest)**
- Subframe (2026-10-24, vendor): ran 5 skills on one existing landing page; "only Impeccable changed how the page looked"; taste-skill, better-ui (Jakub Krehel), Emil Kowalski's skills "polished details at best". Pick if only one: Impeccable. — [Subframe](https://www.subframe.com/tips/best-claude-code-skills-for-ui-design)
- Paralect (undated, cites Oct 2026 stars; sells dev services): 8 packs, same landing-page brief, single runs. frontend-design: moved page off default look in 3 min. ui-ux-pro-max: "Clean and accessible, but the most generic page"; "Skip ui-ux-pro-max if you want to stand out". taste-skill: strong headline but "a common pattern", "random stock image", "not meant for dashboards or app UI". Impeccable: `/audit` + `/polish` "Found real bugs and fixed them without changing the look". Recommendation: new page → frontend-design; existing page → Impeccable. — [Paralect](https://www.paralect.com/skills/top-design-skills)
- Bitdoze (2026-08-28, affiliate links disclosed): recommends one primary (frontend-design as safe baseline, or taste-skill), plus Impeccable as auditor; "overlap is the top complaint", max three skills. — [Bitdoze](https://www.bitdoze.com/best-ai-skills-for-web-design/)
- Claude Code Club (updated Nov 2026; sells $9/mo membership): "if you can only choose one" → Impeccable; frontend-design for a simple new build; taste-skill if you want dials (note: dials are a v1/v2-experimental feature, see §2). — [Claude Code Club](https://www.claudecodeclub.ai/free-resources/claude-design-skills)
- Composio (2026-05-05; promotes own product): install frontend-design first ("the floor, not the ceiling"), add Impeccable if you build both marketing sites and product UI — its brand-vs-product split is the only one that "respects the distinction". taste-skill and ui-ux-pro-max not covered. — [Composio](https://composio.dev/content/top-design-skills)
- SEARCH SNIPPET ONLY: UX Planet "I Tested 3 Claude Code Skills for Web Design" (paywalled; likely Nick Babich, NOT VERIFIED): Taste Skill gave "the most visually impressive result" but used "nearly 30%" of daily usage quota, ~2x UI/UX Pro Max and ~3x frontend-design; frontend-design rated 3/5. — [UX Planet](https://uxplanet.org/i-tested-3-claude-code-skills-for-web-design-which-one-is-best-521137220dc1)

### Inferences
- Across independent-ish sources, the modal advice is: **Impeccable for improving an existing UI; frontend-design as a zero-cost baseline for new UI; taste-skill for showy new landing pages if you accept the cost; ui-ux-pro-max is popular by stars but gets the weakest qualitative reviews ("most generic").**
- For Revive's scenario (an existing, abandoned project whose UI the owner dislikes), "works on existing interfaces" is the relevant axis, and that is exactly where Impeccable is consistently placed first.
- Star counts are not a reliable recommendation signal here: ui-ux-pro-max has the most stars of the third-party skills yet zero HN discussion, and taste-skill has a closed issue alleging fake engagement (see §6).

### Gaps
- No Reddit thread, X post or Threads post was read directly; the Subframe Reddit counts cannot be audited. A human with a logged-in browser should spot-check r/ClaudeCode / r/ClaudeAI / r/vibecoding searches for "impeccable", "taste skill", "ui-ux-pro-max".
- No Korean Threads evidence found at all (neither positive nor negative).
- No YouTube video was watched/transcribed first-hand; view counts and sponsorship NOT VERIFIED.

---

## 2. "Taste Skill": does it exist, canonical repo, author, what it does, license, how it is regarded?

### Takeaway
Yes: canonical repo is **github.com/Leonxlnx/taste-skill** (author "Leonxlnx"/Leon, MIT, ~120k stars, actively maintained). But the skill has been **rebuilt repeatedly**; the current version (2.5.1, 2026-11-07) is a heavy, script-driven kit for **company/marketing websites only** — the dial-based "taste" skill many people remember is v1, now moved to a separate small repo. This matters a lot for bundling.

### Cited Findings (REPO-VERIFIED 2026-11-22 unless noted)
- Repo `Leonxlnx/taste-skill`: created 2026-02-19; 119,795 stars; 8,024 forks; not archived; `pushed_at` 2026-11-22; latest commits on main 2026-11-07 ("tasteskill 2.5.1…") and 2026-11-05. — [GitHub API](https://api.github.com/repos/Leonxlnx/taste-skill); [repo](https://github.com/Leonxlnx/taste-skill)
- LICENSE file present: "MIT License, Copyright (c) 2026 Leonxlnx". marketplace.json also declares `"license": "MIT"`. — [LICENSE](https://raw.githubusercontent.com/Leonxlnx/taste-skill/main/LICENSE); [marketplace.json](https://raw.githubusercontent.com/Leonxlnx/taste-skill/main/.claude-plugin/marketplace.json)
- Repo now holds exactly one skill, folder `skills/taste-skill`, SKILL.md `name: design-taste-frontend` (30,970 bytes) plus 22 reference files (~407 KB), 12 scripts (~1.56 MB), and 1,594 asset files (~34.5 MB). Whole skill folder ≈ 36.6 MB / 1,631 files. — [tree](https://github.com/Leonxlnx/taste-skill/tree/main/skills/taste-skill); [SKILL.md](https://raw.githubusercontent.com/Leonxlnx/taste-skill/main/skills/taste-skill/SKILL.md)
- Self-description: builds "professional company websites at the figma.com and x.ai level"; use for "a landing page, company, product, shop, cafe, hotel, studio, SaaS, AI, developer-tool or game site". — [SKILL.md](https://raw.githubusercontent.com/Leonxlnx/taste-skill/main/skills/taste-skill/SKILL.md)
- Requirements: "Node 22+ and an installed Chrome, Edge or Chromium"; ffmpeg optional; "installs nothing and needs no API keys"; network used only for extra photos, Google Fonts, brand icons. No MCP server. — [README](https://github.com/Leonxlnx/taste-skill/blob/main/README.md)
- The SKILL.md frontmatter registers a **Stop hook** (`gate.mjs --hook claude`, timeout 600 s) — a "finish gate" that holds completion until browser checks pass (max three rounds). — [SKILL.md](https://raw.githubusercontent.com/Leonxlnx/taste-skill/main/skills/taste-skill/SKILL.md)
- Install: `npx skills add https://github.com/Leonxlnx/taste-skill --skill "design-taste-frontend"`; or Claude Code plugin `/plugin marketplace add Leonxlnx/taste-skill` + `/plugin install taste-skill@taste-skill`; or `install.sh` symlink. — [README](https://github.com/Leonxlnx/taste-skill/blob/main/README.md)
- Version churn: v1 (dial-driven: DESIGN_VARIANCE / MOTION_INTENSITY / VISUAL_DENSITY) → v2-experimental → 2.0.0 (2026-10-13) → 2.1.0 (2026-10-19, added "App screens: dashboards, admin, settings, inboxes") → **2.5.0 (2026-11-05) "A complete rebuild… around professional company websites… replacing the 2.1.x direction-sheet and app-screen pipeline"**. Current tree has no `app-screens.md`. — [CHANGELOG](https://github.com/Leonxlnx/taste-skill/blob/main/CHANGELOG.md)
- Author's own cost statement (for v2): "A full run with the look-and-fix loop takes an agent roughly 30 to 45 minutes and a few hundred thousand tokens". Author's own blind test: "v2 7.7, no skill 7.8, other skill 7.2" (i.e. no measurable win over no-skill on juror score; win was on its own inspector). — [CHANGELOG](https://github.com/Leonxlnx/taste-skill/blob/main/CHANGELOG.md)
- Older skills moved out: v1, v2-experimental, minimalist-ui, high-end-visual-design, industrial-brutalist-ui, gpt-taste, stitch-design-taste → `Leonxlnx/taste-skill-classics` (MIT per GitHub API; 49 stars; created and last pushed 2026-10-19; repo size 78 KB). `redesign-existing-projects` was folded into the main skill. — [README "Moved skills"](https://github.com/Leonxlnx/taste-skill/blob/main/README.md); [classics API](https://api.github.com/repos/Leonxlnx/taste-skill-classics)
- Bundled third-party content: `assets/photos/photos.json` lists **274 photos under the "Unsplash License"** and 139 Wikimedia Commons photos (CC0 53, CC BY-SA 4.0 39, CC BY 2.0 22, CC BY-SA 3.0 12, others); brand logos from gilbarbara/logos and Simple Icons marked `"trademark": true` (CC0 files, but third-party trademarks). — [photos.json](https://raw.githubusercontent.com/Leonxlnx/taste-skill/main/skills/taste-skill/assets/photos/photos.json); [icons-credits.json](https://raw.githubusercontent.com/Leonxlnx/taste-skill/main/skills/taste-skill/assets/ui/icons/icons-credits.json)
- Commercial context: README carries paid sponsors (interfaces.dev, React Bits, IMG.LY, Sent.dm), an affiliate link for Kimi API credits, and promotes the author's "TasteCode" desktop app. — [README](https://github.com/Leonxlnx/taste-skill/blob/main/README.md)
- Regard: genuinely recommended by at least one HN user (2026-08-14) and widely listed; but in the two blog tests on an *existing* page it did not change the design (Subframe) and is "not meant for dashboards or app UI" (Paralect). — [HN 49294522](https://news.ycombinator.com/item?id=49294522); [Subframe](https://www.subframe.com/tips/best-claude-code-skills-for-ui-design); [Paralect](https://www.paralect.com/skills/top-design-skills)
- Name collisions exist (senlindesign/taste-skill, Dragoon0x/taste-skills, hmbown/taste, VOIDXAI/taste, forks such as nexu-io's maintained v1 fork); these are not the canonical project. — [senlindesign/taste-skill](https://github.com/senlindesign/taste-skill); [claudemarketplaces listing](https://claudemarketplaces.com/skills/nexu-io/open-design/design-taste-frontend-v1)

### Inferences
- MIT permits redistribution of the repo's own code/text inside another plugin (keep the copyright + license notice). **However, bundling the current skill folder also redistributes ~413 third-party photographs and third-party brand logos**: CC BY / CC BY-SA files need attribution (and share-alike for adaptations), and the Unsplash License has its own restrictions (my understanding, NOT VERIFIED against current Unsplash terms: free use is allowed but not selling unaltered copies or compiling photos into a competing service). This is a real compliance burden for a redistributing plugin, and Revive is a paid-customer-oriented product.
- The current taste-skill is a poor default for "make my existing app UI look better quickly": it targets marketing sites, takes 30–45 min and several hundred thousand tokens by the author's own figure (for v2), needs Node 22 + Chrome, adds a 10-minute-timeout Stop hook, and weighs ~36 MB. It could be a good fit for a *separate* "launch landing page" step.
- If the project owner's preference was formed on the dial-based skill, that is **v1** (`design-taste-frontend-v1` in taste-skill-classics): tiny, MIT, text-only, easy to bundle — but effectively frozen (one push, 49 stars) and the author has moved on.
- A complete rebuild every 2–4 weeks (2.0 → 2.1 → 2.5 between 2026-10-13 and 2026-11-05) means a vendored copy will drift from upstream quickly and behaviour is not stable.

### Gaps
- Which taste-skill version the project owner actually used/liked is unknown — this decides between "current 2.5.x", "v1 classics", or "not taste-skill".
- Token/time cost of 2.5.x specifically (the 30–45 min figure is from the v2 changelog section) NOT VERIFIED.
- Exact SKILL.md of v1 in taste-skill-classics (size, whether it has an explicit out-of-scope list for dashboards — the v2-experimental changelog says "§13 Out of Scope… dashboards, data tables, multi-step forms…") was not opened.
- Issue #48 "[phantomstars] Fake engagement detected on this repository" (closed 2026-06-08): only the title was read; the allegation's substance and the maintainer's reply are NOT VERIFIED. — [issues list](https://github.com/Leonxlnx/taste-skill/issues?q=is%3Aissue+sort%3Acomments-desc)

---

## 3. Evaluation of Anthropic `frontend-design`, `impeccable`, and other widely recommended skills

### Takeaway
**Impeccable** is the best functional match for the design slot (explicitly strongest on existing interfaces, covers app UI *and* landing pages, stack-agnostic, most third-party recommendations) but is a moving, binary-backed product with hooks and network calls. **frontend-design** is the safest thing to bundle (one 9 KB Apache-2.0 file, zero dependencies) but gives the smallest lift and has a recognisable house look. **ui-ux-pro-max** is popular but reviewed as generic and needs Python. No candidate is clean on every dimension.

### Cited Findings

**Impeccable (pbakaus/impeccable)** — REPO-VERIFIED
- Author Paul Bakaus; README: "Impeccable started from Anthropic's frontend-design skill". 1 skill, 24 commands (`polish`, `audit`, `critique`, `bolder`, `quieter`, `typeset`, `layout`, `colorize`, `harden`, `onboard`, `live`, …), plus a deterministic detector ("62 deterministic rules… No LLM, no API key"). — [README](https://github.com/pbakaus/impeccable/blob/main/README.md)
- Self-stated sweet spot: "Impeccable is strongest on interfaces that already exist: point it at a page or a component and iterate." — [README](https://github.com/pbakaus/impeccable/blob/main/README.md)
- SKILL.md scope: "websites, landing pages, dashboards, app UI, components, native iOS/Android screens, or a design system"; has explicit modes (Persuade = marketing; **Operate = app UI, dashboards, admin, settings**; Read; Experience). SKILL.md is ~12.7 KB; references loaded on demand. — [plugin SKILL.md](https://raw.githubusercontent.com/pbakaus/impeccable/main/plugin/skills/impeccable/SKILL.md)
- Workflow: `/impeccable init` writes PRODUCT.md once per project; `/impeccable document` writes DESIGN.md; working files under `.impeccable/` (needs .gitignore entries). — [README](https://github.com/pbakaus/impeccable/blob/main/README.md)
- Runtime: "The skill itself runs a self-contained engine binary that ships next to it or downloads once into `~/.impeccable/bin/`"; launcher verifies downloads against `engine-checksums.txt`. The `plugin/` folder (71 files, ~2.31 MB) contains no binary, so a plugin/vendored install **downloads a native binary on first run**. — [README](https://github.com/pbakaus/impeccable/blob/main/README.md); [launcher script](https://raw.githubusercontent.com/pbakaus/impeccable/main/plugin/skills/impeccable/scripts/impeccable)
- Plugin ships hooks: SessionStart, PostToolUse on `Edit|Write`, and Stop, each invoking the engine. README warning: "Hooks run outside model approval… the first edit can download the engine." — [hooks.json](https://raw.githubusercontent.com/pbakaus/impeccable/main/plugin/hooks/hooks.json); [README](https://github.com/pbakaus/impeccable/blob/main/README.md)
- Network/telemetry: "When a new design starts, the skill fetches a set of visual directions from the impeccable.style catalog. Turning telemetry off doesn't stop that request"; anonymous usage record can be disabled (`npx impeccable telemetry off`, `DO_NOT_TRACK=1`). — [README](https://github.com/pbakaus/impeccable/blob/main/README.md)
- Live mode caveat: if no chat agent is polling, Apply runs the `codex`/`claude` CLI "with approvals, permission checks, and sandboxing off" unless `IMPECCABLE_LIVE_COPY_AGENT=chat|off`. — [README](https://github.com/pbakaus/impeccable/blob/main/README.md)
- Plugin also ships 5 subagents (asset-producer, documenter, finish-reviewer, manual-edit-applier, motion-reviewer). — [plugin/agents](https://github.com/pbakaus/impeccable/tree/main/plugin/agents)
- Third-party verdicts: see §1 (Subframe, Paralect, Claude Code Club, Composio all favour it for existing UIs).

**Anthropic frontend-design** — REPO-VERIFIED
- Lives in two places: `anthropics/skills/skills/frontend-design` (SKILL.md 9,390 bytes + LICENSE.txt; nothing else) and `anthropics/claude-plugins-official/plugins/frontend-design` (plugin v1.1.1, same SKILL.md text, own LICENSE). — [anthropics/skills](https://github.com/anthropics/skills/tree/main/skills/frontend-design); [plugin.json](https://raw.githubusercontent.com/anthropics/claude-plugins-official/main/plugins/frontend-design/.claude-plugin/plugin.json)
- License: Apache License 2.0 (LICENSE.txt in the skill folder; anthropics/skills README: "Many skills in this repo are open source (Apache 2.0)"). Note the GitHub API reports `license: null` for the anthropics/skills repo as a whole — the license is per-skill. — [LICENSE.txt](https://raw.githubusercontent.com/anthropics/skills/main/skills/frontend-design/LICENSE.txt); [README](https://github.com/anthropics/skills/blob/main/README.md)
- Content: pure prompt guidance ("design lead at a design studio… take aesthetic risk if justified"); description: "when building new UI or reshaping an existing one". No scripts, no hooks, no network, stack-agnostic. — [SKILL.md](https://raw.githubusercontent.com/anthropics/skills/main/skills/frontend-design/SKILL.md)
- Maintained: last commits to the skill path 2026-09-03 ("Update frontend-design skill to avoid generic design defaults (#1713)") and 2026-06-09; plugin path last touched 2026-10-26. — [commits](https://github.com/anthropics/skills/commits/main/skills/frontend-design); [plugin commits](https://github.com/anthropics/claude-plugins-official/commits/main/plugins/frontend-design)
- Reception: most-used baseline; praised as helpful; criticised as instantly recognisable and vague (HN quotes in §1); "the floor, not the ceiling" (Composio). — [Composio](https://composio.dev/content/top-design-skills)

**ui-ux-pro-max (nextlevelbuilder/ui-ux-pro-max-skill)** — REPO-VERIFIED
- A searchable local design database driven by a Python script: "80 searchable styles (51 active), 194 product palettes…, 74 font pairings, 141 UX guidelines, 105 icons, 17 GSAP presets, 25 chart types, and 22 stacks". Plugin v2.15.0. — [SKILL.md](https://raw.githubusercontent.com/nextlevelbuilder/ui-ux-pro-max-skill/main/.claude/skills/ui-ux-pro-max/SKILL.md); [plugin.json](https://raw.githubusercontent.com/nextlevelbuilder/ui-ux-pro-max-skill/main/.claude-plugin/plugin.json)
- "Python 3.x is required for the search script (standard library only — the scripts install nothing and make no network calls)." — [README](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill/blob/main/README.md)
- Plugin exposes 7 skills from `.claude/skills/` (ui-ux-pro-max, design, design-system, ui-styling, brand, banner-design, slides), ~10 MB in that folder. — [repo tree](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill/tree/main/.claude/skills)
- Reviews: Paralect "the most generic page… Skip ui-ux-pro-max if you want to stand out"; Bitdoze "Largest context footprint when triggered"; Chase AI positions it as a starting point when you have no design reference. — [Paralect](https://www.paralect.com/skills/top-design-skills); [Bitdoze](https://www.bitdoze.com/best-ai-skills-for-web-design/); [video summary](https://vids-ao8.pages.dev/videos/Q9ty3eopOPs)

**Other names that recur (lighter verification)**
- `emilkowalski/skills` (Emil Kowalski): MIT (LICENSE read), 58,690 stars (github.com HTML). Motion/interaction polish only; "doesn't touch layout, color, or type, so it must be paired with another pack". — [repo](https://github.com/emilkowalski/skills); [Paralect](https://www.paralect.com/skills/top-design-skills)
- `jakubkrehel/skills` ("better-ui" suite): MIT (LICENSE read), 12,556 stars. Review-first detail polish; "Doesn't set direction and keeps the existing style". — [repo](https://github.com/jakubkrehel/skills); [Subframe](https://www.subframe.com/tips/best-claude-code-skills-for-ui-design)
- `Owl-Listener/designer-skills`: MIT, 3,459 stars; large process pack ("273 skills"), "all 33 at once floods the agent" — heavy for solo vibe coders. — [repo](https://github.com/Owl-Listener/designer-skills); [Paralect](https://www.paralect.com/skills/top-design-skills)
- Hallmark (usehallmark.com) and huashu-design appear in Paralect's test (Hallmark: most restrained, no invented stats; huashu-design: 3 directions, ~8.5 min, ~$4.20 per run). Repos NOT VERIFIED. — [Paralect](https://www.paralect.com/skills/top-design-skills)
- No shadcn/Tailwind-specific *design* skill surfaced as widely recommended in any source read; ui-ux-pro-max's `ui-styling` sub-skill and its optional `stack/.mcp.json` (playwright, chrome-devtools, shadcn MCP) are the closest. — [stack/.mcp.json](https://raw.githubusercontent.com/nextlevelbuilder/ui-ux-pro-max-skill/main/stack/.mcp.json)

### Inferences
- Ranking for Revive's design slot by fit (existing project, visible improvement, any stack): **1) Impeccable, 2) frontend-design (fallback / zero-dependency baseline), 3) taste-skill (landing-page step only; or v1 classics if the owner specifically wants it)**. ui-ux-pro-max is a distant fourth on review quality despite stars.
- A pragmatic design is "bundle frontend-design (tiny, safe) as the always-available baseline and *route to / install* Impeccable via its own marketplace rather than vendoring it", because Impeccable's value depends on a version-pinned binary, hooks and frequent releases (v4.10.0; engine 0.1.27 on 2026-11-18).
- Do not bundle two primary design skills as co-defaults: multiple sources report rule conflicts (banned fonts, motion values) when primaries are combined.

### Gaps
- No controlled first-hand test was run in this research; all quality claims are third-party single-run tests or anecdotes.
- Hallmark, huashu-design, ConardLi/garden-skills (web-design-engineer), codeswithroh/tastemaker, MengTo/Skills repos were not verified (GitHub API rate limit).
- Whether `stack/.mcp.json` in ui-ux-pro-max is activated by the plugin install or is only a sample was NOT VERIFIED.

---

## 4. Per-candidate facts verified from the repo itself (license, activity, stars, install, size, dependencies, redistribution)

### Takeaway
All four main candidates carry a permissive license file (MIT or Apache-2.0) that permits redistribution inside another plugin with notices preserved; the practical differences are size, runtime dependencies, hooks/network behaviour, and bundled third-party assets.

### Cited Findings (REPO-VERIFIED 2026-11-22; stars from GitHub REST API unless noted)

| | taste-skill | impeccable | frontend-design | ui-ux-pro-max |
|---|---|---|---|---|
| Repo | [Leonxlnx/taste-skill](https://github.com/Leonxlnx/taste-skill) | [pbakaus/impeccable](https://github.com/pbakaus/impeccable) | [anthropics/skills → skills/frontend-design](https://github.com/anthropics/skills/tree/main/skills/frontend-design) and [claude-plugins-official → plugins/frontend-design](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/frontend-design) | [nextlevelbuilder/ui-ux-pro-max-skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill) |
| Author | Leonxlnx (individual) | Paul Bakaus (individual) | Anthropic | nextlevelbuilder ("Next Level Builder") |
| LICENSE file | MIT, "Copyright (c) 2026 Leonxlnx" | Apache-2.0, "Copyright 2025 Paul Bakaus"; plus NOTICE.md (MIT-derived iOS/Android refs; OFL fonts and MPL-2.0 consent rules only in the browser extension) | Apache-2.0 (`LICENSE.txt` inside the skill folder; plugin folder also has Apache-2.0 LICENSE) | MIT, "Copyright (c) 2024 Next Level Builder"; `ui-styling` sub-skill carries an Apache-2.0 LICENSE.txt |
| Stars | 119,795 | 114,603 | anthropics/skills 198,564 (whole repo); claude-plugins-official 47,920 (HTML) | 152,563 |
| Created | 2026-02-19 | 2025-11-16 | repo 2025-09-22 | 2025-11-30 |
| Last commit (main) | 2026-11-07 (repo pushed_at 2026-11-22) | 2026-11-18 (pushed_at 2026-11-22) | skill path 2026-09-03; plugin path 2026-10-26 | 2026-11-22 |
| Version | 2.5.1 | 4.10.0 (engine 0.1.27) | plugin 1.1.1 | 2.15.0 |
| Install | `npx skills add … --skill design-taste-frontend`; Claude Code marketplace plugin; `install.sh` symlink | `npx impeccable install` (npm); Claude Code marketplace plugin; manual copy of `.claude/skills/impeccable`; git submodule | copy the folder; or official Claude Code plugin marketplace | Claude Code marketplace plugin; `npm i -g ui-ux-pro-max-cli` + `uipro init --ai claude` |
| Size | skill folder ≈ 36.6 MB / 1,631 files (SKILL.md 31 KB) | `plugin/` ≈ 2.3 MB / 71 files (SKILL.md 12.7 KB) + native engine binary downloaded on first run | 9.4 KB SKILL.md + license | `.claude/skills` ≈ 10 MB / 272 files, 7 skills (main SKILL.md 18.6 KB) |
| Runtime deps | Node 22+, Chrome/Edge/Chromium; ffmpeg optional | Self-contained binary (download to `~/.impeccable/bin` if not shipped); Node only for `npx` installer; Chrome/Edge for URL scans | none | Python 3 (stdlib only) |
| MCP / API keys / paid | none / none / none (sponsor + affiliate links in README only) | none / none / none | none | none required (optional sample `.mcp.json` in `stack/`) / none / none |
| Hooks | Stop hook (finish gate, 600 s timeout) | SessionStart, PostToolUse(Edit\|Write), Stop | none | none found in plugin.json |
| Network at runtime | optional (photos, fonts, icons) | engine download; fetches "visual directions" from impeccable.style on new designs; optional telemetry | none | none ("make no network calls") |
| License permits redistribution in another plugin? | Yes for MIT-covered code/text (keep notice). Bundled photos/logos carry their own licenses/trademarks (Unsplash License ×274, CC BY/BY-SA, CC0). | Yes (Apache-2.0 §4: include LICENSE, keep NOTICE, mark modified files). | Yes (Apache-2.0, same conditions). | Yes (MIT; keep notice; Apache-2.0 notice for `ui-styling`). |

Sources for the table: [taste API](https://api.github.com/repos/Leonxlnx/taste-skill), [taste LICENSE](https://raw.githubusercontent.com/Leonxlnx/taste-skill/main/LICENSE), [taste README](https://github.com/Leonxlnx/taste-skill/blob/main/README.md), [taste photos.json](https://raw.githubusercontent.com/Leonxlnx/taste-skill/main/skills/taste-skill/assets/photos/photos.json); [impeccable API](https://api.github.com/repos/pbakaus/impeccable), [impeccable LICENSE](https://raw.githubusercontent.com/pbakaus/impeccable/main/LICENSE), [NOTICE.md](https://raw.githubusercontent.com/pbakaus/impeccable/main/NOTICE.md), [plugin.json](https://raw.githubusercontent.com/pbakaus/impeccable/main/.claude-plugin/plugin.json), [hooks.json](https://raw.githubusercontent.com/pbakaus/impeccable/main/plugin/hooks/hooks.json), [impeccable README](https://github.com/pbakaus/impeccable/blob/main/README.md); [anthropics/skills API](https://api.github.com/repos/anthropics/skills), [frontend-design LICENSE.txt](https://raw.githubusercontent.com/anthropics/skills/main/skills/frontend-design/LICENSE.txt), [frontend-design commits](https://github.com/anthropics/skills/commits/main/skills/frontend-design), [plugins-official LICENSE](https://raw.githubusercontent.com/anthropics/claude-plugins-official/main/plugins/frontend-design/LICENSE); [uupm API](https://api.github.com/repos/nextlevelbuilder/ui-ux-pro-max-skill), [uupm LICENSE](https://raw.githubusercontent.com/nextlevelbuilder/ui-ux-pro-max-skill/main/LICENSE), [uupm README](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill/blob/main/README.md).

Secondary candidates: emilkowalski/skills — MIT (LICENSE read), 58,690 stars; jakubkrehel/skills — MIT, 12,556 stars; Owl-Listener/designer-skills — MIT, 3,459 stars; Leonxlnx/taste-skill-classics — MIT (API), 49 stars, last push 2026-10-19, 78 KB. — [emilkowalski/skills](https://github.com/emilkowalski/skills); [jakubkrehel/skills](https://github.com/jakubkrehel/skills); [Owl-Listener/designer-skills](https://github.com/Owl-Listener/designer-skills); [taste-skill-classics](https://github.com/Leonxlnx/taste-skill-classics)

### Inferences
- "Permits redistribution" is a reading of standard MIT / Apache-2.0 terms, not legal advice. Apache-2.0 additionally requires carrying the NOTICE content and stating changes; MIT requires only the copyright/permission notice.
- Easiest to bundle cleanly: frontend-design (one file + license). Hardest: taste-skill 2.5.x (36 MB, third-party photos, Node+Chrome, Stop hook) and Impeccable (binary bootstrap, three hooks, outbound requests — all of which Revive would be shipping to its users and should disclose).
- Bundling a Stop/PostToolUse hook from a third-party skill inside an orchestrator plugin can interfere with the orchestrator's own flow (taste-skill's gate can hold the turn for up to three rounds; Impeccable's hooks fire on every Edit/Write).

### Gaps
- Last-commit dates for emilkowalski/skills, jakubkrehel/skills, Owl-Listener/designer-skills: NOT VERIFIED (GitHub API rate limit hit).
- Impeccable engine download host (GitHub Releases vs npm vs impeccable.style) and binary size: NOT VERIFIED.
- Whether the Impeccable trademark/name or the marketplace terms impose anything beyond Apache-2.0: NOT VERIFIED (no trademark policy file was looked for).
- Current Unsplash License text was not fetched; redistribution limits stated in §2 are from general knowledge.

---

## 5. Stack-specific vs stack-agnostic

### Takeaway
None of the four main candidates is locked to React/Tailwind/shadcn. Differences are in how far beyond web they go and what tooling they assume.

### Cited Findings
- **frontend-design**: pure design guidance, no stack assumptions. — [SKILL.md](https://raw.githubusercontent.com/anthropics/skills/main/skills/frontend-design/SKILL.md)
- **Impeccable**: web stack-agnostic; live mode "works with Vite, Next, SvelteKit, Astro, Nuxt, and plain HTML"; native iOS/Android/Flutter/React Native supported for design commands and audit, but "The detector, live mode… and the edit hook stay web-only". Repo test fixtures cover Astro, Next.js, Nuxt, TanStack, Vue, React. — [README](https://github.com/pbakaus/impeccable/blob/main/README.md)
- **taste-skill 2.5.x**: "An empty folder gets a static page from `assets/starter.html`. An existing React, Vue, Svelte, Astro or Tailwind project is built in its own stack, with the kit served from its public folder; a Next.js brief is built as a static export." Changelog: "The description no longer promises any stack." Web marketing pages only; brings its own `system.css`/`system.js` kit. — [README](https://github.com/Leonxlnx/taste-skill/blob/main/README.md); [CHANGELOG](https://github.com/Leonxlnx/taste-skill/blob/main/CHANGELOG.md)
- **ui-ux-pro-max**: 22 stacks incl. React, Next.js, Vue, Svelte, Astro, SwiftUI, React Native, Flutter, Tailwind, shadcn/ui, Jetpack Compose, Angular, Laravel; "default to HTML + Tailwind" if no stack is named. — [README](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill/blob/main/README.md)
- **emilkowalski/skills, jakubkrehel/skills**: web motion/interaction detail; stack specifics NOT VERIFIED. — [Paralect](https://www.paralect.com/skills/top-design-skills)

### Inferences
- For a vibe-coder audience (typically Next.js/React + Tailwind + shadcn, sometimes plain HTML or mobile), Impeccable and frontend-design work without adaptation. taste-skill 2.5.x injects its own CSS/JS kit into the project's public folder, which is intrusive for an existing app.
- ui-ux-pro-max's Tailwind default could nudge non-Tailwind projects toward Tailwind unless the stack is stated.

### Gaps
- No evidence gathered on how well each skill respects an existing shadcn/Tailwind design-token setup in practice.

---

## 6. Known complaints (bloat, slowness, opinionated, same-looking output, abandonment, trust)

### Takeaway
Nothing is abandoned — all four are very actively committed to in November 2026. The complaints are: taste-skill = slow/expensive, churny, marketing-only; Impeccable = operational friction (installer, Windows AV flags, hooks, setup step), "sites still look alike"; frontend-design = recognisable house style and vagueness; ui-ux-pro-max = generic output and large context.

### Cited Findings
- **taste-skill** — cost: author-stated 30–45 min and "a few hundred thousand tokens" per full run ([CHANGELOG](https://github.com/Leonxlnx/taste-skill/blob/main/CHANGELOG.md)); UX Planet test (SEARCH SNIPPET ONLY): ~30% of daily quota, ~3x frontend-design ([UX Planet](https://uxplanet.org/i-tested-3-claude-code-skills-for-web-design-which-one-is-best-521137220dc1)). Scope: "not meant for dashboards or app UI" ([Paralect](https://www.paralect.com/skills/top-design-skills)); app-screen pipeline removed in 2.5.0 ([CHANGELOG](https://github.com/Leonxlnx/taste-skill/blob/main/CHANGELOG.md)). Didn't change an existing page's design in Subframe's test; "Its curated directions are a shared default, not personal taste" ([Subframe](https://www.subframe.com/tips/best-claude-code-skills-for-ui-design)). Issues (titles READ DIRECTLY): #106 "How to force agent 100% obey the skill ?", #28 "No matching skills found for: taste", #48 "[phantomstars] Fake engagement detected on this repository"; changelog admits a long test session "had left tens of GB in the temp" folder from Chrome profiles (fixed). 87 issues total, 13 open. — [issues](https://github.com/Leonxlnx/taste-skill/issues?q=is%3Aissue+sort%3Acomments-desc)
- **Impeccable** — "Sites built with it still look alike. Some find it too opinionated for established apps" ([Subframe](https://www.subframe.com/tips/best-claude-code-skills-for-ui-design)); "More moving parts to learn, and it needs an init step per project" ([Claude Code Club](https://www.claudecodeclub.ai/free-resources/claude-design-skills)); "Needs Node 22.12+. Generates `.impeccable/` artifacts… Hooks need per-harness trust" ([Bitdoze](https://www.bitdoze.com/best-ai-skills-for-web-design/), Aug 2026 — README now says Node only for npx). Issue titles READ DIRECTLY: #740 "ESET flags Windows binary as a trojan" (closed 2026-09-06), #814 "Flagged by Windows Security" (closed 2026-10-04), #857 install HTTP 404 (closed 2026-10-15), #691 installer invalid zip, #744 4.2.1 regression, #304 "live-server endpoint leaks bearer token (security)" (closed 2026-07-24). ~46 open / ~546 total issues — high volume but being closed. Detector misses some tells (HN bargainbin, 2026-09-02). — [issues](https://github.com/pbakaus/impeccable/issues?q=is%3Aissue+sort%3Acomments-desc); [HN 49533455](https://news.ycombinator.com/item?id=49533455)
- **frontend-design** — recognisable output and vagueness (HN quotes in §1); "Never asks for a reference… pulls output toward Anthropic's own look" ([Subframe](https://www.subframe.com/tips/best-claude-code-skills-for-ui-design)); "The agent still invents copy, clients and prices" ([Paralect](https://www.paralect.com/skills/top-design-skills)); font banning is "a band-aid" ([Composio](https://composio.dev/content/top-design-skills)).
- **ui-ux-pro-max** — "most conventional page in the test… unverified '6,000+ designers' logo strip" ([Paralect](https://www.paralect.com/skills/top-design-skills)); "Largest context footprint when triggered" ([Bitdoze](https://www.bitdoze.com/best-ai-skills-for-web-design/)); copies/forks on third-party registries have been security-flagged (not the canonical repo, which reportedly passed Snyk) — SEARCH SNIPPET ONLY ([tessl](https://tessl.io/registry/skills/github/nextlevelbuilder/ui-ux-pro-max-skill); [clawhub](https://clawhub.ai/hayasam/ui-ux-pro-max-3)).
- **General** — "Skills overlap and contradict each other"; "Each popular skill develops a recognizable style of its own" ([Subframe](https://www.subframe.com/tips/best-claude-code-skills-for-ui-design)); "Skills are free amplifiers of existing taste" ([Bitdoze](https://www.bitdoze.com/best-ai-skills-for-web-design/)).

### Inferences
- "Produces visibly better UI quickly" (Revive's requirement) argues against taste-skill 2.5.x as the default (slow by design) and for Impeccable's targeted commands (`critique`/`polish`/`bolder` on one component) or frontend-design.
- Impeccable's Windows antivirus flags and install failures are the kind of friction that hits non-expert vibe coders hardest; Revive would need a fallback path (frontend-design) when the engine cannot run. Impeccable's own SKILL.md already defines a "Launcher unavailable" fallback, which helps.
- Plain statement: **no candidate is clearly good on all of quality + speed + bundle-safety.** The honest shortlist is Impeccable (best results, operational baggage), frontend-design (safe, modest results), taste-skill (owner's preference; current version mismatched to app-UI revival, v1 is bundle-friendly but stale).

### Gaps
- No direct user complaints from Reddit/X/Threads could be read; complaint evidence is from blogs, issue titles (bodies not read) and a handful of HN comments.
- Token/context footprint of each skill in a real session was not measured.
