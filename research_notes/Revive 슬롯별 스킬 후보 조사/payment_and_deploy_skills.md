# Claude Code skills for the PAYMENT and DEPLOYMENT slots (state as of 2026-11-22)

Method notes for the report writer:
- All repo facts (license, stars, last commit, folder contents, manifests) were read from the GitHub REST API with `gh api` on 2026-11-22. Star counts are a snapshot of that day. "Last commit" = newest commit on the default branch.
- Social-evidence labels: **READ DIRECTLY** = I fetched the page/API and read the content; **SEARCH SNIPPET ONLY** = only a search-engine summary was available.
- Reddit could not be accessed at all (the search tool refuses the reddit.com domain; Reddit's public JSON search returned nothing). X/Twitter and YouTube produced no relevant hits. Threads pages could not be opened (the fetch returned an unrelated feed). See the Gaps under the social-evidence question.
- Direct quotations were deliberately avoided; statements attributed to people are paraphrases.

---

## Q1. PAYMENTS: which skills / official agent toolkits exist (Stripe, Lemon Squeezy, Polar, Paddle, Creem, Dodo, Toss Payments, PortOne), and which are vendor-official skills rather than MCP-only?

### Takeaway
Stripe, Polar, Paddle, Dodo Payments, Creem and PortOne all publish OFFICIAL skill packs (SKILL.md) — not just MCP servers — and all except PortOne's ship under a clear MIT or Apache-2.0 LICENSE file; Toss Payments publishes only a docs-search MCP server (no official skill), and Lemon Squeezy has no official skill and is shutting down (closed to new sellers mid-November 2026). For the Revive user profile (Korean individual, often no company, wants one hosted checkout link fast), the best-fitting official skill is Polar's `setup-polar` wizard (MIT), with Stripe's `stripe-best-practices` (MIT) as the best-maintained option for users who can actually open a Stripe account; no public skill does the "which provider can I legally open, then make one payment link" routing, so that thin layer must be self-written.

### Cited Findings

**Stripe (official; skills + plugin + remote MCP)**
- `stripe/ai` (formerly `stripe/agent-toolkit`; the old name redirects) is owned by the Stripe org, MIT LICENSE file ("Copyright (c) 2024–2025 Stripe"), 2,077 stars, last commit 2026-11-21, created 2024-11-11, 50 open issues+PRs. — [stripe/ai](https://github.com/stripe/ai)
- Top-level `skills/` contains 11 skills: `stripe-best-practices`, `stripe-docs`, `stripe-implementation-planner`, `stripe-projects`, `stripe-pay`, `stripe-apps`, `stripe-directory`, `stripe-bfcm-dashboard`, `connect-recommend`, `connect-required-verification-information`, `metronome`. — [stripe/ai skills folder](https://github.com/stripe/ai/tree/main/skills)
- The Claude Code plugin lives at `providers/claude/plugin/` (version 0.15.2, `"license": "MIT"`), bundling the same skills, two commands (`explain-error`, `test-cards`), hooks, and an `.mcp.json` that points at the remote HTTP server `https://mcp.stripe.com`. — [stripe/ai Claude plugin](https://github.com/stripe/ai/tree/main/providers/claude/plugin)
- The repo is itself a marketplace (`.claude-plugin/marketplace.json`, name `stripe`), and the plugin is also listed in Anthropic's official directory as a `git-subdir` source pinned to a commit SHA of `stripe/ai`. — [anthropics/claude-plugins-official marketplace.json](https://github.com/anthropics/claude-plugins-official/blob/main/.claude-plugin/marketplace.json)
- `stripe-best-practices/SKILL.md` pins "Latest Stripe API version: 2026-11-18.endive" plus current SDK versions, routes one-time payments to Checkout Sessions, tells the agent to always prefer restricted keys (`rk_`) over secret keys (`sk_`), and says a no-registration sandbox can be created with `stripe sandbox create`. Its `references/payments.md` lists Payment Links as the no-code option best for simple products. — [stripe-best-practices SKILL.md](https://github.com/stripe/ai/blob/main/skills/stripe-best-practices/SKILL.md), [references/payments.md](https://github.com/stripe/ai/blob/main/skills/stripe-best-practices/references/payments.md)
- Stripe's docs give the quickstart as installing the Stripe CLI and running `stripe agent setup`, or manually `claude plugin install stripe@anthropic-plugin-directory`; automatic plugin support is listed for Claude Code, Codex, Cursor, Grok, Kiro and OpenClaw. — [Stripe docs: Agent plugins](https://docs.stripe.com/agents/plugin)
- Conflict: a search summary of Stripe's "building with LLMs" page showed the install command as `stripe@claude-plugins-official`, while the agents/plugin page (read directly) shows `stripe@anthropic-plugin-directory`. — [Stripe docs: Building with LLMs](https://docs.stripe.com/building-with-llms) (SEARCH SNIPPET ONLY); contradicted by [Stripe docs: Agent plugins](https://docs.stripe.com/agents/plugin)
- Copies of `stripe-best-practices` circulate in third-party indexes pinned to older API versions (2026-02-25.clover, 2026-03-25.dahlia, 2026-05-27.dahlia were seen), i.e. a bundled copy goes stale quickly. — [skills.sh listing](https://skills.sh/stripe/agent-toolkit/stripe-best-practices) (SEARCH SNIPPET ONLY)

**Polar (official; skills + plugin + remote MCP incl. sandbox)**
- `polarsource/agent-toolkit` (the name `polarsource/skills` redirects to it): Polar org, MIT LICENSE ("Copyright (c) 2026 Polar Software Inc."), 8 stars, last commit 2026-11-17 (release 0.2.3), created 2026-01-26, 3 open issues+PRs. — [polarsource/agent-toolkit](https://github.com/polarsource/agent-toolkit)
- Skills: `setup-polar`, `polar-integration`, `polar-testing`, `polar-migration`. `.mcp.json` registers two remote HTTP servers: `https://mcp.polar.sh/mcp/polar-mcp` and `https://mcp.polar.sh/mcp/polar-sandbox`. Manifests exist for Claude, Cursor, Gemini and OpenAI. — [polarsource/agent-toolkit skills](https://github.com/polarsource/agent-toolkit/tree/main/skills)
- `setup-polar` describes itself as an interactive onboarding wizard that walks through MCP installation, authentication, creating the first product and checkout, and generating framework-specific code. — [setup-polar SKILL.md](https://github.com/polarsource/agent-toolkit/blob/main/skills/setup-polar/SKILL.md)
- Not listed in Anthropic's official marketplace (no polar entry). — [anthropics/claude-plugins-official marketplace.json](https://github.com/anthropics/claude-plugins-official/blob/main/.claude-plugin/marketplace.json)

**Paddle (official; skills + Claude Code plugin + docs MCP)**
- `PaddleHQ/paddle-agent-skills`: Paddle org, Apache-2.0 LICENSE file, 9 stars, last commit 2026-11-19 ("Add the Lemon Squeezy migration skill"). — [PaddleHQ/paddle-agent-skills](https://github.com/PaddleHQ/paddle-agent-skills)
- 13 skills: `onboarding`, `catalog-setup`, `checkout-web`, `customer-portal`, `pricing-pages`, `sandbox-testing`, `webhooks`, `subscription-sync`, `subscription-update`, `subscription-cancel`, `usage-based-billing`, `billing-history`, `migrate-lemon-squeezy`; provider folders for claude, codex, cursor. — [paddle-agent-skills skills folder](https://github.com/PaddleHQ/paddle-agent-skills/tree/main/skills)
- Paddle's changelog announced an official Claude Code plugin that installs all skills in one command and wires the Paddle docs MCP server, dated 2026-05-14. — [Paddle changelog](https://developer.paddle.com/changelog/2026/agent-skills-claude-code-plugin) (SEARCH SNIPPET ONLY)
- `PaddleHQ/paddle-mcp-server` (Apache-2.0, 50 stars) is marked deprecated in its own description in favour of the remote Paddle MCP server. — [PaddleHQ/paddle-mcp-server](https://github.com/PaddleHQ/paddle-mcp-server)

**Dodo Payments (official; skills repo + agent plugin + remote MCP)**
- `dodopayments/skills`: MIT LICENSE ("Copyright (c) 2025 Dodo Payments"), 14 stars, last commit 2026-11-09, pushed 2026-11-17. — [dodopayments/skills](https://github.com/dodopayments/skills)
- `dodopayments/dodo-agent-plugin` ("Official Dodo Payments Plugin for Claude Code, Codex, Cursor and Opencode"): MIT, 8 stars, last commit 2026-11-09, created 2026-04-21; `.mcp.json` points to remote `https://mcp.dodopayments.com/mcp`. — [dodopayments/dodo-agent-plugin](https://github.com/dodopayments/dodo-agent-plugin)
- Dodo's docs for AI coding agents say `POST /payments` and `POST /subscriptions` are deprecated and recommend Checkout Sessions. — [Dodo docs: build with AI coding agents](https://docs.dodopayments.com/developer-resources/build-with-ai-coding-agents) (SEARCH SNIPPET ONLY)

**Creem (official; skill only)**
- `armitage-labs/creem-skills` is now only a pointer marketplace: NO LICENSE FILE in that repo, 2 stars, last commit 2026-08-12; its README says the skill is maintained in `armitage-labs/creem` at `packages/docs/skills/creem-api`. — [armitage-labs/creem-skills](https://github.com/armitage-labs/creem-skills)
- Canonical `armitage-labs/creem`: MIT LICENSE file, 36 stars, last commit 2026-11-20; the skill folder's own last commit is 2026-11-02. Install: `/plugin marketplace add armitage-labs/creem` then `/plugin install creem-api@creem-skills`. — [armitage-labs/creem](https://github.com/armitage-labs/creem)
- A search summary wrongly concluded there is no official Creem skill; the repo evidence above contradicts that. — [armitage-labs/creem-skills README](https://github.com/armitage-labs/creem-skills)

**Lemon Squeezy (no official skill; platform shutting down)**
- The `lmsqueezy` GitHub org has no skills/MCP/agent repo (org listing filtered for skill|mcp|agent|plugin|claude|ai returned only an unrelated Laravel UI repo). — [lmsqueezy org](https://github.com/lmsqueezy)
- Community-only skills: `adrianwedd/lemonsqueezy-claude-skills` (MIT, 11 stars, last commit 2026-01-06, store-operations skills) and `mervick/lemonsqueezy-agent-skills` (MIT, 0 stars, last commit 2026-09-09). — [adrianwedd/lemonsqueezy-claude-skills](https://github.com/adrianwedd/lemonsqueezy-claude-skills), [mervick/lemonsqueezy-agent-skills](https://github.com/mervick/lemonsqueezy-agent-skills)
- Lemon Squeezy announced it is winding down: closed to new stores in mid-November 2026 and will stop processing payments on 2027-03-31; merchants are being pointed at Stripe Managed Payments, which is not available in every country Lemon Squeezy served. — [Michael Tsai blog, 2026-11-19](https://mjtsai.com/blog/2026/11/19/lemon-squeezy-shutting-down/) (READ DIRECTLY; it links the official post at https://www.lemonsqueezy.com/blog/saying-goodbye-to-lemon-squeezy, which I did not open)
- Date conflict on the sign-up cut-off: HN stories titled "Lemon Squeezy is winding down" were posted 2026-11-16 and a community repo README says no new stores since 16 November 2026, while the summary of the Nov 19 blog post read it as "as of today". — [HN item 50518944](https://news.ycombinator.com/item?id=50518944), [zhuyansen/payment-guard README](https://github.com/zhuyansen/payment-guard); vs [Michael Tsai blog](https://mjtsai.com/blog/2026/11/19/lemon-squeezy-shutting-down/)

**Toss Payments 토스페이먼츠 (official MCP only; no official skill)**
- Official offering is a docs-search MCP server, npm package `@tosspayments/integration-guide-mcp` run with `npx -y ...@latest`; tools are `get-v2-documents`, `get-v1-documents`, `get-glossary-documents`, `document-by-id`; plus `llms.txt` and an "LLM Quick Reference" page. The official LLM guide mentions no Claude Code skill or plugin. — [Toss Payments docs: LLM guide](https://docs.tosspayments.com/guides/v2/get-started/llms-guide) (READ DIRECTLY)
- npm registry metadata: license MIT, latest 0.0.31, last modified 2026-09-22, no repository URL. — [npm registry: @tosspayments/integration-guide-mcp](https://registry.npmjs.org/@tosspayments/integration-guide-mcp)
- No public MCP/skill repo appeared in the `tosspayments` GitHub org listing (only SDK and sample repos). — [tosspayments org](https://github.com/tosspayments)
- Toss Payments launched the MCP in June 2025 and markets it as cutting integration time to about 10 minutes (vendor marketing). — [Toss Payments blog](https://www.tosspayments.com/blog/articles/mcp) (SEARCH SNIPPET ONLY)
- Community wrappers: `pleaseai/claude-code-plugins` (MIT, 17 stars, last commit 2026-11-18) has a `plugins/tosspayments` plugin = one SKILL.md + `.mcp.json` launching the official npm MCP; its plugin.json lists the author as "Toss Payments" and a repository URL under the tosspayments org even though the plugin lives in a community repo. `mainsoft-2024/toss-payments-docs-fetcher-skill` is a skill re-packaging of the MCP (NO LICENSE FILE, 0 stars, last commit 2026-03-30). — [pleaseai/claude-code-plugins tosspayments plugin](https://github.com/pleaseai/claude-code-plugins/tree/main/plugins/tosspayments), [mainsoft-2024/toss-payments-docs-fetcher-skill](https://github.com/mainsoft-2024/toss-payments-docs-fetcher-skill)

**PortOne 포트원 (official skills + CLI + MCP)**
- `portone-io/cli`: in the PortOne org, 0 stars, last commit 2026-09-22, pushed 2026-11-01. NO LICENSE FILE in the repo (the GitHub license API returns 404 and the tree has no LICENSE path) even though the README badge links to one; `package.json` and `Cargo.toml` both declare `MIT`, and the npm package `@portone/cli` (0.2.0, modified 2026-09-21) declares MIT. — [portone-io/cli](https://github.com/portone-io/cli), [npm registry: @portone/cli](https://registry.npmjs.org/@portone/cli)
- It ships skills `portone-guide`, `portone-cli`, `payment-code-generator`, `integration-validator`, a Claude plugin `portone-integration` (v1.1.0) via `.claude-plugin/marketplace.json`, and an installer `portone setup` that supports Claude Code, Codex, Cursor, Gemini CLI, Copilot and OpenCode. The marketplace manifest's owner field names an individual rather than the company. — [portone-io/cli README](https://github.com/portone-io/cli/blob/main/README.md), [portone-io/cli marketplace.json](https://github.com/portone-io/cli/blob/main/.claude-plugin/marketplace.json)
- `portone-guide` tells the agent to prefer V2 for new projects, never mix V1 and V2, and to consult the PortOne MCP server before writing or validating code. — [portone-guide SKILL.md](https://github.com/portone-io/cli/blob/main/skills/portone-guide/SKILL.md)
- `portone-io/mcp-server`: dual-licensed with LICENSE-APACHE and LICENSE-MIT files (npm: "MIT OR Apache-2.0", v0.21.0, modified 2026-11-18), 29 stars, last commit 2026-11-19. It serves official docs to the model and can also do console actions (list channels, add a test channel, look up payments and reconciliation) after a browser console login; the README warns that API responses get passed to third-party AI services. — [portone-io/mcp-server](https://github.com/portone-io/mcp-server)
- A community PortOne plugin also exists at `pleaseai/claude-code-plugins/plugins/portone` (repo-level MIT). — [pleaseai/claude-code-plugins](https://github.com/pleaseai/claude-code-plugins)

**PayPal (official plugin, for completeness)**
- `paypal/AI-Toolkit`: Apache-2.0 LICENSE, 47 stars, last commit 2026-11-03, listed in Anthropic's official marketplace. — [paypal/AI-Toolkit](https://github.com/paypal/AI-Toolkit)

**Eligibility facts that decide which skill is even usable for a Korean individual**
- Polar pays out through Stripe Connect Express; South Korea is on Polar's payout-country list, and individuals are allowed where Stripe Connect Express supports the "individual" business type in that country (the page does not state this explicitly for Korea). — [Polar docs: supported countries](https://polar.sh/docs/merchant-of-record/supported-countries) (READ DIRECTLY)
- Creem lists South Korea among 88 supported countries with local bank transfer payouts; the page does not address individual vs company accounts. — [Creem docs: supported countries](https://docs.creem.io/merchant-of-record/supported-countries) (READ DIRECTLY)
- A Korean payments guide (checked against official pricing on 2026-09-10) lists Toss Payments at 3.4% for cards plus a 220,000 KRW sign-up fee and 110,000 KRW annual fee, PortOne free below 50M KRW monthly volume (PG fees separate), Polar Starter 5% + $0.50 (+1.5% non-US cards), Paddle 5% + $0.50 with a $100 minimum monthly payout; it stresses that being allowed to sign up as an individual is separate from the Korean obligation to register a business. — [agentic30.app payments hub](https://agentic30.app/payments) (READ DIRECTLY)
- A Korean blog (2026-02-12) states Toss Payments requires business registration with 2 weeks to 1 month of review, versus Creem needing no business registration with near-immediate approval. — [tech-donut.com](https://www.tech-donut.com/frontend/side-project-without-business-registration/) (READ DIRECTLY)

### Inferences
- Recommended bundle for the PAYMENT slot: Polar `setup-polar` + `polar-integration` from `polarsource/agent-toolkit` (MIT; official; a wizard that ends in a first product and checkout link; Korea is a payout country; sandbox MCP available). It is the only official skill whose stated purpose matches "first payment as fast as possible". Weakness: tiny adoption signal (8 stars) and a young repo (Jan 2026).
- Alternates: (1) Stripe `stripe-best-practices` (MIT; most actively maintained — API version bumped within the last week) for users who can open a Stripe account, i.e. not Korea-resident entities; (2) Creem `creem-api` (MIT; Korea supported; Korean bloggers recommend it for no-company founders); (3) Dodo `dodo-payments` skill (MIT); (4) Paddle skills (Apache-2.0; heavier onboarding, has a ready-made Lemon Squeezy migration skill).
- Lemon Squeezy should be removed from Revive's routing for new projects: it no longer accepts new stores and stops processing on 2027-03-31.
- For Korean domestic KRW card payments, a business registration is needed with Toss Payments, and the only official agent assets are Toss's docs MCP and PortOne's skills+MCP. PortOne's skills are the only official Korean-PG SKILL.md files, but the repo has no LICENSE file, so written permission or a "reference, don't copy" approach is the safe route.
- No public skill covers the decision Revive actually needs (residency + company status → provider → one hosted checkout link → verify one real payment). `zhuyansen/payment-guard` is the closest but is China-focused, 0 stars, and a CLI rather than a skill. Revive should self-write a thin router skill and delegate provider-specific work to the vendor skills. Docs a self-written skill should point to: Stripe Payment Links (https://docs.stripe.com/no-code/get-started), Polar supported countries and checkout links (https://polar.sh/docs/merchant-of-record/supported-countries), Creem docs (https://docs.creem.io), Dodo AI-agent docs (https://docs.dodopayments.com/developer-resources/build-with-ai-coding-agents), Paddle go-live checklist (https://developer.paddle.com/build/go-live-checklist.md), Toss LLM guide + llms.txt (https://docs.tosspayments.com/guides/v2/get-started/llms-guide, https://docs.tosspayments.com/llms.txt), PortOne MCP/CLI (https://github.com/portone-io/mcp-server).

### Gaps
- Whether Stripe Connect Express accepts the "individual" business type for South Korea (decisive for Polar without a company) was NOT VERIFIED against Stripe's own verification-requirements page; only first-hand Korean user reports support it (see Q3).
- Whether Stripe itself is unavailable to Korea-based merchants was NOT VERIFIED from stripe.com (the page is script-rendered); the only evidence is Korean users saying Stripe does not work for them (Q3) and Polar's reliance on cross-border Connect payouts.
- Dodo Payments' supported-country page returned 404; Korea eligibility for Dodo is NOT VERIFIED.
- Creem's and Dodo's rules on individual (no-company) sellers were not found on the pages read.
- The contents of Dodo's and Creem's SKILL.md files (API freshness, webhook handling quality) were not reviewed line by line.
- The official Lemon Squeezy shutdown post was not opened directly; dates come from a secondary blog and HN story dates.
- Stripe Managed Payments' supported-country list (reported as 37 countries by a third-party blog) was not verified.

---

## Q2. DEPLOYMENT: which skills / official plugins exist (Vercel, Netlify, Cloudflare, Railway, Fly.io, Render, Supabase, Firebase)?

### Takeaway
Every listed platform now has a vendor-official skill pack, and most are also in Anthropic's official plugin marketplace. For vibe-coded side projects the best single skill to bundle is Vercel's standalone `deploy-to-vercel` (from `vercel-labs/agent-skills`, 34.7k stars): it deploys previews by default, asks before pushing, and has a no-account fallback (`vercel deploy --temporary` with a claim URL) — but that repo has NO LICENSE file (README says MIT), so licensing must be clarified. Cleanly licensed alternates are `cloudflare/skills` (Apache-2.0), `railwayapp/railway-skills` (MIT) and `netlify/context-and-tools` (MIT).

### Cited Findings

**Vercel — two different official things**
- `vercel-labs/agent-skills` ("Vercel's official collection of agent skills"): 34,681 stars, last commit 2026-11-20, created 2025-12-08, 201 open issues+PRs. NO LICENSE FILE anywhere in the tree and no `license` field in package.json; the README has a "License" heading followed by "MIT". Skills include `deploy-to-vercel`, `vercel-cli-with-tokens`, `vercel-optimize`, `react-best-practices`, `web-design-guidelines`, etc. — [vercel-labs/agent-skills](https://github.com/vercel-labs/agent-skills)
- `deploy-to-vercel` (metadata: author vercel, version 4.0.0) always deploys as preview unless production is explicitly requested, requires asking the user before any git push, and includes a "No-Auth Fallback": `vercel deploy --temporary` needs no account and returns a temporary URL plus a claim URL and expiry. It is pure instructions around the Vercel CLI (no MCP). — [deploy-to-vercel SKILL.md](https://github.com/vercel-labs/agent-skills/blob/main/skills/deploy-to-vercel/SKILL.md)
- `vercel/vercel-plugin`: Vercel org, 344 stars, last commit 2026-11-20 (pushed 2026-11-22), created 2026-03-04, 70 open issues+PRs. LICENSE file contains only the short Apache-2.0 notice ("Copyright 2026 Vercel, Inc. Licensed under the Apache License, Version 2.0"), so GitHub reports NOASSERTION; plugin.json (v0.56.0) declares `Apache-2.0`. — [vercel/vercel-plugin](https://github.com/vercel/vercel-plugin)
- The plugin bundles 39 skill folders (e.g. `deployments-cicd`, `env-vars`, `domains`, `vercel-cli`, `bootstrap`, `ai-sdk`), 4 commands (`bootstrap`, `deploy`, `env`, `status`), 3 agents, hooks, and an `.mcp.json` for the remote OAuth server `https://mcp.vercel.com`. It is the `vercel` entry in Anthropic's official marketplace. — [vercel-plugin skills](https://github.com/vercel/vercel-plugin/tree/main/skills), [claude-plugins-official marketplace.json](https://github.com/anthropics/claude-plugins-official/blob/main/.claude-plugin/marketplace.json)
- Its `hooks/hooks.json` registers SessionStart hooks (a profiler and a two-part CLAUDE.md injection), a PostToolUse hook on `Skill` for telemetry, and a SessionEnd cleanup hook. — [vercel-plugin hooks.json](https://github.com/vercel/vercel-plugin/blob/main/hooks/hooks.json)

**Cloudflare**
- `cloudflare/skills`: Cloudflare org, Apache-2.0 LICENSE file, 3,424 stars, last commit 2026-11-17, created 2025-12-10, 44 open issues+PRs. 22 skill folders including `cloudflare`, `wrangler`, `workers-best-practices`, `workers-development`, `frameworks-on-cloudflare`, `nextjs-on-cloudflare`, `cloudflare-app-bootstrap`, `durable-objects`. `.mcp.json` points at remote `https://mcp.cloudflare.com/mcp`. Listed in Anthropic's official marketplace as `cloudflare`. — [cloudflare/skills](https://github.com/cloudflare/skills)

**Railway**
- `railwayapp/railway-skills`: Railway org, MIT LICENSE ("Copyright (c) 2026 Railway Corporation"), 345 stars, last commit 2026-11-18, created 2026-01-04. One plugin `railway` containing a single broad skill `use-railway` (sign-up/sign-in, create projects, deploy, databases, domains, troubleshooting), an `.mcp.json` for remote `https://mcp.railway.com`, and a PreToolUse hook on Bash described as "Auto-approve Railway API calls". Listed in Anthropic's official marketplace (git-subdir). — [railwayapp/railway-skills](https://github.com/railwayapp/railway-skills), [railway hooks.json](https://github.com/railwayapp/railway-skills/blob/main/plugins/railway/hooks/hooks.json)

**Netlify**
- `netlify/context-and-tools`: Netlify org, MIT LICENSE ("Copyright (c) 2025 Netlify"), 55 stars, last commit 2026-11-20, created 2025-11-26. 16 skills including `netlify-deploy`, `netlify-config`, `netlify-frameworks`, `netlify-functions`, `netlify-database`; `.mcp.json` points at remote OAuth server `https://mcp.netlify.com/mcp` (no token or local install). Listed in Anthropic's marketplace as `netlify-skills`. — [netlify/context-and-tools](https://github.com/netlify/context-and-tools)
- `netlify/netlify-mcp` ("Netlify's Official MCP server"): NO LICENSE FILE, 73 stars, last commit 2026-11-20. — [netlify/netlify-mcp](https://github.com/netlify/netlify-mcp)

**Render**
- `render-oss/skills`: MIT LICENSE ("Copyright (c) 2026 Render"), 106 stars, last commit 2026-11-20. 22 skills including `render-deploy` (v1.2.0, frontmatter `license: MIT`; Blueprint deploys require a pushed Git repo), `render-static-sites`, `render-web-services`, `render-postgres`, `render-debug`. `.mcp.json` points at `https://mcp.render.com/mcp` with an `Authorization: Bearer ${RENDER_API_KEY}` header. — [render-oss/skills](https://github.com/render-oss/skills)
- The Anthropic marketplace `render` entry points to a separate repo `render-oss/render-plugin-claude-code` (MIT, 1 star, last commit 2026-10-27). — [render-oss/render-plugin-claude-code](https://github.com/render-oss/render-plugin-claude-code)

**Fly.io**
- `superfly/skills`: MIT LICENSE ("Copyright (c) 2026 Fly.io"), 4 stars, last commit 2026-11-03; one plugin `fly` with skills `fly` and `brand`. Fly also publishes many "Sprites" (remote agent computers) plugins, e.g. `superfly/sprites-claude-plugin` (MIT, 4 stars), which are not app-hosting skills. — [superfly/skills](https://github.com/superfly/skills), [superfly/sprites-claude-plugin](https://github.com/superfly/sprites-claude-plugin)
- A September 2026 independent survey said Fly.io had only an experimental MCP built into flyctl and no general skills bundle; the repo above shows a small official skill now exists. — [Flavio Copes blog, updated 2026-09-19](https://flaviocopes.com/cloud-platform-plugins-ai-coding-agents/); contradicted by [superfly/skills](https://github.com/superfly/skills)

**Supabase (backend, not hosting)**
- `supabase/agent-skills`: MIT LICENSE ("Copyright (c) 2026 Supabase"), 3,121 stars, last commit 2026-10-02 (pushed 2026-11-12). Skills: `supabase`, `supabase-postgres-best-practices`; `.mcp.json` points at `https://mcp.supabase.com/mcp?features=docs`. — [supabase/agent-skills](https://github.com/supabase/agent-skills)
- The Anthropic marketplace `supabase` entry points to `supabase-community/supabase-plugin`: NO LICENSE FILE, 56 stars, last commit 2026-10-16. — [supabase-community/supabase-plugin](https://github.com/supabase-community/supabase-plugin)

**Firebase**
- `firebase/agent-skills`: Apache-2.0 LICENSE file, 521 stars, last commit 2026-11-09. 14 skills including `firebase-basics`, `firebase-hosting-basics`, `firebase-app-hosting-basics`, `firebase-auth-basics`, `firebase-firestore`, `firebase-security-rules-auditor`. The Anthropic marketplace `firebase` entry is a local MCP-integration plugin under `external_plugins/firebase`. — [firebase/agent-skills](https://github.com/firebase/agent-skills), [claude-plugins-official](https://github.com/anthropics/claude-plugins-official)

**Independent overview**
- Flavio Copes (independent developer-blogger) surveyed platform plugins in September 2026: he rates Vercel's plugin positively, calls Railway the simplest full setup after Vercel (installer adds CLI, skill, MCP config), calls Cloudflare one of the most complete (but says only the docs MCP gets daily use because Wrangler covers the rest), notes Render's MCP cannot update most existing resources, and advises starting with skills and adding MCP only when the agent must touch live resources, keeping approval prompts on for production. — [flaviocopes.com](https://flaviocopes.com/cloud-platform-plugins-ai-coding-agents/) (READ DIRECTLY)

### Inferences
- Recommended bundle for the DEPLOY slot: the single skill `deploy-to-vercel` from `vercel-labs/agent-skills`. Reasons: instructions-only (no MCP, no hooks, no telemetry), preview-first and ask-before-push safety defaults, and a no-login path that gets a public URL in one step — the lowest-friction route for non-professional builders. Blocker: no LICENSE file; the README's "MIT" statement is weaker than a license file, so either get confirmation from Vercel or have Revive install it at runtime (`npx skills add vercel-labs/agent-skills`) instead of redistributing the files.
- If a clean license is required for redistribution today: `railwayapp/railway-skills` (MIT; good when the revived project has a backend + database) or `cloudflare/skills` (Apache-2.0; good for static/Workers) or `netlify/context-and-tools` `netlify-deploy` (MIT).
- The full `vercel/vercel-plugin` is a poor thing to bundle inside another plugin: it carries its own hooks, CLAUDE.md injection, default-on telemetry and 39 skills. Better to recommend it as an optional install.
- Supabase and Firebase packs belong to a database/auth slot rather than the hosting slot, except Firebase Hosting/App Hosting skills.

### Gaps
- No install/usage counts were verified for any pack (directory "install" numbers are third-party and unverified).
- Whether `vercel deploy --temporary` works for all frameworks / has size limits was not checked beyond the skill text (it states temporary deployments do not work in CI or already-linked directories).
- The `superfly/skills` `fly` SKILL.md contents were not read.

---

## Q3. What do real users recommend (Reddit, X, Threads incl. Korean, YouTube, HN, blogs)?

### Takeaway
Direct evidence of users recommending a specific payment or deploy SKILL is essentially absent in what could be accessed; what exists is (a) Korean first-hand posts recommending Polar — and one blog recommending Creem — as the way to take payments without a company, (b) one independent blogger's platform-plugin survey favouring Vercel and Railway and "skills first, MCP later", and (c) a large, well-documented backlash against the Vercel plugin's telemetry in April 2026. Reddit, X and YouTube could not be mined, so "Reddit recommends X" claims cannot be supported from this research.

### Cited Findings

**Korean-language, payments without a company**
- Threads, @kima.coding (date NOT VERIFIED; the page could not be opened): recommends polar.sh for receiving overseas payments without a Korean corporation, says it is easier than Lemon Squeezy and lets you generate revenue without a business registration. — [Threads post](https://www.threads.com/@kima.coding/post/DGphTM_xDkg) (SEARCH SNIPPET ONLY)
- Threads, @joshproductletter (date NOT VERIFIED): a self-described non-developer says Stripe does not work for overseas payments so they use Polar; integration was not easy but succeeded once the AI was told to follow the procedure exactly. — [Threads post](https://www.threads.com/@joshproductletter/post/DJX_e9KT026) (SEARCH SNIPPET ONLY)
- Threads, @jaehwan.ai.workflow (reply, date NOT VERIFIED): says payment integration is the hardest part of building a SaaS and that they will look at Polar. — [Threads post](https://www.threads.com/@jaehwan.ai.workflow/post/DJa81hvyCB2) (SEARCH SNIPPET ONLY)
- Blog, 정기창 (kichang.info), 2026-03-26, first-hand Polar walkthrough as a Korean individual with no business registration: sign-up → organization → account review approved almost immediately → product → checkout link → button on site. Bad parts: payout needs a Stripe Connect Express account with a SWIFT/BIC code and an English account-holder name; the author says Toss Bank and K Bank do not support SWIFT and their own bank account lacked an English name, so linking failed and required a bank visit; fees 4% + $0.40 vs about 3% for a domestic PG; payouts are manual with a minimum. No AI agent/skill was used. — [kichang.info](https://kichang.info/blog/polar-payment-no-registration) (READ DIRECTLY)
- Blog, tech-donut.com, 2026-02-12 (no named author; recommends a paid-looking template flow, so treat as semi-promotional): recommends Creem as the best fit for employed people without a business registration (no setup or monthly fee, immediate approval, low rejection rate) and contrasts Toss Payments (business registration required, 220,000 KRW sign-up fee, 110,000 KRW annual fee, 2 weeks–1 month review, high rejection rate). — [tech-donut.com](https://www.tech-donut.com/frontend/side-project-without-business-registration/) (READ DIRECTLY)
- Guide site agentic30.app (checked 2026-09-10): groups options as global software (Paddle, Lemon Squeezy, Polar), domestic (Toss Payments, Payple, Payapp, PortOne), link-selling (Groble, Latpeed); says individual sign-up eligibility and the Korean duty to register a business are separate issues and that MoR handles customer sales tax but not the seller's Korean income reporting. — [agentic30.app/payments](https://agentic30.app/payments) (READ DIRECTLY)

**English-language, payments**
- Michael Tsai's blog roundup (2026-11-19) on the Lemon Squeezy shutdown: commenter "Matthew" argues MoR products are a poor fit for most SaaS vendors and recommends Stripe subscriptions with Stripe Tax; commenter "Nazmoon Munny" defends paying the MoR fee as a one-person store because the EU has no VAT threshold for non-EU sellers; commenter "metaning" criticises FastSpring's chargeback fees. Polar/Paddle/Creem/Dodo are not mentioned there. — [mjtsai.com](https://mjtsai.com/blog/2026/11/19/lemon-squeezy-shutting-down/) (READ DIRECTLY)
- Trustpilot reviews (dates not captured): some Polar reviewers report being approved and later offboarded or never receiving a payout; Dodo reviews are mixed, including an account blocked at payout time after about $1,000 and a positive report of accepting payments within 72 hours. — [Trustpilot: polar.sh](https://www.trustpilot.com/review/polar.sh), [Trustpilot: dodopayments.com](https://ca.trustpilot.com/review/dodopayments.com) (SEARCH SNIPPET ONLY)
- A blog on MoR rejections says Creem approved the author's application in about 8 hours and reports (unverified) Reddit accounts of repeat KYC reviews at Polar when payout thresholds are first hit and a mixed 2026 reputation for Dodo. — [shubhq.com](https://shubhq.com/blog/payment-processor-compliance-trap/) (SEARCH SNIPPET ONLY)
- Vendor or vendor-adjacent comparison content (treat as marketing, not user recommendation): Creem blog posts, Dodo blog posts, and multiple fungies.io comparison articles dominate search results for MoR comparisons. — [creem.io blog](https://creem.io/blog/best-merchant-of-record-saas-2026), [dodopayments.com blog](https://dodopayments.com/blogs/merchant-of-record-for-indie-developers), [fungies.io](https://fungies.io/polar-sh-vs-creem-vs-dodo-payments-mor-2026) (SEARCH SNIPPET ONLY)

**Deployment**
- Hacker News, "The Vercel plugin on Claude Code wants to read your prompts", 2026-04-09, 280 points, 111 comments. Paraphrased top comments: one user quotes the report that the plugin's skills get injected into sessions unrelated to Vercel, costing roughly 19k tokens per session; another calls the default-on telemetry that included full bash command strings a breach of trust; another generalises that agent plugins have an all-or-nothing permission model. — [HN item 47704881](https://news.ycombinator.com/item?id=47704881) (READ DIRECTLY via HN API)
- Follow-up HN submission "Vercel Claude Code plugin issues are now fixed", 2026-04-13 (2 points). — [HN item 47756030](https://news.ycombinator.com/item?id=47756030) (READ DIRECTLY via HN API, title/metadata only)
- Independent blogger survey (Flavio Copes, updated 2026-09-19): favourable to Vercel and Railway, "start with skills" advice (details in Q2). — [flaviocopes.com](https://flaviocopes.com/cloud-platform-plugins-ai-coding-agents/) (READ DIRECTLY)
- A deployment guide recommends denying direct production deploys by the agent (e.g. blocking `vercel --prod`) so releases go through git-based deploys. — [claudify.tech](https://claudify.tech/blog/claude-code-deployment-platforms) (SEARCH SNIPPET ONLY)

### Inferences
- Among Korean solo builders the dominant organic recommendation for "no company" payments is an MoR, with Polar named most often and Creem second; the recurring practical pain is not the code but payout setup (SWIFT-capable bank account with an English holder name) and account review. A Revive payment skill should surface those prerequisites before any coding.
- User sentiment toward heavyweight vendor plugins (hooks + telemetry + always-on context) is negative; lean instruction-only skills are the safer thing to bundle.
- There is real disagreement on MoR vs plain Stripe: some experienced sellers consider MoR unnecessary; solo non-company sellers value it. For the Revive audience (no company, Korea) the MoR side of that argument applies.

### Gaps
- Reddit (r/ClaudeAI, r/ClaudeCode, r/vibecoding, r/SaaS, r/indiehackers): NOT ACCESSIBLE. The search tool returns an error for reddit.com, `site:reddit.com` queries returned no Reddit results, and Reddit's public JSON search returned empty. No Reddit claim in these notes is first-hand.
- X/Twitter: no relevant posts surfaced. YouTube: no walkthrough of "Claude Code + payment skill → first paying customer" surfaced.
- Threads: pages could not be opened; three Korean posts are snippet-only and their dates are unverified (the search summary noted the Korean results span several months to over a year old).
- No evidence was found of any user publicly recommending a specific payment SKILL (Stripe/Polar/Creem/Dodo/Paddle packs) by name; adoption signals are limited to star counts.

---

## Q4. Verified repo facts per candidate (repo, owner, license, last commit, stars, install method, credentials, redistribution)

### Takeaway
All facts below were read from the GitHub API on 2026-11-22. Clean, redistributable licenses: Stripe (MIT), Polar (MIT), Dodo (MIT), Creem canonical repo (MIT), Paddle (Apache-2.0), Cloudflare (Apache-2.0), Railway (MIT), Netlify context-and-tools (MIT), Render (MIT), Supabase agent-skills (MIT), Firebase (Apache-2.0), Fly (MIT), Vercel plugin (Apache-2.0 by notice). Problem cases with NO LICENSE FILE: `vercel-labs/agent-skills`, `portone-io/cli`, `supabase-community/supabase-plugin`, `netlify/netlify-mcp`, `armitage-labs/creem-skills` (pointer repo only), `mainsoft-2024/toss-payments-docs-fetcher-skill`.

### Cited Findings

Format: repo — owner type — LICENSE file — stars — last commit — install — credentials — redistribution.

PAYMENTS
- [stripe/ai](https://github.com/stripe/ai) — official (Stripe org) — MIT LICENSE file — 2,077 — 2026-11-21 — Claude Code plugin (`stripe` in Anthropic's marketplace or the repo's own marketplace), `stripe agent setup`, or copy `skills/<name>` as a standalone folder — Stripe account; MCP uses OAuth at mcp.stripe.com; skill recommends restricted keys; a no-registration sandbox is possible via the CLI — MIT permits redistribution if the copyright and license notice are kept.
- [polarsource/agent-toolkit](https://github.com/polarsource/agent-toolkit) — official (Polar org) — MIT LICENSE file — 8 — 2026-11-17 — plugin manifests for Claude/Cursor/Gemini/OpenAI, or standalone skill folders — Polar account; remote MCP (production and sandbox endpoints); exact auth flow NOT VERIFIED — MIT permits redistribution with notice.
- [PaddleHQ/paddle-agent-skills](https://github.com/PaddleHQ/paddle-agent-skills) — official (Paddle org) — Apache-2.0 LICENSE file — 9 — 2026-11-19 — Claude Code plugin / standalone skills — Paddle account (sandbox and live); repo has a `.env.example` (contents not read) — Apache-2.0 permits redistribution; keep LICENSE and any NOTICE, mark modified files.
- [dodopayments/skills](https://github.com/dodopayments/skills) — official — MIT LICENSE file — 14 — 2026-11-09 — standalone skills / marketplace — Dodo account — MIT, redistributable with notice.
- [dodopayments/dodo-agent-plugin](https://github.com/dodopayments/dodo-agent-plugin) — official — MIT LICENSE file — 8 — 2026-11-09 — plugin (Claude Code, Codex, Cursor, OpenCode) with remote MCP — Dodo account; MCP auth NOT VERIFIED — MIT, redistributable with notice.
- [armitage-labs/creem](https://github.com/armitage-labs/creem) (skill at `packages/docs/skills/creem-api`) — official (Creem's GitHub org) — MIT LICENSE file — 36 — 2026-11-20 (skill folder: 2026-11-02) — marketplace `armitage-labs/creem` → `creem-api@creem-skills`, or copy the folder — Creem account + API key — MIT, redistributable with notice.
- [armitage-labs/creem-skills](https://github.com/armitage-labs/creem-skills) — official pointer repo — NO LICENSE FILE — 2 — 2026-08-12 — marketplace manifest only — n/a — do not copy from here; use the canonical MIT repo.
- [portone-io/cli](https://github.com/portone-io/cli) — official org (manifest owner field names an individual) — NO LICENSE FILE (package.json and Cargo.toml declare MIT; npm package declares MIT) — 0 — 2026-09-22 — `portone setup`, or Claude plugin `portone-integration` — PortOne console login; live payments require PG contracts — redistribution is legally ambiguous without a LICENSE file; ask PortOne or install at runtime.
- [portone-io/mcp-server](https://github.com/portone-io/mcp-server) — official — LICENSE-APACHE and LICENSE-MIT files (dual) — 29 — 2026-11-19 — MCP server via `npx -y @portone/mcp-server@latest` or a DXT file; needs Node 22.6+ — browser console login for console features — redistributable under either license.
- Toss Payments MCP — official npm package only, no public repo — npm metadata says MIT; no LICENSE file could be inspected — stars n/a — npm modified 2026-09-22 (v0.0.31) — MCP via `npx -y @tosspayments/integration-guide-mcp@latest` — no API key requirement stated in the docs (NOT VERIFIED) — referencing it in an `.mcp.json` is safer than vendoring. Sources: [npm registry](https://registry.npmjs.org/@tosspayments/integration-guide-mcp), [Toss LLM guide](https://docs.tosspayments.com/guides/v2/get-started/llms-guide)
- [pleaseai/claude-code-plugins](https://github.com/pleaseai/claude-code-plugins) — community — MIT LICENSE file — 17 — 2026-11-18 (tosspayments plugin folder: 2026-11-02) — Claude Code marketplace with `tosspayments` and `portone` plugins — none beyond the wrapped MCPs — MIT, redistributable with notice.
- [adrianwedd/lemonsqueezy-claude-skills](https://github.com/adrianwedd/lemonsqueezy-claude-skills) — community — MIT — 11 — 2026-01-06 — standalone skills — Lemon Squeezy API key — moot (platform closing).
- [zhuyansen/payment-guard](https://github.com/zhuyansen/payment-guard) — community individual — MIT LICENSE file — 0 — 2026-11-22 — Python CLI (`pip install payment-guard`), not a skill — no keys — MIT; aimed at mainland China / Hong Kong sellers.
- [paypal/AI-Toolkit](https://github.com/paypal/AI-Toolkit) — official — Apache-2.0 — 47 — 2026-11-03 — plugin in Anthropic's marketplace — PayPal developer account.

DEPLOYMENT
- [vercel-labs/agent-skills](https://github.com/vercel-labs/agent-skills) — official (Vercel Labs org) — NO LICENSE FILE (README states MIT) — 34,681 — 2026-11-20 — standalone skill folders (`npx skills add vercel-labs/agent-skills`; zips provided per skill) — Vercel CLI; account optional thanks to the temporary-deploy fallback — redistribution rests only on a README statement; confirm before bundling.
- [vercel/vercel-plugin](https://github.com/vercel/vercel-plugin) — official — LICENSE file = Apache-2.0 short notice (GitHub: NOASSERTION), plugin.json `Apache-2.0` — 344 — 2026-11-20 — Claude Code plugin (`vercel` in Anthropic's marketplace; `npx plugins add vercel/vercel-plugin`) — Vercel account; MCP via OAuth — Apache-2.0 terms apply, but the file is not the full license text.
- [cloudflare/skills](https://github.com/cloudflare/skills) — official — Apache-2.0 LICENSE file — 3,424 — 2026-11-17 — plugin (`cloudflare` in Anthropic's marketplace) or `npx skills add` for skills only — Cloudflare account; Wrangler login / remote MCP — redistributable under Apache-2.0.
- [railwayapp/railway-skills](https://github.com/railwayapp/railway-skills) — official — MIT LICENSE file — 345 — 2026-11-18 — plugin (`railway` in Anthropic's marketplace) or Railway's agent installer — Railway account (the skill itself covers sign-up) — MIT, redistributable with notice.
- [netlify/context-and-tools](https://github.com/netlify/context-and-tools) — official — MIT LICENSE file — 55 — 2026-11-20 — plugin (`netlify-skills` in Anthropic's marketplace) — Netlify account; MCP via OAuth, no token — MIT, redistributable with notice.
- [netlify/netlify-mcp](https://github.com/netlify/netlify-mcp) — official — NO LICENSE FILE — 73 — 2026-11-20 — MCP server — Netlify OAuth — do not vendor.
- [render-oss/skills](https://github.com/render-oss/skills) — official — MIT LICENSE file — 106 — 2026-11-20 — `render skills install`, plugin, or `npx skills add` — Render account; MCP needs `RENDER_API_KEY` — MIT, redistributable with notice.
- [superfly/skills](https://github.com/superfly/skills) — official — MIT LICENSE file — 4 — 2026-11-03 — plugin / skills — Fly.io account — MIT.
- [supabase/agent-skills](https://github.com/supabase/agent-skills) — official — MIT LICENSE file — 3,121 — 2026-10-02 — `npx skills add supabase/agent-skills` / plugin — Supabase account; remote MCP — MIT.
- [supabase-community/supabase-plugin](https://github.com/supabase-community/supabase-plugin) — vendor community org — NO LICENSE FILE — 56 — 2026-10-16 — plugin (`supabase` in Anthropic's marketplace) — Supabase account — do not vendor.
- [firebase/agent-skills](https://github.com/firebase/agent-skills) — official — Apache-2.0 LICENSE file — 521 — 2026-11-09 — plugin manifests for several agents — Google/Firebase account, Firebase CLI — Apache-2.0.
- [anthropics/claude-plugins-official](https://github.com/anthropics/claude-plugins-official) — Anthropic — Apache-2.0 — 47,920 — 2026-11-21 — the marketplace that lists stripe, paypal, vercel, cloudflare, netlify-skills, railway, render, supabase, firebase, neon; it has no polar, paddle, dodo, creem, lemon squeezy, toss or portone entries.

### Inferences
- MIT and Apache-2.0 both allow bundling inside another plugin; practical obligations are to ship each upstream LICENSE (and NOTICE where present) next to the copied skill and, for Apache-2.0, to mark any modified files.
- Vendoring freezes content: Stripe's skill hard-codes an API version that changed several times in 2026, so a bundled copy needs an update pipeline (pin a commit SHA and refresh on release) or should be installed from the upstream marketplace at runtime.
- "No LICENSE file" repos default to all-rights-reserved regardless of README or manifest claims; for `vercel-labs/agent-skills` and `portone-io/cli` the manifest/README statements signal intent to be MIT but are weaker than a license file.

### Gaps
- Open-issue counts include PRs; no issue-by-issue review of security bugs was done.
- Credential/auth specifics for the Polar, Dodo and Paddle MCP servers (OAuth vs API token) were NOT VERIFIED.
- Whether any of these vendors' trademarks/brand guidelines restrict naming a bundled copy was not researched.

---

## Q5. Skill (instructions) vs MCP server (tools) for each candidate

### Takeaway
Almost every vendor now ships a hybrid: SKILL.md instruction folders plus a plugin manifest whose `.mcp.json` points to a vendor-hosted remote MCP server. The skills can be bundled alone; the MCP part is only a URL (remote HTTP/OAuth) for Stripe, Polar, Dodo, Vercel, Cloudflare, Railway, Netlify, Supabase and Render, but is locally executed npm code (`npx -y ...@latest`) for Toss Payments and PortOne.

### Cited Findings
- Stripe: skills + commands + hooks + remote HTTP MCP `https://mcp.stripe.com`. — [stripe/ai Claude plugin](https://github.com/stripe/ai/tree/main/providers/claude/plugin)
- Polar: 4 skills + remote HTTP MCP (production and sandbox). — [polarsource/agent-toolkit](https://github.com/polarsource/agent-toolkit)
- Paddle: 13 skills; docs MCP wired by the plugin per the changelog. — [PaddleHQ/paddle-agent-skills](https://github.com/PaddleHQ/paddle-agent-skills), [Paddle changelog](https://developer.paddle.com/changelog/2026/agent-skills-claude-code-plugin) (SEARCH SNIPPET ONLY)
- Dodo: skills repo (instructions) and a separate plugin adding remote HTTP MCP `https://mcp.dodopayments.com/mcp`. — [dodopayments/dodo-agent-plugin](https://github.com/dodopayments/dodo-agent-plugin)
- Creem: skill only (API reference + patterns); no MCP in the marketplace manifest. — [armitage-labs/creem-skills](https://github.com/armitage-labs/creem-skills)
- Toss Payments: MCP only (docs search; stdio via npx). — [Toss LLM guide](https://docs.tosspayments.com/guides/v2/get-started/llms-guide)
- PortOne: skills that depend on the PortOne MCP (stdio via `npx -y @portone/mcp-server@latest`) plus a CLI. — [portone-io/cli](https://github.com/portone-io/cli)
- Vercel `deploy-to-vercel`: skill only, drives the Vercel CLI. — [deploy-to-vercel SKILL.md](https://github.com/vercel-labs/agent-skills/blob/main/skills/deploy-to-vercel/SKILL.md)
- Vercel plugin: skills + commands + agents + hooks + remote OAuth MCP `https://mcp.vercel.com`. — [vercel/vercel-plugin](https://github.com/vercel/vercel-plugin)
- Cloudflare: skills + remote MCP `https://mcp.cloudflare.com/mcp`; `npx skills add` installs skills only. — [cloudflare/skills](https://github.com/cloudflare/skills), [flaviocopes.com](https://flaviocopes.com/cloud-platform-plugins-ai-coding-agents/)
- Railway: one skill + remote MCP `https://mcp.railway.com` + an auto-approve PreToolUse hook. — [railwayapp/railway-skills](https://github.com/railwayapp/railway-skills)
- Netlify: skills + remote OAuth MCP `https://mcp.netlify.com/mcp`. — [netlify/context-and-tools](https://github.com/netlify/context-and-tools)
- Render: skills + remote MCP requiring a bearer API key from the environment. — [render-oss/skills](https://github.com/render-oss/skills)
- Supabase: skills + remote docs MCP. Firebase: skills (the Anthropic marketplace entry is the MCP integration). Fly: skills. — [supabase/agent-skills](https://github.com/supabase/agent-skills), [firebase/agent-skills](https://github.com/firebase/agent-skills), [superfly/skills](https://github.com/superfly/skills)

### Inferences
- Bundling implications: (1) skill folders are static text — low risk, but go stale; (2) a remote-MCP entry adds live account tools (create products, deploy, read logs) under the user's OAuth grant — Revive would be shipping a capability that can change real resources, so approval prompts should stay on; (3) a stdio `npx ...@latest` MCP executes unpinned third-party code on the user's machine at every start — a supply-chain exposure Revive would inherit if it ships that config, so pin a version; (4) hooks shipped by vendor plugins (Stripe, Vercel, Railway) run code in every session and should not be silently inherited.
- The lowest-risk composition for Revive is: bundle instruction-only skills, and have the skill prompt the user to add the vendor's MCP themselves only when needed.

### Gaps
- Tool inventories of the remote MCP servers (what write actions each exposes) were not enumerated.

---

## Q6. Known complaints and risks (outdated APIs, secret handling, webhooks, abandoned repos, telemetry)

### Takeaway
The biggest documented incident is the Vercel plugin's April 2026 telemetry/prompt-injection controversy (since narrowed, but telemetry is still on by default); other concrete risks are Stripe's plugin hooks that report skill usage and inject feedback prompts, Railway's auto-approve hook, stale forks of fast-moving skills, licence-less repos, misattributed community wrappers, and the Lemon Squeezy shutdown. No abandoned repos were found among official candidates — all had commits within the last eight weeks.

### Cited Findings
- Vercel plugin, April 2026: a developer reported the plugin showed a telemetry consent question in non-Vercel projects via a UserPromptSubmit hook with an empty matcher, sent session/tool/skill events to telemetry.vercel.com by default, and stored a device UUID; coverage reached #1 on Hacker News (280 points, 111 comments, 2026-04-09). The author later reported that prompt collection, the injected consent flow, bash-command telemetry and the persistent device UUID were removed. — [HN item 47704881](https://news.ycombinator.com/item?id=47704881) (READ DIRECTLY); [TechRadar](https://www.techradar.com/pro/that-felt-wrong-dev-uses-claude-to-expose-why-a-popular-no-code-platform-wants-to-read-all-your-prompts), [claudeissues.com issue 43778](https://claudeissues.com/issue/43778-vercel-plugin-uses-userpromptsubmit-hook-for-undisclosed-telemetry-consent-injec), [author's follow-up](https://hn.jakechampion.name/reader/https://akshaychugh.xyz/writings/png/vercel-plugin-telemetry-update) (SEARCH SNIPPET ONLY)
- Current state per the plugin's README: telemetry is still ON by default, disabled with `VERCEL_PLUGIN_TELEMETRY=off`; it sends a daily active ping, a random installation UUID, harness category, plugin version and the names of the plugin's own skills when invoked; it states that prompt text, bash commands, file paths, project names and account IDs are not collected, and that the prompt-injection hooks are no longer registered by default. — [vercel/vercel-plugin README](https://github.com/vercel/vercel-plugin/blob/main/README.md)
- The plugin still injects content into CLAUDE.md context at session start (two `inject-claude-md` hook steps). — [vercel-plugin hooks.json](https://github.com/vercel/vercel-plugin/blob/main/hooks/hooks.json)
- Stripe plugin hooks: `hooks.json` is described as prompting agents for Stripe feedback and giving CLI setup guidance; the PostToolUse script reports Stripe skill usage (`reportSkillUsage`) and, on a sampled basis, injects a feedback message into the agent's context, unless telemetry is disabled. — [stripe/ai hooks.json](https://github.com/stripe/ai/blob/main/providers/claude/plugin/hooks/hooks.json), [postToolUse.mjs](https://github.com/stripe/ai/blob/main/providers/claude/plugin/scripts/lifecycle/postToolUse.mjs)
- Railway plugin registers a PreToolUse hook on Bash that auto-approves Railway API calls, i.e. it reduces permission prompts for a tool that can change infrastructure. — [railway hooks.json](https://github.com/railwayapp/railway-skills/blob/main/plugins/railway/hooks/hooks.json)
- Stale copies: third-party mirrors of `stripe-best-practices` pin older API versions than upstream (upstream: 2026-11-18.endive). — [stripe-best-practices SKILL.md](https://github.com/stripe/ai/blob/main/skills/stripe-best-practices/SKILL.md); mirrors: [skills.sh](https://skills.sh/stripe/agent-toolkit/stripe-best-practices) (SEARCH SNIPPET ONLY)
- Deprecations: Paddle's local MCP server repo is deprecated in favour of the remote one; Dodo deprecates `POST /payments` and `POST /subscriptions` in favour of Checkout Sessions; PortOne V1 and V2 are incompatible APIs that must not be mixed. — [PaddleHQ/paddle-mcp-server](https://github.com/PaddleHQ/paddle-mcp-server), [Dodo docs](https://docs.dodopayments.com/developer-resources/build-with-ai-coding-agents) (SEARCH SNIPPET ONLY), [portone-guide SKILL.md](https://github.com/portone-io/cli/blob/main/skills/portone-guide/SKILL.md)
- Data exposure: PortOne's MCP README warns that API responses (e.g. payment records) are forwarded to the third-party AI service. — [portone-io/mcp-server README](https://github.com/portone-io/mcp-server/blob/main/README.md)
- Misattribution: the community `pleaseai` tosspayments plugin lists "Toss Payments" as author and a tosspayments-org repository URL. A registry page for the same publisher's PortOne plugin showed a "Medium" security rating with a review-before-use note. — [pleaseai tosspayments plugin](https://github.com/pleaseai/claude-code-plugins/tree/main/plugins/tosspayments), [tessl registry: pleaseai/portone](https://tessl.io/registry/pleaseai/portone) (SEARCH SNIPPET ONLY)
- Unpinned execution: Toss and PortOne MCP configs run `npx -y <package>@latest`. — [Toss LLM guide](https://docs.tosspayments.com/guides/v2/get-started/llms-guide), [portone-io/cli .mcp.json](https://github.com/portone-io/cli/blob/main/.mcp.json)
- Platform risk: Lemon Squeezy stops processing on 2027-03-31; MoR account risk is reported by reviewers for Polar (offboarding, unpaid payouts) and Dodo (blocked at payout). — [mjtsai.com](https://mjtsai.com/blog/2026/11/19/lemon-squeezy-shutting-down/) (READ DIRECTLY), [Trustpilot: polar.sh](https://www.trustpilot.com/review/polar.sh) (SEARCH SNIPPET ONLY)
- Positive security defaults in the leading candidates: Stripe's skill mandates restricted keys and has a dedicated `references/security.md`; Vercel's deploy skill deploys previews by default, requires approval before pushing, and tells the agent not to share the claim link. — [stripe-best-practices](https://github.com/stripe/ai/tree/main/skills/stripe-best-practices), [deploy-to-vercel SKILL.md](https://github.com/vercel-labs/agent-skills/blob/main/skills/deploy-to-vercel/SKILL.md)
- Maintenance: every official candidate had a default-branch commit between 2026-09-22 (portone-io/cli) and 2026-11-21 (stripe/ai); none is archived. — repo links in Q4

### Inferences
- If Revive bundles a vendor plugin wholesale it inherits that vendor's hooks and telemetry; copying only the `skills/<name>` folders avoids this.
- For a first real payment the dominant failure modes are non-code: account review rejection, payout-account prerequisites, and (for Korean PGs) business registration — a Revive skill should check these before generating code.
- Webhook-handling quality of the Polar, Creem, Dodo and Paddle skills remains unassessed; Revive's verification step should independently test signature verification and idempotency with a sandbox payment.

### Gaps
- I found no public reports of insecure secret handling or webhook bugs specific to the Polar, Creem, Dodo, Paddle or PortOne skills — absence of evidence only; their SKILL.md bodies were not audited.
- The current Vercel plugin code was not audited against its README telemetry claims.
- What Stripe's `reportSkillUsage` transmits, and the name of its telemetry opt-out variable, were NOT VERIFIED (only the hook entry script was read).
