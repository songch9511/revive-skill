# Community consensus on Claude Code Agent Skills, Korean-community picks, and the mechanics of bundling third-party skills (state as of 2026-11-22)

Access legend used on every social/blog item below:
- **READ DIRECTLY** = I opened the page itself (browser pane or fetch) and read the text.
- **READ VIA FETCH-SUMMARY** = the page was fetched and summarised by the fetch tool's small model; I did not see the raw text. Treat numbers as "as reported by the page".
- **SEARCH SNIPPET ONLY** = only the search engine's snippet/summary was seen; the post itself was not opened.

Repo facts (stars, license, last push, archived) come from the GitHub REST API or raw files, queried 2026-11-22, unless marked otherwise.

---

## 1. Which skills and skill packs come up again and again (cross-platform, 2026)?

### Takeaway
Across the 11 recommendation sources I could access, `obra/superpowers` is the only near-universal pick (10 of 11); the next tier is Anthropic's `frontend-design` and `skill-creator`, `garrytan/gstack` (usually "use selectively"), and `mattpocock/skills` (especially the grill/interview and diagnose skills). **Reddit could not be read or searched at all**, so this ranking reflects blogs, X snippets and Korean community posts, not Reddit comment threads.

### Cited Findings

**Mention tally (my count across the 11 sources listed below; S-numbers refer to the source list)**

