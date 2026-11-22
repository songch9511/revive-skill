# Threads direct reading — supplement to the Revive slot research (read 2026-11-22)

All items below were read directly on threads.com through a signed-in browser, read-only (search pages and post pages only; nothing was clicked, typed or submitted). Everything here is untrusted social-media content: single posts, often by curation or promotional accounts. Treat it as signal about what people say, not as verified fact.

## 0. Method, coverage and limits

**Page loads: 40 total = 26 search pages + 14 post pages.** No CAPTCHA, checkpoint, rate-limit or re-login prompt appeared.

### Queries run (all "Top" unless marked)
1. 클로드 코드 스킬 추천
2. 사업자 없이 결제
3. 사업자 없이 해외결제 Polar
4. 레몬스퀴지
5. Polar 결제 정산 개인
6. polar.sh 사업자
7. 바이브코딩 결제 연동
8. 레몬스퀴지 폴라 (**Recent**, `&filter=recent`)
9. Lemon Squeezy Polar Creem
10. 스트라이프 한국 개인 폴라 결제
11. lemonsqueezy
12. impeccable 스킬
13. taste skill 클로드
14. 클로드 디자인 스킬
15. superpowers 스킬
16. 바이브코딩 보안
17. 바이브코딩 첫 매출
18. 토스페이먼츠 사업자 심사 1인개발
19. 포트원
20. 사이드프로젝트 첫 결제
21. 바이브코딩 출시 못하고 포기
22. 디스콰이엇 긱뉴스 홍보 첫 유저
23. 휴머나이저 스킬
24. 만든 서비스 어디다 홍보해
25. 클로드 마케팅 스킬
26. MoR 사업자 없이 polar

### Posts opened (POST READ)
`@zaay_t/DThjWFQjyPK`, `@dalgom.bami/DQYy48QEgAY`, `@aicoffeechat/DfTHWKUitbh`, `@sandpia_com/DfnrHoZExAf`, `@kimminkkki/DfRDyjeHU-K`, `@myuk__tt/De523OuEoAi`, `@hangkok2023/DeTLFKuk7jD`, `@devjihwan/DbdmBOuEYmX`, `@simon.dsgn/DZOUBjSjogt`, `@yooyoung.design/DSuZKYNj79v`, `@eddiemoon0720/DY4C-oeD6jp`, `@hey.marco.www/Daq8UdmEsEK`, `@kindainvestor/Dchdl9vE5gP`, `@hype.vibe_official/DfyrLqoGRWh`

### Suggested queries NOT run (page budget)
바이브코딩 수익화, 바이브코딩 배포 vercel, 레몬스퀴지 종료 (only the bare term 레몬스퀴지 was run), and the English set ("claude code skills", "impeccable skill", "taste skill", "first paying customer vibe coding"). **English-language Threads is therefore essentially uncovered**, and the Deployment slot has almost no evidence here.

### Limits that matter when weighing this file
- **Threads search is fuzzy and shallow.** Each query returned only about 5–10 posts even after scrolling. Multi-word queries containing brand names drifted badly off-topic (queries 3, 5, 6, 8, 9, 10, 26 returned mostly travel, fashion, food and tax posts). Single distinctive Korean terms (레몬스퀴지, 포트원) worked best. **Absence of a topic in these notes is weak evidence of absence on Threads.**
- `&filter=recent` does change the result set (ordered by recency), but the one attempt was all noise.
- Some multi-part threads did not render their later parts in the page text (`@hangkok2023` parts 2–3, `@kindainvestor` parts 2–4), so the repo name of the latter and the author's own stated cause in the former are not captured.
- Dates are as displayed (MM/DD/YY). Listing and post page sometimes differ by one day; the post-page date is used where the post was opened. "5d"/"6d" relative dates are relative to 2026-11-22.
- **Engagement** is given as the raw number sequence shown under the post, in Threads' usual order likes / replies / reposts / shares. Threads hides zero counts, so when fewer than four numbers appear the mapping of the later numbers is uncertain. View counts are shown only on post pages.
- No post contained instructions aimed at AI agents. Two posts tell human readers to paste a link or text into their AI assistant as the install or registration method (`@kindainvestor`, `@saas_kr`); noted, not acted on.

---

## 1. Design slot (UI/UX)

**Summary:** On Korean Threads the design conversation is about *removing the "AI-made look"* and about *feeding real references*, not about any one of our four front-runners by name. `impeccable` and `ui-ux-pro-max` appear only inside a star-ranked list; `taste-skill` and Anthropic `frontend-design` did not surface at all in these queries. Three candidates we had not listed came up.