| Rank | Skill / pack | Mentions | Sources | Repo facts (GitHub API 2026-11-22) |
|---|---|---|---|---|
| 1 | Superpowers | 10/11 | S1,S2,S3,S5,S6,S7,S8,S9,S10,S11 | 323,828 stars, MIT, pushed 2026-11-03 — [obra/superpowers](https://github.com/obra/superpowers) |
| 2 | frontend-design (Anthropic) | 4/11 | S3,S6,S7,S8 | Apache-2.0 per-skill LICENSE.txt — [anthropics/skills](https://github.com/anthropics/skills) |
| 2 | skill-creator (Anthropic) | 4/11 | S2,S3,S6,S8 | Apache-2.0 per-skill LICENSE.txt — [anthropics/skills](https://github.com/anthropics/skills) |
| 2 | gstack | 4/11 | S2,S6 (selectively),S9,S11 | 142,296 stars, MIT, pushed 2026-11-22 — [garrytan/gstack](https://github.com/garrytan/gstack) |
| 5 | mattpocock/skills (grill-me / grill-with-docs / diagnose / tdd) | 3/11 (+1 unconfirmed: S2 lists a "grilling" skill whose repo I did not verify) | S4,S7,S8 | 329,859 stars, MIT, pushed 2026-11-19 — [mattpocock/skills](https://github.com/mattpocock/skills) |
| 5 | caveman | 3/11 | S4,S10,S11 | Apache-2.0 LICENSE file; stars NOT VERIFIED (API rate-limited) — [JuliusBrussee/caveman](https://github.com/JuliusBrussee/caveman) |
| 7 | ui-ux-pro-max | 2/11 (+1 unconfirmed in S5) | S1,S2 | 152,563 stars, MIT, pushed 2026-11-22 — [nextlevelbuilder/ui-ux-pro-max-skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill) |
| 7 | Impeccable | 2/11 | S9,S11 | 114,603 stars, Apache-2.0, pushed 2026-11-22 — [pbakaus/impeccable](https://github.com/pbakaus/impeccable) |
| 7 | claude-mem | 2/11 | S1,S8 | 118,877 stars, Apache-2.0, pushed 2026-11-21 — [thedotmack/claude-mem](https://github.com/thedotmack/claude-mem) |
| 7 | marketingskills | 2/11 | S1,S2 | 61,910 stars, MIT, pushed 2026-11-20 — [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills) |
| 7 | humanizer | 2/11 | S2,S5 | 72,039 stars, MIT, pushed 2026-11-19 — [blader/humanizer](https://github.com/blader/humanizer) |
| 7 | last30days-skill | 2/11 | S2,S10 | repo NOT VERIFIED |
| 7 | ponytail | 2/11 | S2,S11 | repo NOT VERIFIED |
| — | addyosmani/agent-skills | 1/11 (S2, rated top tier) plus comparison coverage in S12 | S2 | 119,615 stars, MIT, pushed 2026-11-18 — [addyosmani/agent-skills](https://github.com/addyosmani/agent-skills) |
| — | single mentions | webapp-testing, mcp-builder (S6); context7, web-artifacts-builder, hookdeck/webhook-skills, k-skill (S3); code-simplifier, doc-coauthoring, vercel-react-best-practices, web-design-guidelines, planetscale, TerraShark, spartan-ai-toolkit (S7); context-mode (S8); Remotion (S1); taste-skill, Understand-Anything, archify, rea (S2) | | |

**Source list (date, platform, author, what was said, experience vs filler)**

- **S1** — gymcoding.co "Claude Code 스킬 TOP 5", 2026-07-22, Korean blog by instructor "짐" of a paid-course site (pages carry course purchase links → vendor/educational promotion). Picks: Remotion, Claude Mem, UI/UX Pro Max, Marketing Skills, Superpowers; gives a "제품 출시" combo of Superpowers for planning + Marketing Skills for campaign. READ VIA FETCH-SUMMARY — [gymcoding](https://www.gymcoding.co/articles/claude-skills-top-5-guide)
- **S2** — wikidocs "클로드 스킬 코덱스 스킬 추천 모음 57선", last edited 2026-11-06, Korean online book; author advertises a paid lecture and an open KakaoTalk room on the page (promotional context, but an independent curator, not a skill author). Three-star (★★★) items: marketingskills, last30days-skill, archify, superpowers, agent-skills, rea, grilling, skill-creator, gstack, taste-skill, ponytail, ui-ux-pro-max, Understand-Anything. READ DIRECTLY — [wikidocs 446636](https://wikidocs.net/446636)
- **S3** — wikidocs blog "클로드 스킬 모음 추천 7개", 2026-10-23, author @ai_agent_skill (also sells a "클로드 코드 스킬 100선" e-book). Picks: Superpowers, Context7, Frontend Design, Web Artifacts Builder, Hookdeck Webhook Skills (Stripe/Shopify webhook signature verification and idempotency), K-Skill, Skill Creator. Listicle style, no first-hand usage narrative. READ DIRECTLY — [wikidocs blog 34282](https://wikidocs.net/blog/@ai_agent_skill/34282/)
- **S4** — damoang.net AI당 "6만 스타짜리 Claude Code 스킬 모음, 진짜 쓸 만한지 보기", posted 05.10 (2026), user 지나가던행인이, 3,555 views / 40 likes / 16 comments. After "며칠 써봤습니다" the author narrows mattpocock/skills' 40+ skills to four: `/grill-with-docs`, `/diagnose`, `/improve-codebase-architecture`, `/caveman`; cautions on `/tdd` and `/grill-me`. **Genuine first-hand community review.** READ DIRECTLY — [damoang 2988](https://damoang.net/ai/2988)
- **S5** — Korean LinkedIn post "Claude Code Skill 10만 개 중 진짜 살아남은 4개" (date and original author not identified; the same title surfaces under several profiles). Snippet says 90% of installed skills were never used and four survive in daily use; snippets describe Vercel Find Skills, a 7-stage workflow skill (matches Superpowers), Humanizer, and a design-review skill covering 13 stacks (identity not confirmed). SEARCH SNIPPET ONLY — [LinkedIn](https://kr.linkedin.com/in/bor2i)
- **S6** — buildthisnow.com "The Best Claude Code Skills in 2026", 2026-09-24, author speedy_devv. **Vendor blog** (sells a Claude Code framework). Picks: frontend-design, Superpowers, skill-creator, webapp-testing, mcp-builder, gstack ("keep only the few commands you use"). Says to skip most of Anthropic's example-skills bundle, document-skills unless you generate Office files, and running Superpowers together with gstack or feature-dev. READ VIA FETCH-SUMMARY — [buildthisnow](https://www.buildthisnow.com/blog/guide/mechanics/best-claude-code-skills-2026)
- **S7** — welcomedeveloper.com "The 10 Claude Code Skills I Actually Use at Work", 2026-04-08, first-hand (React Native platform + MySQL side project). Picks: superpowers ("overkill for small fixes"), vercel-react-best-practices, frontend-design, spartan-ai-toolkit, mattpocock/skills (uses `tdd`, `refactoring-plan`), planetscale, web-design-guidelines, doc-coauthoring, code-simplifier, TerraShark. **Experience-backed.** READ VIA FETCH-SUMMARY — [welcomedeveloper](https://www.welcomedeveloper.com/posts/the-10-claude-code-skills/)
- **S8** — Artificial Corner (Substack) "I Tried 33 Claude Code Skills. These Are The Best", 2026-06-01, Frank Andrade. Order: Skill Creator ("the first one I'd install"), Grill Me, Superpowers, Frontend Design, Context Mode, Claude Mem. Names none of the 27 rejected skills → partly listicle. READ VIA FETCH-SUMMARY — [artificialcorner](https://artificialcorner.com/p/best-claude-code-skills)
- **S9** — X post by Kenny Rogers, "My March 2026 Claude Code Skill Stack" (March 2026): Superpowers, gstack, Impeccable as daily stack; Impeccable called the most helpful for making LLM-built UIs look good. SEARCH SNIPPET ONLY — [x.com/KenTheRogers](https://x.com/KenTheRogers/status/2035056372560404772?lang=en)
- **S10** — Charlie Hills Substack note listing 22 skills; says he does not use them all daily and that superpowers, caveman and last30days get the most use. Date not captured. SEARCH SNIPPET ONLY — [substack note](https://substack.com/@charliehills/note/c-302629554)
- **S11** — X post by Leonard Rodman "22 Claude Skills You Should Install Today": Superpowers, GStack ("23 skills in one setup"), Caveman, Ponytail, Codex, I-Have-ADHD; search summary also attributes Impeccable "for final UI polish". Date not captured. Listicle filler (22-item list, no usage evidence). SEARCH SNIPPET ONLY — [x.com/RodmanAi](https://x.com/RodmanAi/status/2083554201268109345)
- **S12 (comparison, not a recommendation list)** — dbggr.dev "Agent skill libraries compared: Superpowers vs gstack vs pstack", published 2026-10-14, updated 2026-11-19; the byline and fact-checker are self-declared AI agents. Compares Superpowers (15 skills), gstack (57), pstack (54), mattpocock/skills (27), addyosmani/agent-skills (25), anthropics/skills (19), Vercel (9), Microsoft (197), Trail of Bits (83). READ VIA FETCH-SUMMARY — [dbggr](https://dbggr.dev/articles/agent-skill-libraries-compared/)

**Other cross-cutting signals**
- An X thread by 数字游民Jarod compares "Superpowers, gstack and Compound Engineering" as the three Claude Code "super plugins" (date not captured). SEARCH SNIPPET ONLY — [x.com/jarodise](https://x.com/jarodise/status/2038427720473039222)
- TechCrunch (2026-03-17) reports gstack went viral on X and Product Hunt with ~20,000 stars within days, and also drew criticism: founder Sherveen Mashayekhi argued it only got attention because the author is YC's CEO, and vlogger Mo Bitar's video "AI is making CEOs delusional" called it essentially prompts in a text file that developers already build for themselves. READ VIA FETCH-SUMMARY — [TechCrunch](https://www.techcrunch.com/2026/03/17/why-garry-tans-claude-code-setup-has-gotten-so-much-love-and-hate/)
- The damoang reviewer makes the same star-inflation point about mattpocock/skills: a large share of stars is influencer reach, and he guesses the same repo by an unknown author would have "5천~1만 스타". READ DIRECTLY — [damoang 2988](https://damoang.net/ai/2988)
- Star counts for other frequently named repos (GitHub API 2026-11-22): affaan-m/ECC 308,451 (MIT) — [repo](https://github.com/affaan-m/ECC); multica-ai/andrej-karpathy-skills 234,936 (no license) — [repo](https://github.com/multica-ai/andrej-karpathy-skills); anthropics/skills 198,564 — [repo](https://github.com/anthropics/skills); ComposioHQ/awesome-claude-skills 80,020 — [repo](https://github.com/ComposioHQ/awesome-claude-skills); hesreallyhim/awesome-claude-code 58,543 — [repo](https://github.com/hesreallyhim/awesome-claude-code); sickn33/agentic-awesome-skills 50,111 — [repo](https://github.com/sickn33/agentic-awesome-skills); anthropics/claude-plugins-official 47,920 — [repo](https://github.com/anthropics/claude-plugins-official); wshobson/agents 42,781 — [repo](https://github.com/wshobson/agents); vercel-labs/skills (the `npx skills` CLI) 40,375 — [repo](https://github.com/vercel-labs/skills).
- `gsd-build/get-shit-done` (64,116 stars, MIT) is **archived**, last push 2026-05-31 — [repo](https://github.com/gsd-build/get-shit-done); yet blog guides still describe a "gstack → GSD → Superpowers" combination (SEARCH SNIPPET ONLY) — [dev.to/imaginex](https://dev.to/imaginex/a-claude-code-skills-stack-how-to-combine-superpowers-gstack-and-gsd-without-the-chaos-44b3)

### Inferences
- Superpowers is the safe "consensus" answer for a workflow/discipline layer; it is named by independent first-hand users (S7), Korean curators (S1–S3) and X posters (S9–S11) alike.
- The second tier splits by purpose rather than competing: Anthropic `frontend-design` / Impeccable / ui-ux-pro-max for design; mattpocock grill + diagnose for alignment and debugging; `skill-creator` as a meta tool; marketingskills for copy.
- Experience-backed sources (S4, S7, the 칼쓰뎅 comment in S4) recommend *individual skills picked out of packs*, whereas listicles (S11, 22-item lists) recommend whole packs. For Revive's "one skill per slot" design the experience-backed pattern is the more relevant one.
- Star counts are a weak quality signal here; two independent sources (TechCrunch, damoang) attribute a large share of gstack's and mattpocock/skills' stars to author fame.

### Gaps
- **Reddit (r/ClaudeAI, r/ClaudeCode, r/vibecoding): no data.** The search tool refuses the reddit.com domain, direct JSON fetch returned HTTP 403, and the browser pane blocks reddit.com. No Reddit post is cited anywhere in these notes; mention counts therefore exclude Reddit entirely.
- **YouTube: no video was opened**; a search for 2026 "best Claude Code skills" videos returned only blog roundups. The only video reference is Mo Bitar's, second-hand via TechCrunch.
- **Threads: no post surfaced** in any search (threads.net is also blocked for the search tool).
- X posts are snippet-only; like counts, exact dates (S10, S11) and reply sentiment were not captured.
- The tally is small (11 sources) and skewed toward blogs with something to sell (S1, S3, S6). It should be presented as indicative, not as a measured ranking.

---

## 2. What do Korean-language communities recommend (especially 바이브코딩 → 출시/수익화), and which skills are Korean-made?

### Takeaway
Korean sources echo the global list (Superpowers, gstack, ui-ux-pro-max, marketingskills, mattpocock grill/diagnose) and add Korea-specific items: `NomaDamas/k-skill`, a `korean-privacy-terms` skill for 개인정보처리방침/약관 at launch, and Korean-made harnesses such as oh-my-claudecode. I found no Korean source that recommends a payment (토스페이먼츠 등) or 수익화 skill by name.

### Cited Findings
- The wikidocs guidebook has a dedicated "08부 바이브코딩 스킬 모음" (last edited 2026-10-16) ordered along the path from idea to public release: gstack (기획부터 배포까지 역할별 명령, ★★★), taste-skill (뻔한 화면을 막는 디자인 규칙, ★★★), korean-privacy-terms (한국어 처리방침과 약관 초안 + 동의 모달/쿠키 배너, ★☆☆), ponytail (과잉 구현 방지, ★★★), ui-ux-pro-max (★★★), Understand-Anything (코드베이스 지식 그래프, ★★★), open-code-review (공개 전 변경 코드 리뷰, ★★☆), run-hackathon. READ DIRECTLY — [wikidocs 435360](https://wikidocs.net/435360)
- The same page warns that korean-privacy-terms only produces drafts, that the repo's Korean terms-of-service template file was empty when checked on 2026-09-22, and that output needs expert review. READ DIRECTLY — [wikidocs 435360](https://wikidocs.net/435360)
- It cross-references superpowers and addyosmani-style agent-skills as the development-process layer to use alongside the vibe-coding set. READ DIRECTLY — [wikidocs 435360](https://wikidocs.net/435360)
- The 57-skill list tags several skills for "1인 사업자": yc-office-hours (만들기 전에 묻는 사업 멘토), marketingskills, humanizer, blog-post, korean-privacy-terms, ponytail, Understand-Anything. READ DIRECTLY — [wikidocs 446636](https://wikidocs.net/446636)
- gymcoding's "제품 출시" example chains Superpowers (plan) with Marketing Skills (campaign, "신제품 출시 이메일 5통"); the page does not use the word 바이브코딩 or 수익화. READ VIA FETCH-SUMMARY — [gymcoding](https://www.gymcoding.co/articles/claude-skills-top-5-guide)
- A second gymcoding article recommends design-oriented skills named find-animation-opportunities, pick-ui-library, kill-ai-slop and prototype. SEARCH SNIPPET ONLY — [gymcoding 5선](https://www.gymcoding.co/articles/claude-code-skills-5-practical-guide)
- damoang community: the reviewer's advice is "40개 다 깔자" 보다 "4개 핵심부터 시작"; commenter 칼쓰뎅 reports two months on a ~40,000-line project running `to-prd → grill-with-docs → to-issues → tdd` across 140+ issues and says the "fix here, break there" cycle largely stopped after adopting the skills (used with Codex). READ DIRECTLY — [damoang 2988](https://damoang.net/ai/2988)
- A Korean explainer advises beginners to start with Superpowers and add gstack once role-based work grows. SEARCH SNIPPET ONLY — [ssockssock](https://ssockssock.com/claude-code-upgrade-tools/)
- GeekNews weekly 2026-13 introduced gstack as a Skills collection usable in Claude Code or Codex, alongside a tool called Harness. SEARCH SNIPPET ONLY — [news.hada.io weekly 202613](https://news.hada.io/weekly/202613)
- A GeekNews item explains that the skill `description` field is what the model uses to decide when to invoke a skill. SEARCH SNIPPET ONLY — [news.hada.io topic 27640](https://news.hada.io/topic?id=27640)
- A Korean blog (2026-05-10) reads the simultaneous rise of mattpocock/skills, karpathy-skills, SuperClaude and awesome-claude-code as skills becoming the primary unit of agent engineering, and relays Matt Pocock's criticism that full-process frameworks (GSD, BMAD, Spec-Kit) take control away from the user. READ VIA FETCH-SUMMARY — [ice-ice-bear](https://ice-ice-bear.github.io/ko/posts/2026-05-10-claude-code-skills-explosion/)
- A Korean blog on skills.sh notes opaque quality control and a proliferation of look-alike skills on skill marketplaces. SEARCH SNIPPET ONLY — [wikidocs blog jaehong 9418](https://wikidocs.net/blog/@jaehong/9418/)

**Korean-made or Korea-specific skills and packs (repo facts: GitHub API / raw files 2026-11-22)**

| Repo | What it is | Stars | License | Last push |
|---|---|---|---|---|
| [NomaDamas/k-skill](https://github.com/NomaDamas/k-skill) | "한국인을 위한 스킬 모음집" — KTX/SRT, 공공데이터, 쇼핑 등 국내 서비스 연동; ships a single-plugin marketplace | 8,488 | MIT | 2026-11-18 |
| [Yeachan-Heo/oh-my-claudecode](https://github.com/Yeachan-Heo/oh-my-claudecode) | Multi-agent orchestration harness; listed as "올인원 프레임워크" in the Korean awesome list | 40,999 | MIT | 2026-11-21 |
| [revfactory/harness](https://github.com/revfactory/harness) | Meta-skill that designs agent teams and generates their skills | 9,389 | Apache-2.0 | 2026-09-28 |
| [modu-ai/moai-adk](https://github.com/modu-ai/moai-adk) | SPEC-driven development harness for Claude Code | 1,259 | Apache-2.0 | 2026-11-22 |
| [ww-w-ai/bkit-claude-code](https://github.com/ww-w-ai/bkit-claude-code) (redirected from popup-studio-ai/bkit-claude-code) | "bkit Vibecoding Kit — PDCA methodology" | 606 | Apache-2.0 | 2026-11-19 |
| [team-attention/plugins-for-claude-natives](https://github.com/team-attention/plugins-for-claude-natives) | Claude Code plugins for power users | 832 | MIT | 2026-04-20 |
| [DaleSeo/korean-skills](https://github.com/DaleSeo/korean-skills) | Korean grammar check / 윤문 skills, installable as a plugin marketplace | NOT VERIFIED | MIT (LICENSE file) | NOT VERIFIED |
| [bear2u/my-skills](https://github.com/bear2u/my-skills) | Personal Korean skill collection ("한국어 스킬 21개" per the awesome list) | NOT VERIFIED | NOT VERIFIED | search result flagged it as stale |
| [J-nowcow/awesome-korean-agent-skills](https://github.com/J-nowcow/awesome-korean-agent-skills) | Curated list of Korean agent skills by function; README states it is "100% AI 에이전트가 자동으로 운영"; last updated 2026-11-21 | NOT VERIFIED | CC0-1.0 | — |

- The Korean awesome list has categories directly matching Revive slots: 디버깅 & 빌드 에러 (10+), 보안 감사 (11+), 웹 프론트엔드 (21+), DevOps & 배포 (17+), 코드 리뷰 (26+). — [awesome-korean-agent-skills README](https://github.com/J-nowcow/awesome-korean-agent-skills)

### Inferences
- The Korean "vibe coding to launch" canon, as far as one curated book defines it, is: gstack for the product-team frame, a taste/design skill, a "write less code" guard (ponytail), a code-comprehension aid, a pre-release review, and Korean legal boilerplate. The legal-document step is the one item with no equivalent in English lists and is directly relevant to a Korean first-paid-customer flow.
- Payment integration appears to be an unserved slot in Korean recommendations: the only payment-adjacent skill named in any Korean source is the English-language Hookdeck webhook pack (Stripe/Shopify), not a 토스페이먼츠/포트원 skill.
- Korean curators that monetise courses (gymcoding, wikidocs authors) dominate search results; the damoang thread is the only clearly non-commercial, experience-based Korean source found.

### Gaps
- No Korean Threads, X, YouTube, velog, Discord or 오픈카톡 write-up was opened. A velog post "Claude Code × Superpowers: 39k 스타 최강 플러그인 체험기" surfaced in search but was not read — [velog](https://velog.io/@takuya/claude-code-superpowers-guide).
- Whether moai-adk, bkit and revfactory/harness are Korean-made is my background understanding plus Korean-language context; **NOT VERIFIED** from the repos themselves.
- The repos behind `korean-privacy-terms`, `taste-skill`, `ponytail`, `yc-office-hours` and `open-code-review` were not identified (the wikidocs chapter pages that carry install commands were not opened).
- No Korean-made payment (토스페이먼츠, 포트원, 카카오페이) or 수익화 skill was found; one targeted search returned nothing. This is "not found", not "does not exist".

---

## 3. Which skills do people stop using, and how many is "too many"?

### Takeaway
Reported reasons for dropping or trimming skills are token cost, overlapping workflow packs, and heavyweight packs used wholesale; nobody gives a hard number, but experience-based sources converge on a handful (about 3–5 active picks, one workflow layer at most). Claude Code itself enforces a ceiling: the skill listing gets 1% of the context window and the least-invoked skills lose their descriptions first.

### Cited Findings

**Official mechanics (Claude Code docs)**
- The listing of skill names and descriptions is budgeted at 1% of the model's context window; on overflow Claude Code "drops descriptions starting with the skills you invoke least", which removes the keywords needed for matching. — [Claude Code docs: skills](https://code.claude.com/docs/en/skills.md)
- Each entry's combined `description` + `when_to_use` is capped at 1,536 characters regardless of budget (configurable with `skillListingMaxDescChars`); the budget can be raised with `skillListingBudgetFraction` or `SLASH_COMMAND_TOOL_CHAR_BUDGET`; low-priority skills can be set to `"name-only"` in `skillOverrides`. — [Claude Code docs: skills](https://code.claude.com/docs/en/skills.md)
- `disable-model-invocation: true` means Claude cannot invoke the skill on its own and its description is not in context; the user can still run `/name`. — [Claude Code docs: skills](https://code.claude.com/docs/en/skills.md)
- An invoked skill's content stays in the conversation for later turns; after auto-compaction only the first 5,000 tokens of each invoked skill are re-attached, within a shared 25,000-token budget filled from the most recently invoked skill. — [Claude Code docs: skills](https://code.claude.com/docs/en/skills.md)
- The docs recommend keeping `SKILL.md` under 500 lines. — [Claude Code docs: skills](https://code.claude.com/docs/en/skills.md)
- Auditing tools: `/doctor` estimates listing cost, `/skill-doctor` (v2.1.252+) reports per-skill context cost and usage and flags never-invoked skills, and the Skills row in `/context` shows the listing size after the budget is applied. — [Claude Code docs: skills](https://code.claude.com/docs/en/skills.md)

**User and reviewer reports**
- A staff engineer with 181 installed skills (gstack, 36 marketingskills, 42 wondelai skills, 14 superpowers, claude-mem and others) cut the active set to 43 and moved 139 into an on-demand "vault", reporting about 96% fewer tokens per session; the per-session figure (1.18M tokens) is his own bytes÷4 estimate. Posted April 19, edited May 8 (year not shown). READ VIA FETCH-SUMMARY — [dev.to/pponali](https://dev.to/pponali/how-i-cut-claude-code-token-consumption-by-96-with-the-skill-vault-pattern-9d1)
- A Korean LinkedIn post says roughly 90% of installed skills were never used and only four survived daily use. SEARCH SNIPPET ONLY — [LinkedIn](https://kr.linkedin.com/in/bor2i)
- damoang reviewer: start with four core skills rather than all 40+; `/tdd` "무조건 호출하면 워크플로우가 느려져요" and suits neither prototyping nor visual UI work; `/grill-me` can become a patience test; the pack's setup step demands up-front decisions (issue tracker, labels, doc locations). READ DIRECTLY — [damoang 2988](https://damoang.net/ai/2988)
- First-hand author (S7): Superpowers is "overkill for small fixes"; he left `frontend-design` unused for two months; his starter set is four skills, adding more only as work requires. READ VIA FETCH-SUMMARY — [welcomedeveloper](https://www.welcomedeveloper.com/posts/the-10-claude-code-skills/)
- Vendor blog (S6): a "minimum viable set" of three plugins plus webapp-testing; remove unused skills instead of raising the listing budget; do not run Superpowers with gstack or with feature-dev because both claim the same plan/build/review steps; invoking three gstack skills in one session can add about 50,000 tokens. READ VIA FETCH-SUMMARY — [buildthisnow](https://www.buildthisnow.com/blog/guide/mechanics/best-claude-code-skills-2026)
- Comparison article (S12): gstack has 57 skills, 36 of them over 500 lines, compiles binaries, downloads Chromium and adds a section to CLAUDE.md; recommends "one workflow library at most, or none" and cherry-picking single skills with pinned versions. READ VIA FETCH-SUMMARY — [dbggr](https://dbggr.dev/articles/agent-skill-libraries-compared/)
- Same article, estimated always-on cost: Superpowers ~1,500 tokens (session-start hook injects 3,405 characters), gstack ~1,200 plus a CLAUDE.md section, mattpocock/skills ~570 (16 of 27 skills manual-only), addyosmani/agent-skills ~2,400, anthropics/skills ~2,400 for all 19. READ VIA FETCH-SUMMARY — [dbggr](https://dbggr.dev/articles/agent-skill-libraries-compared/)
- Same article: addyosmani/agent-skills removed its session-start injection on 15 September, citing roughly 3.5k wasted cache-creation tokens per session (a maintainer decision, not a user report). READ VIA FETCH-SUMMARY — [dbggr](https://dbggr.dev/articles/agent-skill-libraries-compared/)
- Same article relays research (I did not open the papers): SkillsBench (arXiv 2604.04323) — Claude Opus 4.6 passed 51.2% of tasks with hand-picked skills, 35.4% with none, 38.4% when retrieving from 34,198 public skills; a web-development study (arXiv 2608.23067) — 31 public skills cut pass rates by 1.3–4.2% and raised token cost 72–394%; Vercel's own eval found its skill "never invoked in 56% of eval cases". READ VIA FETCH-SUMMARY — [dbggr](https://dbggr.dev/articles/agent-skill-libraries-compared/)
- A hands-on review found Superpowers makes code quality more stable but is token-heavy, and advises native Claude Code for quick scripts. SEARCH SNIPPET ONLY — [zerofuturetech](https://zerofuturetech.substack.com/p/i-deep-tested-three-claude-code-harness)
- Korean blog (S3): installing too many skills shortens descriptions and lowers automatic selection accuracy; rules that must hold every turn belong in CLAUDE.md, not a skill. READ DIRECTLY — [wikidocs blog 34282](https://wikidocs.net/blog/@ai_agent_skill/34282/)
- Official troubleshooting agrees on triggering: a skill that must fire every time should be a hook; a skill that fires too often needs a narrower description or `disable-model-invocation: true`. — [Claude Code docs: skills](https://code.claude.com/docs/en/skills.md)

### Inferences
- "Too many" is better expressed as a budget than a count. On a 200k-context model, 1% is about 2,000 tokens, roughly 8,000 characters at ~4 chars/token — room for only about five descriptions at the 1,536-character cap, or a few dozen one-line descriptions. A Revive bundle of 6–12 skills fits only if every bundled description is short. (Arithmetic is mine; the 1% and 1,536 figures are from the docs.)
- Because the least-invoked skills lose descriptions first, rarely used Revive slots (payment, pre-launch check) are exactly the ones that would silently stop auto-triggering in a user's already crowded setup. An orchestrator that routes explicitly by name is more robust than relying on description matching.
- `disable-model-invocation: true` would remove listing cost but, per the docs' wording, also stops Claude (and therefore an orchestrator skill) from invoking the skill itself; it is not a free fix for a routed design. Whether an orchestrator can instead read a bundled SKILL.md by path is untested here.
- The clearest conflict pattern is two "mandatory process" packs at once (Superpowers + gstack, Superpowers + feature-dev). Revive should bundle at most one process layer, or none, and take single skills from the others.
- Heavy packs with install-time side effects (gstack: binaries, Chromium, CLAUDE.md edits) are poor candidates for vendoring into another plugin; single-file skills are good ones.

### Gaps
- No first-person "I uninstalled X because…" post from Reddit, X or Threads could be read; the "stopped using" evidence is blogs and one Korean forum thread.
- No source reports measured triggering-failure rates for a named pack in real use; the 56% non-invocation figure is Vercel's own eval, relayed second-hand.
- The arXiv papers and the Superpowers v6.0.0 efficiency claims were not verified at source.
- No user-stated numeric threshold ("more than N skills breaks things") was found.

---

## 4. How do plugins package and bundle skills — copy, reference, dependency, or submodule?

### Takeaway
A plugin can ship its own skills (`skills/<name>/SKILL.md`), and it can also declare `dependencies` on other plugins, including cross-marketplace ones if the root marketplace allowlists them; a marketplace entry can also point at someone else's repo (`github` / `url` / `git-subdir`, pinnable by `sha`) instead of copying files. In practice Anthropic's official directory mostly references upstream repos with pinned SHAs, while community mega-collections vendor everything by relative path; none of the marketplaces I checked uses git submodules.

### Cited Findings

**Packaging basics (official docs)**
- A plugin's skills live in `skills/`, one `<name>/SKILL.md` per skill; the manifest `.claude-plugin/plugin.json` is optional and `name` is its only required key. — [Plugin manifest reference](https://code.claude.com/docs/en/plugins-reference)
- The manifest `skills` key takes a path or array of paths and *adds to* the default `skills/` scan. — [Plugin manifest reference](https://code.claude.com/docs/en/plugins-reference)
- Every component is namespaced under the plugin name; plugin skills are invoked as `/plugin-name:skill-name` and do not collide with standalone skills. — [Claude Code docs: skills](https://code.claude.com/docs/en/skills.md)
- Every component path must start with `./` and resolve inside the plugin root; a path containing `..` fails validation as a traversal attempt. — [Plugin manifest reference](https://code.claude.com/docs/en/plugins-reference)
- A `CLAUDE.md` at the plugin root is not loaded as context; instructions must go in a skill. — [Plugin manifest reference](https://code.claude.com/docs/en/plugins-reference)
- A plugin with a top-level `bin/` directory is not installed by claude.ai or Cowork. — [Plugin manifest reference](https://code.claude.com/docs/en/plugins-reference)
- Plugin names starting with `claude-`, `anthropic-`, `anthropics-` or `cc-plugin-` are reserved and error in validation ("revive" is unaffected). — [Plugin manifest reference](https://code.claude.com/docs/en/plugins-reference)
- A marketplace is a repo with `.claude-plugin/marketplace.json` listing plugins and where to fetch each; users install with `claude plugin install <entry-name>@<marketplace>`; users who install from a hosted marketplace get a copy in the plugin cache. — [Create a marketplace](https://code.claude.com/docs/en/plugin-marketplaces)

**Dependencies (official docs)**
- `dependencies` in `plugin.json` lists plugins that must be enabled; each entry is `"name"`, `"name@marketplace"`, or `{ "name", "marketplace", "version" }`; bare names resolve against the declaring plugin's own marketplace. — [Plugin dependencies](https://code.claude.com/docs/en/plugins/dependencies.md)
- The docs describe a "bundle" plugin whose manifest contains only a `name` and a `dependencies` array, so users install a curated set with one command. — [Plugin dependencies](https://code.claude.com/docs/en/plugins/dependencies.md)
- By default Claude Code does not install a dependency from a different marketplace unless the user already has it installed and enabled at the same scope; to allow it, the *root* marketplace must list the target in `allowCrossMarketplaceDependenciesOn`. — [Plugin dependencies](https://code.claude.com/docs/en/plugins/dependencies.md)
- If a cross-marketplace dependency is declared in `plugin.json` without the allowlist, "the install completes without the dependency and your plugin then fails to load"; declared in the marketplace entry, the install is refused with an explanatory message. — [Plugin dependencies](https://code.claude.com/docs/en/plugins/dependencies.md)
- Version constraints are semver ranges resolved against git tags named `<plugin-name>--v<version>` on the repo hosting the dependency, so the *dependency's maintainer* must tag releases; without a constraint the dependency tracks the latest version its marketplace provides. — [Plugin dependencies](https://code.claude.com/docs/en/plugins/dependencies.md)
- Missing declared dependencies are auto-installed on `claude plugin install`, `/reload-plugins`, marketplace auto-update and `claude plugin update` (the last requires v2.1.319+). — [Plugin dependencies](https://code.claude.com/docs/en/plugins/dependencies.md)
- If a dependency is disabled, the dependent plugin is disabled at the next load with an error telling the user to enable it or remove the dependency. — [Plugin dependencies](https://code.claude.com/docs/en/plugins/dependencies.md)

**Referencing upstream from your own marketplace (official docs)**
- Plugin source types: relative path, `github` (`repo`, `ref`, `sha`), `url` (any git URL), `git-subdir` (`url`, `path`, `ref`, `sha`; sparse checkout of one subdirectory of another repo), `npm`, `archive` (zip + `sha256`), `command`. — [Marketplace reference](https://code.claude.com/docs/en/plugins/marketplace-reference.md)
- `sha` is a full 40-character commit SHA; when both `ref` and `sha` are set Claude Code checks out `sha`. — [Marketplace reference](https://code.claude.com/docs/en/plugins/marketplace-reference.md)
- If the fetched plugin has no `plugin.json`, the marketplace entry *is* the manifest and may declare `skills`, `commands`, `mcpServers` and so on; if it has one, `strict: true` (default) appends the entry's component fields and `strict: false` with any component field is a load-failing conflict. — [Marketplace reference](https://code.claude.com/docs/en/plugins/marketplace-reference.md)
- When an entry whose `source` is the marketplace root lists specific `skills` subdirectories, only those load and the default `skills/` scan is skipped. — [Plugin manifest reference](https://code.claude.com/docs/en/plugins-reference)
- Git submodules are supported: when cloning a marketplace repo Claude Code fetches only the submodules that hold plugin files (v2.1.295+; earlier versions fetch all and can hit the 120 s clone timeout). — [Marketplace reference](https://code.claude.com/docs/en/plugins/marketplace-reference.md)
- A marketplace added by direct `url` to a `marketplace.json` cannot use relative-path sources. — [Marketplace reference](https://code.claude.com/docs/en/plugins/marketplace-reference.md)

**What existing marketplaces actually do (raw `marketplace.json` files read 2026-11-22)**
- `anthropics/claude-plugins-official`: 317 entries — 163 `url`, 98 `git-subdir`, 55 relative-path, 1 `command`; external entries are pinned, e.g. a `git-subdir` entry carrying both `ref: "v1.5.5"` and a `sha`. No entry declares `dependencies`. → predominantly **reference upstream with pinned SHA**. — [marketplace.json](https://github.com/anthropics/claude-plugins-official/blob/main/.claude-plugin/marketplace.json)
- Some official entries act as the manifest for upstream skill repos by listing `skills` paths (e.g. `amd-skills`, `box`). — [marketplace.json](https://github.com/anthropics/claude-plugins-official/blob/main/.claude-plugin/marketplace.json)
- `obra/superpowers-marketplace`: 10 entries, all `url` sources pointing at separate repos, unpinned (e.g. `https://github.com/obra/superpowers.git`). → **reference upstream, track latest**. — [marketplace.json](https://github.com/obra/superpowers-marketplace/blob/main/.claude-plugin/marketplace.json)
- `anthropics/skills`: marketplace `anthropic-agent-skills` with 5 plugins, all `source: "./"`, `strict: false`, each listing a subset of `./skills/*` (document-skills = xlsx, docx, pptx, pdf; example-skills = 12 skills incl. frontend-design, skill-creator, webapp-testing, mcp-builder). → **one repo sliced into several plugins**. — [marketplace.json](https://github.com/anthropics/skills/blob/main/.claude-plugin/marketplace.json)
- `wshobson/agents`: 93 entries — 91 relative-path, 2 `git-subdir`. — [marketplace.json](https://github.com/wshobson/agents/blob/main/.claude-plugin/marketplace.json)
- `alirezarezvani/claude-skills`: 121 entries, all relative-path. → **vendored in-repo**. — [marketplace.json](https://github.com/alirezarezvani/claude-skills/blob/main/.claude-plugin/marketplace.json)
- Single-plugin, self-hosted marketplaces (source `./`): mattpocock/skills, obra/superpowers, Yeachan-Heo/oh-my-claudecode, NomaDamas/k-skill, coreyhaines31/marketingskills, nextlevelbuilder/ui-ux-pro-max-skill, whawkinsiv/solo-founder-skills; pbakaus/impeccable uses `./plugin`; addyosmani/agent-skills points a `github` source at its own repo. — e.g. [mattpocock marketplace.json](https://github.com/mattpocock/skills/blob/main/.claude-plugin/marketplace.json)
- No `.gitmodules` file exists at the root of wshobson/agents, alirezarezvani/claude-skills, sickn33/agentic-awesome-skills, VoltAgent/awesome-agent-skills or obra/superpowers-marketplace (HTTP 404 on the raw path). — e.g. [wshobson/agents](https://github.com/wshobson/agents)
- None of the 13 marketplace files parsed declares `dependencies` on any entry or sets `allowCrossMarketplaceDependenciesOn`. — e.g. [claude-plugins-official marketplace.json](https://github.com/anthropics/claude-plugins-official/blob/main/.claude-plugin/marketplace.json)
- gstack is installed by `git clone` plus a setup script rather than as a marketplace plugin (its `.claude-plugin/marketplace.json` did not parse as JSON when fetched). — [garrytan/gstack README](https://github.com/garrytan/gstack)
- Outside the plugin system, the `npx skills add <owner/repo>` CLI is the other common distribution route, and copies made by it do not carry hooks. — [vercel-labs/skills](https://github.com/vercel-labs/skills); hook caveat per [dbggr](https://dbggr.dev/articles/agent-skill-libraries-compared/)

### Inferences
- Revive has three workable designs, in increasing order of coupling to upstream:
  1. **Vendor** (copy) each chosen skill into `revive/skills/…`. Skills appear as `revive:<skill>`, work offline, cannot drift, and need license notices kept alongside (see section 5). This is what most community collections do.
  2. **Own marketplace that references upstream**: add entries in Revive's marketplace whose `source` is `github`/`git-subdir` pointing at the upstream repo, pinned by `sha`, and have the Revive plugin list them as bare-name `dependencies`. Because bare names resolve inside Revive's own marketplace, no cross-marketplace allowlist is needed, nothing is copied into Revive's repo, and the upstream plugin keeps its own namespace (e.g. `superpowers:…`). This mirrors the official directory's pattern. (Combination is my reading of the docs; I did not test it.)
  3. **Cross-marketplace dependency** (`"superpowers@superpowers-marketplace"`) with `allowCrossMarketplaceDependenciesOn`. Least control: the user must also have, or be able to reach, that marketplace, and unpinned dependencies move with upstream.
- Version-range pinning via `dependencies` only works if the upstream maintainer publishes `<plugin>--v<version>` tags, which third-party skill authors mostly will not have done; `sha` pinning in Revive's own marketplace entry avoids that requirement.
- Depending on whole packs drags in everything they ship (Superpowers' session-start hook, all 15 skills in the listing). If Revive wants one skill per slot, vendoring single skills (option 1) or an entry that lists only specific `skills` subdirectories of an upstream repo without its own `plugin.json` is the only way to avoid the extra context load.
- Dependencies are rare in the wild (none in 13 marketplaces checked), so user-facing failure modes (dependency disabled → Revive disabled) are less battle-tested than plain vendoring.

### Gaps
- The docs do not document a mechanism for one skill to invoke another plugin's skill directly; how reliably an orchestrator skill routes to `other-plugin:skill` is **NOT VERIFIED**.
- Whether a marketplace entry can cherry-pick `skills` subdirectories from an upstream repo that *does* have its own `plugin.json` (strict-mode append behaviour suggests it only adds, not restricts) was not tested.
- Plugin cache copy semantics (symlinks, files outside the plugin directory) are described on the "plugin loading" page, which I did not open.
- I did not inspect any plugin that vendors *third-party* skills with attribution files, so there is no observed best-practice layout for NOTICE/LICENSE placement inside a bundle.

---

## 5. Licensing norms, Anthropic's own repo, and repackaging disputes

### Takeaway
MIT is the dominant license among popular skill repos, with Apache-2.0 second; several very popular repos have no license at all, and a few use restrictive Creative Commons terms. **Contrary to the assumption in the brief, anthropics/skills as of 2026-11-22 states that the docx/pdf/pptx/xlsx document skills are also Apache-2.0** — I found no source-available / non-redistributable skill in the repo today. I found no documented dispute over repackaged or resold skills.

### Cited Findings

**anthropics/skills (verified from raw files, 2026-11-22)**
- README, verbatim: "Many skills in this repo are open source (Apache 2.0). We've also included the document creation & editing skills … in the `skills/docx`, `skills/pdf`, `skills/pptx`, and `skills/xlsx` subfolders. These are also open source (Apache 2.0)". — [anthropics/skills README](https://github.com/anthropics/skills/blob/main/README.md)
- `LICENSE.txt` begins with "Apache License, Version 2.0" in 18 of 19 skill folders: academy-guide, algorithmic-art, brand-guidelines, canvas-design, claude-api, discernment-nudge, docx, frontend-design, internal-comms, mcp-builder, pdf, pptx, skill-creator, slack-gif-creator, theme-factory, web-artifacts-builder, webapp-testing, xlsx. — e.g. [skills/docx/LICENSE.txt](https://github.com/anthropics/skills/blob/main/skills/docx/LICENSE.txt), [skills/frontend-design/LICENSE.txt](https://github.com/anthropics/skills/blob/main/skills/frontend-design/LICENSE.txt)
- `skills/doc-coauthoring/LICENSE.txt` returns 404 — that one skill has no per-folder license file. — [skills/doc-coauthoring](https://github.com/anthropics/skills/tree/main/skills/doc-coauthoring)
- The repository has no root-level license detected (GitHub API `license: null`); it does contain a `THIRD_PARTY_NOTICES.md`. 198,564 stars, last push 2026-11-16. — [anthropics/skills](https://github.com/anthropics/skills)
- README disclaimer: the skills are "provided for demonstration and educational purposes only". — [anthropics/skills README](https://github.com/anthropics/skills/blob/main/README.md)
- `anthropics/claude-plugins-official` is Apache-2.0 at repo level. — [claude-plugins-official](https://github.com/anthropics/claude-plugins-official)

**License distribution among repos checked (GitHub API `license.spdx_id` or LICENSE file, 2026-11-22)**
- **MIT**: obra/superpowers, garrytan/gstack, addyosmani/agent-skills, mattpocock/skills, nextlevelbuilder/ui-ux-pro-max-skill, coreyhaines31/marketingskills, blader/humanizer, affaan-m/ECC, wshobson/agents, Yeachan-Heo/oh-my-claudecode, NomaDamas/k-skill, alirezarezvani/claude-skills, sickn33/agentic-awesome-skills, VoltAgent/awesome-agent-skills, vercel-labs/skills, gsd-build/get-shit-done, team-attention/plugins-for-claude-natives, EveryInc/compound-engineering-plugin, whawkinsiv/solo-founder-skills, DaleSeo/korean-skills. — e.g. [obra/superpowers](https://github.com/obra/superpowers), [mattpocock/skills](https://github.com/mattpocock/skills), [garrytan/gstack](https://github.com/garrytan/gstack)
- **Apache-2.0**: thedotmack/claude-mem, pbakaus/impeccable, JuliusBrussee/caveman, revfactory/harness, modu-ai/moai-adk, ww-w-ai/bkit-claude-code, anthropics/claude-plugins-official, anthropics/skills (per skill). — e.g. [pbakaus/impeccable](https://github.com/pbakaus/impeccable), [thedotmack/claude-mem](https://github.com/thedotmack/claude-mem)
- **No license detected**: vercel-labs/agent-skills (34,681 stars; no LICENSE at root), multica-ai/andrej-karpathy-skills (234,936 stars), ComposioHQ/awesome-claude-skills (80,020), travisvn/awesome-claude-skills (15,897). — [vercel-labs/agent-skills](https://github.com/vercel-labs/agent-skills), [andrej-karpathy-skills](https://github.com/multica-ai/andrej-karpathy-skills), [ComposioHQ/awesome-claude-skills](https://github.com/ComposioHQ/awesome-claude-skills)
- **Restrictive Creative Commons**: trailofbits/skills is CC-BY-SA-4.0 (share-alike) — [trailofbits/skills](https://github.com/trailofbits/skills); hesreallyhim/awesome-claude-code is CC BY-NC-ND 4.0 (non-commercial, no derivatives) — [LICENSE](https://github.com/hesreallyhim/awesome-claude-code/blob/main/LICENSE)
- **CC0**: J-nowcow/awesome-korean-agent-skills. — [repo](https://github.com/J-nowcow/awesome-korean-agent-skills)
- Of 36 repos with a determinable status: 20 MIT, 8 Apache-2.0 (counting anthropics/skills), 4 none, 2 restrictive CC, 1 CC0, 1 unverified (yayashuxue/solo-founder-playbook has no `LICENSE` at the default path). — counts derived from the repo pages above, e.g. [solo-founder-playbook](https://github.com/yayashuxue/solo-founder-playbook)

**What the common licenses require when redistributing**
- MIT: the copyright notice and permission notice must be included in all copies or substantial portions. — [MIT License text](https://opensource.org/license/mit)
- Apache-2.0 §4: give recipients a copy of the license, mark modified files as changed, retain copyright/attribution notices, and carry forward any NOTICE file contents. — [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0)
- A repository with no license leaves default copyright in place; others have no permission to reproduce, distribute or create derivative works. — [choosealicense.com: No License](https://choosealicense.com/no-permission/)
- `plugin.json` has a `license` field taking an SPDX identifier. — [Plugin manifest reference](https://code.claude.com/docs/en/plugins-reference)

**Disputes and norms**
- A dedicated search for disputes about repackaged or resold skills returned no reported case. — search run 2026-11-22; nearest hit is the attribution-hygiene issue below
- The awesome-claude-code maintainer states the NC-ND license "was adopted to prevent appropriation of the labor of myself and the developers whose work is featured on this list from being used in harmful or predatory ways". — [awesome-claude-code LICENSE](https://github.com/hesreallyhim/awesome-claude-code/blob/main/LICENSE)
- A GitHub issue (Oct 2026) on a kit that adapts third-party MIT and Apache-2.0 skills asks to consolidate attribution: notices were per-file, with no consolidated notice and no license texts kept alongside. SEARCH SNIPPET ONLY — [claude-sdlc-kit issue #12](https://github.com/AlejBlasco/claude-sdlc-kit/issues/12)
- The gstack backlash was about hype and originality ("prompts in a text file"), not licensing. READ VIA FETCH-SUMMARY — [TechCrunch](https://www.techcrunch.com/2026/03/17/why-garry-tans-claude-code-setup-has-gotten-so-much-love-and-hate/)
- A Korean blog notes look-alike skills proliferating on skill marketplaces with opaque quality control. SEARCH SNIPPET ONLY — [wikidocs blog](https://wikidocs.net/blog/@jaehong/9418/)
- Plugins can run hooks and MCP servers outside the sandbox, so reviewers advise reading scripts and hooks and pinning versions before reuse. READ VIA FETCH-SUMMARY — [dbggr](https://dbggr.dev/articles/agent-skill-libraries-compared/)

### Inferences
- Every skill in section 1's top tiers is MIT or Apache-2.0, so vendoring them inside Revive is permitted provided each copy keeps its license text and copyright notice (and, for Apache-2.0 sources such as Impeccable, claude-mem, caveman and Anthropic's skills, any NOTICE content and a note of modifications). A per-skill `LICENSE` file next to each vendored `SKILL.md` plus a root `THIRD_PARTY_NOTICES.md` (the pattern Anthropic's own repo uses) would satisfy both.
- Do not vendor from unlicensed repos (vercel-labs/agent-skills' React/web-design skills, andrej-karpathy-skills) without explicit permission; reference them instead (marketplace entry or install instruction), which distributes nothing.
- trailofbits/skills (CC-BY-SA) would impose share-alike on adapted copies — relevant to the pre-launch security slot; referencing rather than modifying is the lower-risk route.
- The brief's premise about source-available document skills appears to be outdated. Since the document skills are not candidates for any Revive slot anyway, the practical impact is nil, but the final report should not repeat the old claim.
- Absence of disputes plus an explicit "anti-appropriation" license on the largest curated list suggests the norm is social (credit authors, do not resell) rather than litigated. Clear attribution is the cheap way to stay inside that norm.

### Gaps
- **When** the anthropics/skills document-skill license changed (and whether it ever differed) is NOT VERIFIED: the commit-history query hit the GitHub API rate limit. Only the current state was confirmed.
- I confirmed only the first line of each `LICENSE.txt` ("Apache License") plus the full head of the docx file; I did not diff every file against the canonical Apache-2.0 text or read `THIRD_PARTY_NOTICES.md`.
- `doc-coauthoring`'s license is unstated at folder level; whether the README's "many skills" wording covers it is unclear.
- Licenses for JuliusBrussee/caveman and EveryInc/compound-engineering-plugin were read from the LICENSE file only (stars not retrieved).
- No legal source was consulted on whether SKILL.md prose is treated differently from code; this section reports license texts, not legal advice.
- A null result on disputes from one search is weak evidence; Reddit and X, where such complaints would most likely appear, were not readable.

---

## 6. Prior art and competitors with a Revive-like goal

### Takeaway
There is no established plugin that specifically revives an abandoned project and drives it to a first paid customer. The nearest prior art is (a) solo-founder skill packs that coach idea → first customers, of which `whawkinsiv/solo-founder-skills` is the closest structural match, (b) gstack's product-team flow from office hours to ship, and (c) one small "Project Graveyard" skill for triaging abandoned projects. All are small except gstack.

### Cited Findings
- **whawkinsiv/solo-founder-skills** — 21 skills, MIT, 269 stars (as shown on the repo page), plugin install via `/plugin marketplace add whawkinsiv/solo-founder-skills`. "Sell before you build": get the first 10 paying customers by hand, build the smallest version, ship safely, grow to 100. Skills map almost one-to-one onto Revive's slots: `journey` (finds your stage from paying customers and names the next step), `landing-page`, `payments` (payment links first, then Stripe Checkout, portal, webhooks), `beautify`, `secure`, `go-live` (go/no-go check), `first-customers`, `pricing`, `humanize`, `legal`. READ VIA FETCH-SUMMARY — [repo](https://github.com/whawkinsiv/solo-founder-skills)
- Its marketplace is a single self-contained plugin (`solo-founder`, source `./`): all skills are authored in-repo, no dependencies declared. — [marketplace.json](https://github.com/whawkinsiv/solo-founder-skills/blob/main/.claude-plugin/marketplace.json)
- A plugin directory listing notes most of its skills are advice and checklists rather than tooling. SEARCH SNIPPET ONLY — [awesomeclaudeplugins](https://awesomeclaudeplugins.com/whawkinsiv/solo-founder-skills)
- **yayashuxue/solo-founder-playbook** — 6 skills built from patterns in 101 Starter Story founder interviews (idea evaluation, growth strategy, failure-mode diagnosis such as `/solo-failures`, plan roasting); plugin install; also a no-install browser demo. No LICENSE file at the default path (NOT VERIFIED). — [repo README](https://github.com/yayashuxue/solo-founder-playbook)
- It was submitted to awesome-claude-code as a resource. SEARCH SNIPPET ONLY — [awesome-claude-code issue #3327](https://github.com/hesreallyhim/awesome-claude-code/issues/3327)
- **Jakeschincariol/founder-skill** — 11 MIT skills that "test a business before you launch it": founder-board, -marketing, -cfo, -consumer (100 simulated buyer agents), -launch, -pricing, -offer, -competitors, -brand, -ops, -plan; installs as plugin `founder-skill`. — [repo README](https://github.com/Jakeschincariol/founder-skill)
- **ericvtheg/solo-founder-toolkit** — MIT plugin "that helps indie hackers stop overthinking and start shipping": commands `/solo-feature-ideas`, `/solo-validate-idea` (Solo Founder Risk Index; ship, simplify or kill), `/solo-build-in-public-tweet`; a landing-page reviewer agent (6 Conversion Pillars); background skills including solo-founder-anti-patterns ("95% Ready Trap", "Infrastructure Sophistication Trap"). — [repo README](https://github.com/ericvtheg/solo-founder-toolkit)
- **Project Graveyard** (attributed to shubhamsaboo on a skills directory) — assesses abandoned projects and decides which unfinished work is worth completing; triggers on "abandoned/unfinished/old side projects" and "revive, resurrect, or finally ship"; installed by copying a folder; published roughly 103 days before the search. SEARCH SNIPPET ONLY — [getclaudeskills.com](https://www.getclaudeskills.com/skills/project-graveyard-shubhamsaboo)
- **sshah03/resurrect-anything** — a manual-only `/resurrect` skill for bringing back lost things (dead apps and sites, Flash games) from surviving traces; retrieval, not launch. SEARCH SNIPPET ONLY — [repo](https://github.com/sshah03/resurrect-anything)
- **gstack** — MIT, 142,296 stars; positions itself as a virtual team and documents a chained flow: `/office-hours` (six forcing questions, writes a design doc the other skills read) → plan reviews → `/review` → `/qa` → `/ship` (runs tests and review and opens the PR, attaching evidence); its `/design-review` runs Impeccable's engine first if Impeccable is installed. — [gstack README](https://github.com/garrytan/gstack)
- Korean sources describe gstack's release-stage commands as `/ship` and `/land-and-deploy`. SEARCH SNIPPET ONLY — [ssockssock](https://ssockssock.com/claude-code-upgrade-tools/)
- **Korean vibe-coding kits**: bkit ("Vibecoding Kit — PDCA methodology", Apache-2.0, 606 stars) — [repo](https://github.com/ww-w-ai/bkit-claude-code); the wikidocs book's `yc-office-hours` (만들기 전에 묻는 사업 멘토, tagged for 1인 사업자) and `run-hackathon` (기획 → 개발 → 검증 → 녹화 → 발표 with stage-completion checks). READ DIRECTLY — [wikidocs 446636](https://wikidocs.net/446636), [wikidocs 435360](https://wikidocs.net/435360)
- **marketingskills** (MIT, 61,910 stars; "CRO, copywriting, SEO, analytics, and growth engineering"; 42 skills as of July 2026 per gymcoding) covers the landing-page-and-copy end. — [repo](https://github.com/coreyhaines31/marketingskills); skill count per [gymcoding](https://www.gymcoding.co/articles/claude-skills-top-5-guide)
- Non-skill prior art: an Indie Hackers guide on relaunching a broken side project recommends an audit-first approach with Claude Code — inspect the repo, remove fragile features, add one clear user action. SEARCH SNIPPET ONLY — [Indie Hackers](https://indiehackers.com/post/f238e054e9)

### Inferences
- solo-founder-skills is the competitor to study first: same audience, same slot coverage (design, payments, security, go-live, landing page), a stage-detecting router skill, and a single self-authored plugin with no bundled third-party skills. Revive's differentiators would be (1) starting from an existing abandoned codebase rather than an idea, (2) routing to best-in-class community skills instead of in-house advice checklists, and (3) Korean-market specifics (약관/개인정보처리방침, local payment).
- gstack already demonstrates soft integration with another pack ("if you have impeccable installed, its engine runs first") — a detect-and-use pattern that avoids both vendoring and hard dependencies, and a fourth option beside those in section 4.
- The "getting unstuck / revive" entry point is thinly served: only Project Graveyard targets it, and it stops at triage. No found tool connects triage to payment, deploy and launch.
- Most founder packs are advice-heavy and have low adoption (hundreds of stars at most, where known), which suggests the niche is open but also that demand is unproven.

### Gaps
- Star counts, last-push dates and (for solo-founder-playbook) license were not retrieved for the smaller repos because the GitHub API rate limit was reached; only whawkinsiv's 269 stars is from the repo page.
- Project Graveyard's actual repo, license and content were not opened; the attribution to "shubhamsaboo" comes from a directory URL only.
- I did not search the official plugin directory (317 entries) for launch/founder plugins, nor skills.sh rankings.
- No Korean-language competitor with a "죽은 사이드 프로젝트 살리기 → 첫 유료 고객" framing was found; Korean Threads/X were not searchable, so this is weak evidence of absence.
- No usage or satisfaction data exists for any of these packs beyond stars.