| Item | Source | Status |
|---|---|---|
| **`heydamir/unslop`** — skill for removing AI design patterns; evaluates and fixes screens that are *already built* rather than generating new UI. Follow-up part: supports React, Next.js, Vue, Svelte, Tailwind; can produce a sub-10-second before/after video with Playwright + FFmpeg. Author confirms it works in Codex. One reply asks for someone to teach them hands-on; another advises recording a 360px mobile view and keyboard tab order before changing so regressions (shifted buttons, lost focus ring) are visible. | https://www.threads.com/@sandpia_com/post/DfnrHoZExAf — @sandpia_com (solo full-stack dev, 1.7K followers; curation, not the skill author) — 11/11/26 — 50.4K views; 260 / 7 / 101 / 183 | POST READ |
| **`emilkowalski/skills`** — described as 17 design and motion principles distilled from Apple WWDC talks by a Linear design engineer, "almost 10K" GitHub stars; rules about immediate press feedback, interruptible animation, velocity-continuous swipes. Install line given: `npx skills@latest add emilkowalski/skills`. Pitched for reviewing an existing screen or building a new one. No user replies. | https://www.threads.com/@hey.marco.www/post/Daq8UdmEsEK — @hey.marco.www (1.1K followers; curation) — 07/11/26 — 6.1K views; 35 / 3 / 14 / 28 | POST READ |
| **Appllama MCP** (reference-driven, not a skill) — prompt pattern: have the agent read all screens and videos of a top-earning app and apply its hierarchy, spacing, type, motion and copy length 1:1; then compare side by side. Also organises screens by flow (onboarding, paywall, permission prompts), pitched as the way to decide where the paywall goes. Two replies are sceptical of 1:1 copying: UI will resemble the app but the reason it succeeds will not transfer. | https://www.threads.com/@aicoffeechat/post/DfTHWKUitbh — @aicoffeechat (64.4K followers; large AI-news curation account) — 11/03/26 — 17.2K views; 196 / 6 / 90 / 120 | POST READ |
| **Inspo MCP** — free MCP that searches 800+ good-looking websites and hands the agent matching references; advice is to stop writing "sleek/modern" in prompts. | https://www.threads.com/@aicoffeechat/post/DdSQIokCv4r — @aicoffeechat — 09/15/26 — 224 / 6 / 89 / 144 | SEARCH LISTING ONLY |
| Star-ranked "top Claude Code skills" list: superpowers, anthropics/skills, **ui-ux-pro-max-skill** ("builds a design system"), **impeccable** ("catches the tacky AI design look"), awesome-claude-skills, hyperframes, humanizer, book-to-skill, prompt-master. Ranking is by stars, not by use. | https://www.threads.com/@glitter_ai_factory/post/DeKNFruE3BF — @glitter_ai_factory (curation) — 10/07/26 — 433 / 16 / 219 / 373 | SEARCH LISTING ONLY |
| COREVIS Library — 1,273 UI parts, effects, icons with an `llms.txt` index, free, commercial use allowed per the post. **Self-promotion** (author's own product per a later post by the same account). | https://www.threads.com/@jay.ai.daily/post/DfTey89ihZm — @jay.ai.daily — 11/04/26 — 778 / 94 / 328 / 662 | SEARCH LISTING ONLY |
| Paid UI component packs with "copy for Claude / copy for Codex" prompt buttons; post warns there is **no licence notice**, so check the original pack before using on a client site. | https://www.threads.com/@aicharim_kr/post/Df1PLSEjzmT — @aicharim_kr — ~11/18/26 ("4d") — 3 / 5 | SEARCH LISTING ONLY |
| "Don't say 'make it pretty', show good examples" — six reference sites (aimed at video, same principle). | https://www.threads.com/@naminsoo__ai/post/DeG5YnKgTE9 — @naminsoo__ai — 10/05/26 — 808 / 48 / 410 / 827 | SEARCH LISTING ONLY |

**Reading:** the two highest-engagement design items seen (unslop at 50K views, Appllama at 17K) are both about *fixing or grounding an existing screen*. That matches Revive's situation (an existing, stale project) better than a generate-from-scratch skill.

---

## 2. Getting unstuck slot (debugging, reviving a stale codebase)

**Summary:** Very thin. Nobody in the posts seen describes using a debugging skill. `superpowers` is known but framed as *planning before coding*, not debugging. `mattpocock/skills` and `addyosmani/agent-skills` did not surface.

| Item | Source | Status |
|---|---|---|
| `superpowers` ranked first by stars, glossed as "plan before coding". | https://www.threads.com/@glitter_ai_factory/post/DeKNFruE3BF — 10/07/26 — 433 / 16 / 219 / 373 | SEARCH LISTING ONLY |
| **Everything Claude Code (ECC, `affaan-m/ECC`)** — pitched as a hackathon winner's full setup: 183 skills, 48 agents, 79 commands, including security checks, memory and context optimisation. A whole harness, not a slot skill. | https://www.threads.com/@nice.steve.moon/post/DbTPHMtkyPD — @nice.steve.moon (curation) — 07/27/26 — 490 / 15 / 233 / 484 | SEARCH LISTING ONLY |
| Built-in `/advisor` command — while working on a cheaper model, call a stronger model as adviser when stuck. A built-in "unstuck" path that needs no third-party skill. | https://www.threads.com/@aicoffeechat/post/DW-DCY4E7DA — @aicoffeechat — 04/11/26 — 293 / 10 / 63 / 120 | SEARCH LISTING ONLY |
| Making Claude Code and Codex talk to each other directly instead of copy-pasting between them (cross-model review). | https://www.threads.com/@miri.ad.saiz/post/DeUCtVlD9VN — @miri.ad.saiz — 10/10/26 — 116 / 34 / 39 / 140 | SEARCH LISTING ONLY |
| **`find-skills` (vercel-labs)** — "a skill that finds skills"; one post claims it is the most-installed skill worldwide (3M installs) because people are stuck on *which* skill to install. | https://www.threads.com/@working.ref/post/DcN4kTtEsio — @working.ref — 08/19/26 — 169 / 2 / 71 / 114; and https://www.threads.com/@hyunsoo.it/post/Dfa4Hzmj9_c — @hyunsoo.it — 11/07/26 — 84 / 2 / 33 / 85 | SEARCH LISTING ONLY (both) |
| Korean-made plugin "스킬러들의 수다" — four "skill experts" discuss and turn a vague idea into a workflow skill. **Author promoting own work.** | https://www.threads.com/@gptaku_ai/post/DVXsiQLE42p — @gptaku_ai — 03/02/26 — 111 / 7 / 35 / 70 | SEARCH LISTING ONLY |
| Token-cost anxiety: a 30-turn Claude Code conversation costs far more than the first message; ten saving tips. Relevant to "heavy skill pack" complaints. | https://www.threads.com/@gptersorg/post/DWnKDDSEe1X — @gptersorg (GPTers community account) — 04/02/26 — 15 / 6 / 1 / 6 | SEARCH LISTING ONLY |

**Reading:** what blocks these builders is rarely described as a code bug. See section 8: the stuck points people actually write about are discovery, validation, payment set-up and Korean paperwork.

---

## 3. Payment slot — the most decision-relevant section

**Summary of what Threads actually shows:**
1. Korean PG onboarding (PortOne → KG이니시스, Toss Payments) is a real, slow wall: reviews measured in weeks to months, sign-up fees, and required 사업자등록 + 통신판매업 paperwork.
2. Merchant-of-record services are named by a credible engineer as the way to take money without a business registration — but **no first-hand Polar approval or payout (정산) story was found**, good or bad.
3. The only Lemon Squeezy sentiment found is negative (errors, unreachable support, wanting to move to Polar). **Nothing about a Lemon Squeezy shutdown surfaced.**
4. Paddle got one concrete positive first-hand report. Creem and Dodo Payments got zero hits.
5. Experienced repliers repeatedly say: take a bank transfer first, pick a payment module later.

### 3a. No business registration (사업자 없이)

| Item | Source | Status |
|---|---|---|
| Long post by a senior engineer/mentor on why Korean students and employees do not try selling: in Korea you need a 개인사업자 to legally take revenue, and registering triggers costs before any income — possible loss of health-insurance dependant status and move to 지역가입자 (he puts it at roughly ₩100K/month to start), mandatory national pension (~₩90K/month), bookkeeping duty, possible loss of family allowances, student-loan bracket changes, ineligibility for 예비창업 support programmes. Part 2 says **MoR services such as Polar or Lemon Squeezy, or an AdMob/AdSense ad model, are the only ways to do it without a business registration**, and that employees avoid registering for fear of 겸업금지 issues. In a quote-reply he adds that registering with no revenue is hard for an employer to notice, and revenue under about ₩20M/year is also hard to notice — his opinion, not tax advice. | https://www.threads.com/@dalgom.bami/post/DQYy48QEgAY — @dalgom.bami (15-year SW engineer, startup CTO, SW Maestro mentor; 10.2K followers) — 10/29/25 — 14.7K views; 272 / 27 / 22 / 25. Part 2: https://www.threads.com/@dalgom.bami/post/DQYy5W3kuu6 — 69 / 2 / 3 | POST READ |
| Replies to the above: a 5-year sole proprietor confirms the regional health-insurance burden roughly doubles what an employee paid and reports being over-billed by miscalculation more than once. The author says he used to tell students to just register, then regretted it when they suffered the side effects on apps that earned little. | same thread — @1000ship 11/03/25; @dalgom.bami 10/30/25 | POST READ |
| Quote-repost: this information is hard to find unless you know someone, the process costs money and effort, "and I haven't earned 1 won yet" — motivation breaks. | quote on the same post — @wooing0306 — ~32 weeks before 2026-11-22 | POST READ |
| Question from a 16-year developer: what payment module do people attach to a global micro-service; he has heard Stripe does not accept individuals like him; Lemon Squeezy? Paddle? Only two replies; one is "I'm curious too". | https://www.threads.com/@zaay_t/post/DThjWFQjyPK — @zaay_t — 01/15/26 — 1.1K views; 2 / 2 | POST READ |

### 3b. Lemon Squeezy, Polar, Paddle, Stripe

| Item | Source | Status |
|---|---|---|
| **Lemon Squeezy complaint (first-hand):** do not use it — occasional errors and the support team is almost unreachable. | reply in https://www.threads.com/@zaay_t/post/DThjWFQjyPK (own URL https://www.threads.com/@yooyoung.design/post/DTht7Nyj0uL) — @yooyoung.design — 01/15/26 | POST READ |
| Same person three weeks earlier: selling code components to overseas buyers in USD via vibe coding, first sale of a $168 membership. In replies: uses Lemon Squeezy, has become dissatisfied, and **"if I rebuilt it I'd want to use Polar"**; sells both single items and an unlimited subscription; runs it as a **Korean 개인사업자**, says an overseas entity is not required. Another user (@anelo_tech) also uses Lemon Squeezy. **Flag:** the author sells a "earning dollars A–Z" workbook and newsletter (14.8K followers) — course-seller incentives. | https://www.threads.com/@yooyoung.design/post/DSuZKYNj79v — @yooyoung.design — 12/26/25 — 6.3K views; 31 / 19 / 1 / 2 | POST READ |
| **Paddle (first-hand, positive):** "really fast — verified right away and started using it", offered as the answer to a slow Korean PG review. The asker's follow-up question about Paddle's fees went unanswered in the visible thread. | reply in https://www.threads.com/@kimminkkki/post/DfRDyjeHU-K — @nomadcarpenter_ — 11/03/26 | POST READ |
| Polar listed among "free apps a solo developer uses every day" for revenue and subscription status, alongside PostHog and Featurebase. **Self-promotion** for the poster's own product (item 1 in the list). Not a payout experience. | https://www.threads.com/@stashby.me/post/Dfx9J1_EoGD — @stashby.me — ~11/16/26 ("6d") — 188 / 22 / 89 / 108 | SEARCH LISTING ONLY |
| Stripe: appears only as the thing Korean individuals believe they cannot use (@zaay_t above), and as something US individuals can use without a separate filing (@dalgom.bami above). | — | — |
| **Not found in any query:** Lemon Squeezy shutdown or migration reactions; Polar approval, rejection or payout problems; Creem; Dodo Payments; tax handling of MoR payouts for Korean individuals. | — | — |

### 3c. Korean PGs — 토스페이먼츠, 포트원, 이니시스 and others

| Item | Source | Status |
|---|---|---|
| A vibe coder applied for PG through **PortOne → KG이니시스**; 8 business days in, support can only say "wait"; asks for a faster option. **40 replies**, including: another applicant is "two full months in, entering the third — 8 days is just the start"; attaching **KakaoPay directly was the fastest and still took a month**; **Payple** recommended by several (check whether it supports subscriptions); **Paddle** (see above); sir.kr route; an agency pushing **NICEPAY 포스타트** with its own referral channel and a 3.0% card-fee offer (**promotional**); another agency offering to connect Toss/Naver/Kakao pay (**promotional**). Useful practical reply: while waiting, make sure the footer shows 사업자정보, 이용약관, 환불규정 and the pricing page shows prices — those are the usual review deficiency requests and having them ready turns a follow-up into a one-day fix. | https://www.threads.com/@kimminkkki/post/DfRDyjeHU-K — @kimminkkki (self-described vibe coder) — 11/02/26 — 2.6K views; 10 / 40 / 3 / 4 | POST READ |
| A registered sole proprietor realises after building that there is no way to charge users; asks PortOne? Toss? 이니시스? Replies: for mobile, **in-app purchase is the easiest** (two people); AdMob is the common start; **"take a bank transfer (무통장입금) first and watch whether users actually pay"** (@worker.cab); one person points to @groble.im; one says they built monetisation in from launch. Nobody recommends a specific Korean PG. | https://www.threads.com/@myuk__tt/post/De523OuEoAi — @myuk__tt — 10/24/26 — 1.3K views; 14 / 23 / 1 | POST READ |
| PortOne was advertised as free up to some volume, but then the underlying PGs (다날 and others) contacted the user asking for payment. | https://www.threads.com/@retrooldpop_official/post/DVvk7gZkaUF — @retrooldpop_official — 03/11/26 — 1 / 1 | SEARCH LISTING ONLY |
| Toss Payments' sign-up fee is higher than expected; is there an alternative? One reply: PortOne. | https://www.threads.com/@dd.devlog/post/DYMmkbYk-LP — @dd.devlog — 05/11/26 — 1 / 8 / 1; reply https://www.threads.com/@fizz_div/post/DYM1h8smRIh | SEARCH LISTING ONLY |
| "Launching a paid app in Korea is brutal": business registration, then 통신판매업 신고, which needs a 구매안전서비스 이용확인증, then a 등록면허세 on top. | https://www.threads.com/@mr_gongsang/post/DW8koNnD6Kv — @mr_gongsang — 04/10/26 — 63 / 36 / 2 / 8 | SEARCH LISTING ONLY |
| Vibe-coded dating service already taking money while **manually issuing 현금영수증**; says it becomes fully automatic once PG approval comes through. I.e. launched on manual payment before PG. Topic tag "바이브 코딩 사업" — possible course/consulting account. | https://www.threads.com/@guidehun1/post/DTaYgjTgUoe — @guidehun1 — 01/12/26 — 76 / 34 / 41 / 2 | SEARCH LISTING ONLY |
| Directory account listing 부트페이, 토스페이먼츠, 포트원 as "what AI answers" for Korean PGs. **Promotional** for its own directory. | https://www.threads.com/@saas_kr/post/DfHloItGVF3 — @saas_kr — 10/30/26 — 2 / 1 / 2 | SEARCH LISTING ONLY |

### 3d. Mobile store payouts (adjacent trap)

| Item | Source | Status |
|---|---|---|
| Google Play told a 개인사업자 with an *organisation* account, only after in-app purchases had occurred and right before withdrawal, to create a new *individual* account and transfer the apps. Poster mentions having seen someone preparing a group complaint. | https://www.threads.com/@whitep.life/post/DfjHSB1GnbB — @whitep.life — 11/10/26 — 39 / 35 / 6 / 11; earlier part https://www.threads.com/@whitep.life/post/Dfa6IFMgXtG — 11/07/26 | SEARCH LISTING ONLY |
| Same Google Play problem reported independently, asking if others have seen it. | https://www.threads.com/@stayme.dev/post/DdSR62Zj-w2 — @stayme.dev — 09/15/26 — 9 / 10 / 1 / 6 | SEARCH LISTING ONLY |
| iOS rejection as a "common app"; forced move to an individual Google account, then home address exposed on the store; fixed via a 지방세납세증명서 as address proof. | https://www.threads.com/@ziafuture/post/Dev4WiJH2n3 — @ziafuture — 10/21/26 — 27 / 28 / 9 / 6 | SEARCH LISTING ONLY |
| Apply for the App Store Small Business Program (15% instead of 30%). | https://www.threads.com/@jaelyung_kim/post/DbzfGQGj9H6 — @jaelyung_kim — 08/09/26 — 203 / 13 / 81 / 103 | SEARCH LISTING ONLY |

---

## 4. Deployment slot

Almost no evidence: no Vercel, Railway, Cloudflare or Netlify post surfaced, and the dedicated deployment query was not run. What did surface is a **Korean distribution target we had not listed: 토스 미니앱 / 앱인토스 (Apps in Toss).**

| Item | Source | Status |
|---|---|---|
| Designer shipped a first app with no-code (FlutterFlow), then **launched a Toss mini-app with Claude Code**; argues DB, auth, API, payments and store release all at once is overwhelming for a beginner. | https://www.threads.com/@arcoa.kr/post/DXOZA6nksji — @arcoa.kr — 04/17/26 — 46 / 33 / 8 / 4 | SEARCH LISTING ONLY |
| Tried 앱인토스 and ended up on the App Store: first commit to review approval in about 16 hours for a simple game. | https://www.threads.com/@cactuslimoo/post/DeHVmj7kqJn — @cactuslimoo — 10/05/26 — 26 / 16 / 1 | SEARCH LISTING ONLY |
| Counter-evidence on Toss mini-apps as a revenue channel: 8 mini-apps earned ₩9,000 in 14 days (see section 8). | https://www.threads.com/@devjihwan/post/DbdmBOuEYmX | POST READ |

---

## 5. Landing page, copy and launch slot

| Item | Source | Status |
|---|---|---|
| **Korean-made SEO/GEO skill, released free on GitHub** — pitched as doing what ₩500K–3.5M/month SEO, GEO and "AI search optimisation" agencies do, because that work is mostly public standards plus repeatable checklists. Author says it both diagnoses and implements, and works worldwide and in other agents. One real-use reply two months later: tried it, "the analysis is excellent, using it regularly" (@pixelconnect.web, 10/13/26). **By far the highest engagement seen in this whole session. Author promoting own work**; the repo link is in part 3 of the thread, which did not render, so the repo name is **not captured** — needs a follow-up look. | https://www.threads.com/@kindainvestor/post/Dchdl9vE5gP — @kindainvestor (1.8K followers) — 08/26/26 — **244K views; 2.6K / 300 / 1.3K / 3.2K**; 36 quotes | POST READ |
| **`humanizer`** (62.6K stars per the post) recommended as one of three skills office workers should install first, with anthropics/skills and **`last30days`** (66K stars; gathers the last 30 days of Reddit, X and YouTube reaction on a topic — pitched for market research). | https://www.threads.com/@starlight_korean/post/DfHuMRVHxrM — @starlight_korean (curation) — 10/30/26 — 203 / 4 / 90 / 153 | SEARCH LISTING ONLY |
| `humanizer` also in the star-ranked list ("erases the AI tone"). | https://www.threads.com/@glitter_ai_factory/post/DeKNFruE3BF — 10/07/26 | SEARCH LISTING ONLY |
| "100 marketing skills, 10 team leads" system that introduces itself, takes your info once and proceeds through gates; 333 replies are the requested "me!" comments feeding a YouTube video. **Promotional / engagement-bait**; no public repo shown. | https://www.threads.com/@kook0526/post/Dayrzf7Ds_w — @kook0526 — 07/15/26 — 119 / 333 / 25 / 30 | SEARCH LISTING ONLY |
| Marketing tool by a developer: collect material, generate per-platform posts, connect Instagram/Threads/TikTok/YouTube/X, MCP for Claude/ChatGPT. **Self-promotion.** | https://www.threads.com/@posteady.com_/post/Dff90g3Gfj- — @posteady.com_ — 11/09/26 — 1K / 117 / 436 / 1.1K | SEARCH LISTING ONLY |
| `find-skills` example prompt in a post is literally "is there a skill that makes good landing pages?" — discovery, not a specific landing skill, is what gets shared. | https://www.threads.com/@working.ref/post/DcN4kTtEsio — 08/19/26 | SEARCH LISTING ONLY |

**Not found:** `coreyhaines31/marketingskills`, `blader/humanizer` by repo name, the Korean humanizers (`im-not-ai`, `k-skill`, `humanizer-kr`), `solo-founder-skills`. The query 휴머나이저 스킬 returned only the generic `humanizer` inside lists.

---

## 6. Pre-launch checks slot (verification, security)

| Item | Source | Status |
|---|---|---|
| **Anthropic's official `security-guidance` plugin** — free on every Claude Code plan, install with `/plugin install security-guidance`, then runs automatically with no command. Described as three checks: on file edit (risky patterns), at the end of a turn (whole diff), and at commit (reads surrounding code to confirm). Catches hard-coded passwords/API keys, `eval`-style execution of external input, XSS, command injection — about 25 regex patterns. The post relays Anthropic's own caveat: it catches low-hanging fruit and does not replace semantic analysis or an experienced reviewer. Replies are thanks only; no usage reports. | https://www.threads.com/@eddiemoon0720/post/DY4C-oeD6jp — @eddiemoon0720 (14-year PO; 861 followers; curation) — 05/28/26 — 17.4K views; 125 / 9 / 55 / 110 | POST READ |
| Bundle of 83 security-check skills for Claude Code (vulnerability checks, CVE tracking, red-team report formatting). Name not visible in the listing; low engagement. | https://www.threads.com/@ibwj/post/Deg6HjUiZ8c — @ibwj — 10/15/26 — 13 / 2 / 12 | SEARCH LISTING ONLY |
| ECC harness advertises built-in security checks (see section 2). | https://www.threads.com/@nice.steve.moon/post/DbTPHMtkyPD | SEARCH LISTING ONLY |
| A non-security pre-launch check that came from a real PG-review experience: footer business info, terms, refund policy and visible pricing (see 3c). | https://www.threads.com/@kimminkkki/post/DfRDyjeHU-K — reply by @home_father_ 11/03/26 | POST READ |
| Design regression check before/after a visual change: 360px mobile and keyboard tab order (see section 1). | https://www.threads.com/@sandpia_com/post/DfnrHoZExAf — reply by @reference_radar 11/13/26 | POST READ |

**Not found:** any first-hand "my vibe-coded app leaked keys / got hacked" story, `vibe-security-skill`, `cloudflare/security-audit-skill`, superpowers `verification-before-completion`, or the built-in `/security-review`. The single security query returned mostly unrelated posts.

---

## 7. Korean launch channels — what people actually use

**Summary:** In this sample **Threads itself is the launch channel**, used as build-in-public. 디스콰이엇 and 긱뉴스 did not appear in any post read (one query only). A crop of new "show your vibe-coded service" directories exists, which signals that distribution is the shared unmet need.

| Item | Source | Status |
|---|---|---|
| A free Claude Code 101 site announced **only on Threads** reached 1,000+ daily visitors within a week, with spill-over from Facebook shares. Author deliberately added no ads or donation button. | https://www.threads.com/@gptaku_ai/post/DVfvEVCE4rA — @gptaku_ai — 03/05/26 — 38 / 15 / 4 / 4 | SEARCH LISTING ONLY |
| Rules for marketing an app on Threads from someone claiming 1M views on a service account: no URL in the post, do not list features, write so readers feel it is their own problem, hide selling intent, say what problem it solves. | https://www.threads.com/@designbywani/post/DS7BJbbCmKC — @designbywani — 12/31/25 — 133 / 36 / 36 / 26 | SEARCH LISTING ONLY |
| Designer's cute desktop-pet product: $723 revenue five days after launch, versus a year to reach $1,000 for an earlier reading-log app. Lesson stated: make cute things. A reply asking where it was promoted and sold got **no visible answer**; the account itself is a 5K-follower build-in-public designer. | https://www.threads.com/@simon.dsgn/post/DZOUBjSjogt — @simon.dsgn — 06/05/26 — 9.9K views; 167 / 42 / 19 / 39 | POST READ |
| Designer's vibe-coded site hit 80K visits in two days after going viral. | https://www.threads.com/@stonegg_life/post/DZp0nFSDLCV — @stonegg_life — 06/17/26 — 185 / 67 / 26 / 17 | SEARCH LISTING ONLY |
| A solo app maker posts the build process on Threads so that people search the app by name, because store keyword search is owned by incumbents. | reply in https://www.threads.com/@hangkok2023/post/DeTLFKuk7jD — @uta_koto — 10/10/26 | POST READ |
| Failure stories get engagement too: author expected Threads to like only success stories; repliers asked for the full story. | https://www.threads.com/@devjihwan/post/DbdmBOuEYmX — replies 08/01/26 | POST READ |
| New showcase platform **hypevibe.co.kr**, built after the author asked builders where they promote; 119 replies are mostly builders dropping their own service links. A prize contest was announced for 11/20. **Self-promotion.** | https://www.threads.com/@hype.vibe_official/post/DfyrLqoGRWh — @hype.vibe_official (53 followers) — ~11/17/26 ("5d") — 4.5K views; 76 / 119 / 18 / 6 | POST READ |
| "앱자랑" community for makers to show apps and test each other's (hongbo.sanghak.kr). **Self-promotion** in a reply. | reply in https://www.threads.com/@hangkok2023/post/DeTLFKuk7jD — @baedorphin — 10/10/26 | POST READ |
| For generic simple apps, a store listing is not enough: you need a mini web landing page plus matching Shorts and an Instagram account. | reply in the same thread — @jessahnjw — 10/11/26 | POST READ |
| ~₩30K app selling about one copy a day with no promotion. | https://www.threads.com/@im.monthly.dev/post/Dc-UL80knw2 — @im.monthly.dev — 09/07/26 — 27 / 4 / 3 | SEARCH LISTING ONLY |
| 사주 (fortune) services: one reports 14.8% payment conversion; another got a paid order within 25 minutes with no ads running. | https://www.threads.com/@onp0int__/post/DcLz4BNGDd5 — 08/18/26 — 41 / 24 / 6 / 27; https://www.threads.com/@tinytoy.factory/post/DfAG1_cifZj — 10/27/26 — 13 / 2 / 1 | SEARCH LISTING ONLY |

**Not found:** 디스콰이엇, 긱뉴스, 오픈카톡, 네이버 카페, 당근, 크몽 as first-customer channels.

---

## 8. Why vibe coders stall, and what got them to launch or first payment (first-hand)

**The stall described on Threads is rarely "the code broke". It is, in order of how often it appeared: nobody finds the product; no market check was done; payment and paperwork; "just a bit more polish".**

| Item | Source | Status |
|---|---|---|
| **5 apps on Google Play in 4 months** with Claude (minimum app 5 days, an astrology app 2 months); revenue is poor. The author's stated cause is in parts 2–3, which did not render; replies make clear it is that Play keyword search surfaces only apps that got there first. Another developer with 5 apps is considering a B2B pivot or going back to the day job; one replier disagrees and says the answer is to ship more, sooner. | https://www.threads.com/@hangkok2023/post/DeTLFKuk7jD — @hangkok2023 (20-year developer) — 10/09/26 — 5K views; 20 / 20 / 2 / 1 | POST READ |
| **14 iOS apps + 8 Toss mini-apps in a year; the 8 mini-apps earned ₩9,000 in 14 days.** Built an iOS app from plan to review submission in one day, then found 10 apps with the same name, his being eighth; daily impressions 12–14 after three weeks. Claude Code never searched the name, and its own planning document had read "many competitors" as "validated market", which he did not read closely. His conclusion: many competitors meant page one of search was already full. A replier with 2 mini-apps (₩5,669 in 9 days) stopped adding apps after seeing 8% next-day return and 1 of 60 users left after a week. | https://www.threads.com/@devjihwan/post/DbdmBOuEYmX — @devjihwan — 07/31/26 — 5.9K views; 35 / 17 / 3 / 1; reply @n2slab 09/04/26 | POST READ |
| Someone who had the same idea as a product that later earned $723 in five days: tried a little, then **stopped "for many reasons"**, and says he would not assume he'd have had the same result. | reply and quote on https://www.threads.com/@simon.dsgn/post/DZOUBjSjogt — @uhd_kr — 06/06/26 | POST READ |
| Solo dev at v2.0.0: planned to run ads once it's "complete", keeps thinking "just a bit more" and postponing. | https://www.threads.com/@doff.app/post/DVvTfxSD0fz — @doff.app — 03/11/26 — 32 / 8 | SEARCH LISTING ONLY |
| Built the app, registered the business, then realised there was no way to take payment. | https://www.threads.com/@myuk__tt/post/De523OuEoAi — 10/24/26 | POST READ |
| Paperwork kills motivation before the first won is earned. | quote on https://www.threads.com/@dalgom.bami/post/DQYy48QEgAY — @wooing0306 | POST READ |
| A solo developer's app-launch checklist (developer accounts, identity and address proof, and more) written because the non-coding steps were the hard part. | https://www.threads.com/@mr_gongsang/post/DXEaGMDj9Xw — @mr_gongsang — 04/13/26 — 144 / 47 / 66 / 60 | SEARCH LISTING ONLY |
| First successful payment-system implementation: "just trying is best — keep looking for a way". | https://www.threads.com/@soo_sang_han/post/DZfBiWGmlDW — @soo_sang_han — 06/12/26 — 16 / 14 / 2 | SEARCH LISTING ONLY |

**What moved people to revenue, per the posts read:** charging from day one rather than converting later (@thokey_official reply, 10/26/26); taking a bank transfer before any PG (@worker.cab; @guidehun1); in-app purchase instead of web PG for mobile; selling to overseas buyers in USD through an MoR (@yooyoung.design); emotional/cute differentiation rather than features (@simon.dsgn); building an audience on Threads before and during launch.

---

## 9. Prior art for "revive an abandoned project / coach a solo builder to first revenue"

**Nothing with Revive's specific goal was seen.** Adjacent things that did appear:

| Item | Why it is adjacent | Source | Status |
|---|---|---|---|
| **Replica Skill** (`Jakeschincariol/replica-skill`, ~4.1K stars per the post, MIT) — 11 skills that analyse an existing app, design, build UI and backend, test, deploy, and mine user reviews for what to fix. | End-to-end staged pipeline from idea to deployed app; closest in shape, but for cloning, with no payment or first-customer stage mentioned. | https://www.threads.com/@vibe.itji/post/Deyah9Aj0Jg — @vibe.itji (curation) — 10/22/26 — 300 / 8 / 139 / 330 | SEARCH LISTING ONLY |
| `find-skills` | Solves "which skill do I use" — overlaps Revive's routing function. | section 2 | SEARCH LISTING ONLY |
| "100 marketing skills + 10 team leads", gated flow | Orchestrator-over-many-skills pattern, marketing only. | section 5 | SEARCH LISTING ONLY |
| ECC | Monolithic harness; the "install everything" alternative to slot routing. | section 2 | SEARCH LISTING ONLY |
| "스킬러들의 수다" | Korean-made skill-authoring plugin. | section 2 | SEARCH LISTING ONLY |
| hypevibe, 앱자랑, saaskr | Directories addressing the distribution gap, not coaching. | section 7 | mixed |
| "Five people earning with AI as one-person businesses all started in the same order" (12-part thread) | Content-form "sequence to revenue" coaching; not opened. Hook-style post — treat as content marketing. | https://www.threads.com/@zero__gray/post/DdIq4iBiTRA — @zero__gray — 09/11/26 — 693 / 36 / 270 / 672 | SEARCH LISTING ONLY |

---

## 10. Where Threads evidence CONFIRMS, CONTRADICTS or ADDS TO the front-runner list

### Confirms
- **`obra/superpowers`, `impeccable`, `ui-ux-pro-max`, `humanizer`, anthropics/skills** are the names Korean curation accounts repeat — but only inside star-ranked lists. This confirms *awareness*, not *use*.
- **Polar as the direction of travel away from Lemon Squeezy** (one first-hand seller would choose Polar if rebuilding) and **MoR as the no-business-registration route** (one credible engineer names Polar and Lemon Squeezy).
- **Paddle works quickly for a Korean builder** (one first-hand report).
- **Korean PGs (Toss Payments, PortOne) are slow and paperwork-heavy for solo builders** — strongly confirmed: 8 days to 2+ months of review, sign-up fees, 통신판매업 chain.
- Heavy all-in-one packs exist and get shared (ECC), consistent with the existing "too many skills" concern.

### Contradicts or weakens
- **Lemon Squeezy "reportedly shutting down": Threads gave no confirmation.** The only reactions found are about reliability and support (Dec 2025 – Jan 2026). Do not cite Threads for the shutdown.
- **`superpowers` for the *debugging* slot:** on Threads it is described as a plan-first workflow. No one mentions `systematic-debugging`.
- **`taste-skill`, Anthropic `frontend-design`, `mattpocock/skills`, `addyosmani/agent-skills`, `coreyhaines31/marketingskills`, `vibe-security-skill`, `cloudflare/security-audit-skill`, Creem, Dodo Payments, and the Korean humanizers (`im-not-ai`, `k-skill`, `humanizer-kr`) did not surface at all.** Given how weak Threads search is, this is weak negative evidence, but it does mean none of them can be called "popular on Korean Threads" on the strength of this session.
- **The premise that the stuck point is technical.** First-hand Threads stories locate the stall in discovery, validation, payment set-up and admin, and in endless polishing — not in broken code. A Revive that leads with debugging may be aimed at the smaller problem.
- **Web PG as the default payment path.** Repliers steer beginners to bank transfer first, in-app purchase for mobile, or ads.

### Adds (candidates and facts not in the front-runner list)
- **Design:** `heydamir/unslop` (fix existing screens; strongest fit for a revive flow), `emilkowalski/skills` (motion and interaction principles), and reference-driven MCPs (Appllama, Inspo).
- **Pre-launch:** Anthropic's official **`security-guidance`** plugin (free, automatic, ~25 patterns, explicitly low-hanging-fruit only) — a zero-friction baseline to sit under any third-party security skill. Plus two non-security checklists that came from real pain: PG-review readiness (footer business info, terms, refund policy, visible pricing) and a name/keyword collision check before launch.
- **Launch:** a Korean-made **SEO/GEO skill by @kindainvestor** with the largest reach seen (244K views) and one real-use endorsement — repo name still to be captured. **`last30days`** as a market-research/validation skill.
- **Payments:** **Payple** and **direct KakaoPay** as Korean options people recommend; **NICEPAY 포스타트** (promoted by an agency); **bank transfer + manual 현금영수증** as the real first-payment path; Google Play's 개인사업자 organisation-account payout trap.
- **Deployment/distribution:** **토스 미니앱 / 앱인토스** as a Korean target several builders use — with a cautionary revenue data point.
- **Launch channel:** Threads itself, used build-in-public, is the channel with concrete numbers in this sample; new maker directories (hypevibe, 앱자랑, saaskr) exist but are unproven.
- **A missing slot:** *validation and discovery before more building* (name collision, keyword saturation, willingness to pay). Two of the clearest failure stories are exactly this, and one blames the agent's own optimistic planning document.
- **Routing itself is a recognised pain:** `find-skills` is promoted as the most-installed skill because people do not know which skill to use — supportive of Revive's slot-routing idea, and also its nearest general-purpose substitute.

### Open follow-ups this session could not close
1. First-hand Polar approval and payout experience for Korean individuals without 사업자등록, and how the payout is taxed — **not found on Threads**; the single most important gap remains open.
2. Lemon Squeezy shutdown reactions — not found.
3. Repo name of the @kindainvestor SEO/GEO skill (part 3 of the thread).
4. English-language Threads and the Deployment slot — not covered.
