# Wiki Log
*Append-only. Format: `## [YYYY-MM-DD] action | description`*
*AI maintains this. Never delete entries — only append.*

---

## [2026-08-07] root-triage | AI-as-Dev — Multi-Agent Orchestration → new concept; Feature All-in-One SM Hub → hole-fill; Exo Enterprise Content Workflow → hole-fill (promote-candidate)
### [2026-08-07] root-triage | Batch 2 (4h): Buzz UI functionality into Flow OS → already wiki'd (Team-surface appendix); fixed broken frontmatter (ccompiled→compiled+promoted-to). Q-A BUILDING THE ACTUAL SOFTWARE → hole-fill (reference frontmatter; OSS-assembly multi-agent workflow, relates to AI-as-Dev concept). Claude Code Agent (OS) Dashboard → hole-fill (placeholder, YT link only). AEO Report of Exo Home Page → hole-fill (reference frontmatter; exoent.co 67/100, sitemap/canonical/JSON-LD/freshness/citations gaps → website action area).
### [2026-05-13] setup | Created raw/, index.md, log.md — LLM wiki upgrade (Phase 0)
### [2026-05-13] setup | Batch-tagged all root notes with vault-context: business or vault-context: personal via PowerShell
### [2026-05-13] setup | Notes without frontmatter flagged for manual YAML addition

### [2026-07-07] restructure | Wiki consolidated into WIKI/ folder
- Deleted `vault-index.md` (broken auto-generated duplicate from June 24 session)
- Deleted `vault-log.md` (1-entry duplicate of log.md)
- Moved `index.md` and `log.md` from vault root into `WIKI/`
- Moved `raw/` from vault root into `WIKI/raw/` (old contents — Q-A drafts — moved to root as personal notes)
- Renamed `WIKI/README/` to `WIKI/references/` (holds Karpathy source notes: llm-wiki.md, llm-knowledge-base.md)
- Created `WIKI/SCHEMA.md` — wiki configuration file adapted from Karpathy's pattern for this vault
- Updated `Vault-Directions.md` — relaxed "no folders" rule, documented WIKI/ folder
- Updated `agents/CLAUDE.md` — added pointer to WIKI/SCHEMA.md for wiki operations
- Created `WIKI-SETUP-LOG.md` at vault root documenting the full restructure

### [2026-07-07] ingest | Hormozi — "The Only 4 Ways To Scale A Service Business"
- Source: YouTube transcript (https://www.youtube.com/watch?v=Dq3R3uS0sQ4)
- Saved to `raw/hormozi-4-ways-to-scale-service-business.md` with frontmatter + sha256
- Created `concepts/four-ways-to-scale-service-business.md` — framework breakdown, decision matrix, Exo relevance
- Created `entities/alex-hormozi.md` — entity page with frameworks, portfolio, quotes
- Updated `index.md` — added 3 new pages (1 entity, 1 concept, 1 raw source)
- Deleted original transcript from `agent-workspace/NOTEPAD/Transcripts/yt-transcript.md`

### [2026-07-07] setup | Auto-ingest cron + MCP filesystem server deployed
- Created Hermes cron job `wiki-auto-ingest` (every 2h) on VPS — watches WIKI/raw/ for new sources, compiles wiki pages, updates index/log, git pushes
- Installed `mcp` Python package on VPS Hermes venv
- Added MCP filesystem server to VPS Hermes config — `mcp_servers.vault` pointing at `/home/exo/jay-obsidian-main/`
- 14 MCP tools now available to any Hermes conversation: read_file, write_file, edit_file, list_directory, directory_tree, search_files, etc.
- Gateway restarted successfully — Telegram + Photon connected, MCP vault server connected (14 tools discovered)
- This means: (1) drop sources in WIKI/raw/ → wiki auto-compiles every 2h, (2) any Hermes conversation can read/write the vault directly via MCP tools

### [2026-07-10] query | Exo Vault meta-leverage system
- Read two-layer architecture docs in `agent-workspace/Exo Enterprise/Exo-Vaults/` and `strategy-notes/vault-ecosystem-strategy.md`
- Read `agent-workspace/KNOWLEDGE-SYSTEM.md` and `company-ssot/07-exo-delivery-os.md`
- Read canonical Karpathy references in `WIKI/references/`
- Created `concepts/exo-vault-meta-leverage-system.md` to connect personal Forge, Exo company operating vault, client vaults, Flow OS, and Delivery OS
- Updated `index.md`

### [2026-07-10] query | Exo system boundary map
- Captured the clearest system-boundary framing as its own artifact
- Created `concepts/exo-system-boundary-map.md`
- Clarified ownership boundaries for `agent-workspace`, `jay-obsidian-main`, client vaults, and Flow OS
- Added exploratory role for EXA AI / Exo Academy as the training, synthesis, and education namespace fed by (not exclusive) vault knowledge
- Updated `index.md`

### [2026-07-13] compile | Vault compile pass — 17 files changed since last compile
- 15 vault root/agent files changed since 2026-07-10 compile (all AUM/BOMT brainstorms + Flow OS handoff)
- Added AUM + BOMT concept page to wiki index (now 6 pages total)
- Added `references/exo-system-boundary-map ref.md` to references section
- Added "Recently Changed" section to index.md cataloging all 17 changed files with type + summary
- Key new captures: Jay's "Quick Run Through" reaction (prototype not null), Updated Harnesses Transcript (file trees vs frameworks), Agents-Inbox (executor loop spec v0.1 promoted to §22), Flow OS backend handoff (emit_diff + Reflex Arc v1 LIVE)
- Updated `index.md`

### [2026-07-13] milestone | Flow OS Diff Write Contract LIVE — emit_diff() chokepoint + Reflex Arc v1
- New Supabase project `jdjyiyeddpfzpgrqffav` (old one deleted by Supabase after 90-day pause; Dec-2025 backup deliberately not restored — error-detour schema)
- emit_diff() SECURITY DEFINER RPC = the one door into diffs; vocabulary-validated (unknown/retired/unregistered all rejected); RLS on client_id; client zero Exo = `e0000000-0000-4000-8000-000000000001`
- Reflex Arc v1 (FastAPI, `flow-os/backend/`) verified end-to-end ~1s: emit → realtime → rule fires → rule_executions row; 3 live ops rules; 14 diffs in the moat (7 backfilled from jsonl era)
- brand namespace seeded (8 stub events); `handoff=updated` retired (active=false)
- This unblocks the executor loop in `concepts/aum-bomt-intelligence-compounding-vehicle.md` §22 (diffs metadata/actor columns designed for it); remaining: B.3 Hermes agent_handle, B.4 24/7 VPS deploy
- Full session record: `agent-workspace/log/2026-07-13-session-diff-write-contract.md` · Handoff for next agent: `agents/handoff-2026-07-13-flow-os-backend.md`

### [2026-07-13] infra | Flow OS repo cloned to VPS
- Cloned `jaysteel-bit/flow-os` to `~/flow-os/` on the Contabo VPS (147.93.181.36)
- Generated SSH key on VPS (`~/.ssh/id_ed25519`, `exo@vps-flow-os`); registered as GitHub deploy key on the repo (ID 157202502, read+write)
- VPS `git pull` verified working autonomously — no agent forwarding needed for future operations
- No auto-sync cron yet (manual pull for now); `state/infra.md` updated

### [2026-07-19] compile | Vault compile pass — 2 files changed since last compile
- 2 vault notes changed since 2026-07-13 compile:
  - `Google AI Pricing Model v0.1.md` (dump, 142 lines) — Google AI's value-capture hybrid pricing model for post-AI infrastructure firms. 4-layer architecture (implementation fee + SaaS subscription + usage metric + value-share), 90-day BOT frontend, multi-department backend monetization. Maps directly to Exo offer stack + AUM model.
  - `References/Reference - Old Captions.md` (reference, 194 lines) — Personal social media captions/lyrics. Not wiki material — skipped.
- Created concept page: `concepts/post-ai-pricing-architecture.md` (now 7 pages total)
- Updated `index.md` — added new concept entry, bumped page count, refreshed last-updated date
- No promotion candidates this pass (pricing note is strategic thinking; OFFER-BIBLE.md remains the canonical pricing decision home)

### [2026-07-31] compile | Vault compile pass — 6 files changed since last compile (index was 12 days stale, 5-day cadence)
- Triggered by the `FORGE WIKI/index.md` staleness flag in `agent-workspace/BRIEF.md` (12 days old, expected ≤5). The heartbeat owns this loop; it had not fired since 2026-07-19.
- 6 vault notes changed since the 2026-07-19 compile:
  - `flow-os-desktop-shell-ui-direction-2026-07-27.md` (notepad, 193 lines) — full Flow OS desktop shell UI direction: ChatGPT/Codex + Hermes teardown, the Company Pulse correction (pill + rotating hero headlines + KPI row, NOT status-bar-only), phased moves, success criteria.
  - `Flow OS Desktop UI-UX.md` (dump, 90 lines) — Grok conversation: Tauri vs Electron, onboarding installer, Flow OS MCP + API integration.
  - `Exo Launch - Air Build.md` (dump, 210 lines) — Air.inc creative-ops teardown mapped onto Exo Launch; four ComfyUI integration paths (Comfy Cloud API → RunPod → MCP → fork, with verdicts); Tauri assessment that concluded "wrap the whole OS, not just Launch."
  - `Grok Open Ship Opensource Email Convo.md` (dump, 55 lines) — cold-outreach vs nurture tool split; OpenShip self-hosted mail rejected on deliverability. Tactical, not a framework — no page.
  - `Exo Dept Lead Magnet Quiz Funnel.md` (dump, 5 lines) — department-orb quiz lead magnet. Too thin to compile; pairs with the fuller `agent-workspace/NOTEPAD/lead-magnet-quiz-funnel.md`.
  - `Attachments/Top 4 Scarcest Skills.md` (reference, 1 line) — a single pasted image, no text. Skipped.
- **Created concept page:** `concepts/flow-os-desktop-shell.md` — "Flow OS Desktop Shell — Tauri + Company Pulse Theater." Clears the SCHEMA threshold on both counts (central to one source, present in 3). Three decisions captured: Tauri over Electron; wrap all of Flow OS rather than Exo Launch alone; Company Pulse is product identity and survives the shell revamp. Links to [[Exo System Boundary Map]], [[AUM + BOMT — The Intelligence Compounding Vehicle]], [[Exo Vault Meta-Leverage System]].
- `WIKI/raw/` scanned — no new raw sources since 2026-07-07 (hormozi transcript only). Nothing to ingest.
- **Index drift fixed** (found while reconciling, all pre-existing):
  - `Exo System Boundary Map` was listed under **Entities** but lives in `concepts/` — moved to Concepts.
  - `references/exo-system-boundary-map ref.md` was listed but **does not exist on disk** (added by the 2026-07-13 pass; never created or since deleted) — removed the dead row.
  - Page count said 7 while only 6 pages existed. Now genuinely 7 (6 concepts + 1 entity) with the new page, and the count is broken out so it can be checked at a glance.
  - `SCHEMA.md` was not listed anywhere in the index despite being the read-first file — added under References.
  - "Recently Changed" still said "since 2026-07-10" while the log had moved on twice — refreshed to the 2026-07-19 baseline, with the older AUM/BOMT cluster summarized into a carried-forward note instead of re-listing 17 rows.
- No promotion candidates to the Reservoir this pass — the desktop shell decisions are already codified there at `Exo Enterprise/departments/product/flow-os/DESKTOP-SHELL-UX.md` (status: locked). The ComfyUI integration ladder from `Exo Launch - Air Build.md` is the one open item worth promoting once a build path is chosen.

### [2026-08-04] root-triage | Pipeline live + hot backlog pass
- **Pipeline:** SCHEMA §1b expanded to **dumps + loose root notes**; HEARTBEAT owns root triage (cap 3/tick); vault skill rewritten (VPS path, WIKI/, `/vault triage`); Dump Template gains `compiled`/`acted-on`/`backlog`; heartbeat pinned `deepseek/deepseek-v4-flash-0731` (chat stays grok-4.5).
- **Reservoir:** `HEARTBEAT.md`, `KNOWLEDGE-SYSTEM.md`, `Skills/vault/SKILL.md`, `state/infra.md` updated. Doctrine: thinking→Forge, decisions→agent-workspace; never body-dump into Reservoir.
- **Hot notes triaged:**
  - `emitt-diff talk.md` → created `concepts/emit-diff-chokepoint-scale.md` (acted-on + compiled)
  - `Flow OS + Buzz.md` → created `concepts/flow-os-team-surface.md` + frontmatter (loose root now in system)
  - `Exo AUM Business Model v2.md` → hole-fill + AUM concept appendix (DRAFT scores flagged)
  - `Steel Pants + Steel Belt.md` → hole-fill only (below wiki threshold)
- Index refreshed: 9 pages (8 concepts + 1 entity).
- No SSOT promote this pass (no new locked pricing/offer decisions). Queue remains large historically — heartbeat drains cap 3 ongoing.

### [2026-08-04] root-triage | Connector taxonomy + desktop-shell/AEO hole-fill
- **Queue select:** 3 loose root/dump notes processed (cap 3), none newer than the 17:53 stamp — routine drain of the historical backlog, not a new burst.
- `Paycom Flow Integration— Seven Hills B2B Insight.md` → **Wiki** `concepts/flow-os-connector-taxonomy.md` (Tier 1 unified / Tier 2 direct / SFTP stance — don't native-build Paycom) + **Reservoir** `agent-workspace/state/tasks/flow-os-connector-taxonomy.md` (build tagged connector list). Frontmatter added (type: research, acted-on true, compiled 2026-08-04).
- `Flow OS Desktop UI-UX.md` → hole-fill only. Already a listed source on `concepts/flow-os-desktop-shell.md`; marked acted-on + compiled, no new page (avoid duplicate).
- `AEO Calculator Lead Magnet.md` → hole-fill only (thin — 1-line idea). acted-on, compiled, backlog: build the AEO visibility calculator, pair with lead-magnet funnel.
- Index refreshed: **10 pages (9 concepts + 1 entity)**.
- No SSOT promote (connector stance is decision-grade for Flow OS build order but lives in a task until built; not a new locked offer/pricing).
- Queue remains large historically (~100 loose root notes untouched) — heartbeat drains cap 3 ongoing; many are evergreen quotes/one-liners below page threshold and will hole-fill only.

### [2026-08-05] root-triage | AUM commitment + concierge + onboarding (hole-fill, cap 3)
- `AUM + BOMT Model Commitment.md` → hole-fill only. Already a named source on `concepts/aum-bomt-intelligence-compounding-vehicle.md` (fully synthesized); marked acted-on + compiled, no duplicate page. Backlog false.
- `Exo Concierge Support — Webex.md` → hole-fill only (thin — Webex/Flow OS concierge + SOP-in-EXA). Below page threshold. acted-on, compiled, backlog: create concierge SOP + document 40-min Webex session workflow.
- `Dump - Exo Onboarding Strategy.md` → hole-fill only (onboarding messaging, EXA-as-utility-wedge, luxury/concierge positioning). Below page threshold. acted-on, compiled, backlog: draft onboarding flow + clarify BOM/T.
- No new wiki pages, no index change (0 additions). No SSOT promote (no new locked decisions — all operational/strategic musings below decision grade).
- Queue still large (~110 loose root notes) — draining cap 3 ongoing; most are evergreen quotes/one-liners that will hole-fill only.

### [2026-08-05] root-triage | AUM pure structure + 2-headed model + motion graphics (hole-fill, cap 3)
- `AUM PURE STRUCTURE - Inputs + Outputs Draft.md` → **hole-fill into** `concepts/aum-bomt-intelligence-compounding-vehicle.md` (new appendix). Price-agnostic structural framing: the one equation, two controllable levers (decision volume × value/decision), constraint chain (#1 = Flow OS instrumentation), open unit question (what is a "decision"). Added Jay's correction flag prominently: brainstormed numbers are fictitious projections, NOT fact — clean pricing-as-fact places before treating as baseline. Frontmatter added + acted-on/compiled. Backlog: define the "decision" unit + provable value-share methodology.
- `Exo 2 Headed Monster Model.md` → hole-fill only. AUM+BOMT two-headed structure (BOMT machine + permanent roll-up) already covered by `concepts/aum-bomt-*` + EXO-HOLDCO-MAP. Marked acted-on + compiled; no duplicate page.
- `Motion Graphics Websites - Used for Business.md` → hole-fill only (thin — Jitter.video + Malloy.sg for brand content). Below page threshold. acted-on, compiled; backlog: evaluate motion-graphics tools for content production.
- No new wiki pages, no index change (appended to existing concept). No SSOT promote (no new locked decision — correction is directional, not a new decision).
- Queue still large (~100 loose root notes) — draining cap 3 ongoing; most evergreen quotes/one-liners will hole-fill only.

### [2026-08-05] root-triage | AUM Break-Even + Steel Ecosystem (wiki-create) + Steel Product dump

- `AUM Break-Even — When AUM Beats Services.md` → **appended** `## Appendix — 2026-08-05 (AUM Break-Even)` to `concepts/aum-bomt-intelligence-compounding-vehicle.md`. Break-even equation, hypothetical baseline (~4,600 Tier-2 decisions/mo @ $0.50), volume vs value paths, Year-1/2/3 honest math (one namespace won't beat services), Path B (Hybrid Premium) for Year-1 cash flow, `sales:` as first namespace. Answers the "min decision volume" open question from the Pure-Structure appendix. Numbers flagged hypothetical, not real pricing. acted-on/compiled, backlog open.
- `Steel by Exo Ecosystem.md` → **Wiki** `concepts/steel-by-exo-ecosystem.md` (new). Premium identity sub-brand: v0.1 chain (card → profile → global citizenship), product lines (Card/App/steel.id/Teams/wearables-deferred), brand tiers Steel/+/++, Steel Global PMA structure + Worlds/steel.id earn tiers, growth flywheel, open decisions. actted-on/compiled + backlog. **Index: 12 pages (11 concepts + 1 entity).**
- `Dump - Steel Product Concepts.md` → hole-fill only (thin — NFC/connected jewelry, biometrics box). Below page threshold; pairs with Steel ecosystem concept. acted-on/compiled, backlog: jewelry-tech research.
- No SSOT promote (Steel structure is aspirational direction, not a locked decision; AUM break-even pricing hypothetical pending Path-B confirmation). Queue still large (~89 loose root notes) — draining cap 3 ongoing.

- `Exo Launch - Air Build.md` → **Wiki** `concepts/exo-launch-creative-ops.md`
  - Air.inc → Launch capability map (DAM/proofing/multiply/portals → diffs+why)
  - ComfyUI ladder: Cloud API (P1) → RunPod (P2) → MCP (P3) → **no fork**
  - Generation behind API wrapper; Tauri OS-wide already on desktop-shell concept (cross-link only)
- Dump frontmatter: acted-on true, compiled 2026-08-05, backlog checklist (Phase 1 path, hero workflow JSON, agency must-have integration)
- Desktop-shell concept blurb points at new Launch page
- Index: **11 pages (10 concepts + 1 entity)**
- No Reservoir task yet — optional when Jay greenlights Phase 1 Comfy Cloud wiring
- No SSOT promote (ladder is direction-grade; Phase 1 lock still open on dump backlog)

### [2026-08-05] task + Air UVP gap fill | Launch Phase 1
- Reservoir: `state/tasks/exo-launch-comfy-cloud-phase1.md` (atomized Comfy Cloud dogfood path + agency integration stack)
- Wiki concept `exo-launch-creative-ops.md`: UVP gap table from Air.inc public positioning (conversational search, creative intelligence, performance↔library, Canvas/brand-kit multiply, desktop sync, intake→delivery memory, visual-first status, Figma/Adobe/Slack/Canva, time-to-value, guest vs seat)
- Dump `Exo Launch - Air Build.md`: `promoted-to` task path; backlog updated
- Stance: copy Air *file UX / ops patterns*; win on diffs/why + multi-dept OS — not “be Air”

## [2026-08-06] root-triage | AUM reconstruction + Steel giveback + Speaks offer (hole-fill, cap 3)
- `AUM + BOMT — Long-Term Model Reconstruction.md` → **hole-fill only**. Already fully synthesized into `concepts/aum-bomt-intelligence-compounding-vehicle.md` (listed as source; §6 sustainability, §7 tensions, §9 7.5/10 assessment, §11 source table all incorporated). No duplicate page. acted-on + compiled.
- `Steel Giveback or Luxury Positioned Nightmare_.md` → **hole-fill** (acted-on false → true). Partial-giveback (10-15%) / no-giveback-on-Steel++ decisions already canonical in `agent-workspace/Exo Enterprise/company-ssot/sub-brands/steel-ecommerce-strategy.md`. No new page.
- `Speaks Offer.md` → **hole-fill** (thin — Steelspeaks $500 low-price offer → Skool platform → Flow OS trial → concierge funnel brainstorm). Below page threshold; pairs with OFFER-BIBLE/offer stack. acted-on + compiled, backlog: model Steelspeaks offer funnel + Skool affiliate profit-center check.
- No new wiki pages, no index change (0 additions). No SSOT promote (no new locked decisions — all already canon or directional).
- Queue still large (~91 loose root notes) — draining cap 3 ongoing; most are evergreen quotes/one-liners that will hole-fill only.


### [2026-08-06] root-triage | Hybrid HoldCo wiki + 3 dumps (cap 3)
- `Grok AI Convo.md` → **Wiki** `concepts/exo-hybrid-holdco-strategy.md` (new). Berkeley/roll-up/hybrid lens on EXO-HOLDCO-MAP: 3 structural archetypes (roll-up / Berkshire / CSI), how hybrid maps to Exo flagship+arms (includes the identical Part 2 AUM/tech-stack already on aum-bomt concept), 5 strategic paths, recommended lean (1+2 = focused core + steel.id), activation triggers, Exo Playbooks, legal/structure hygiene. acted-on + compiled.
- `Exo Business Model Add On - Grok.md` → **hole-fill** (same Part 2 content as Grok AI Convo — AUM reframe, pricing paths A/B/C, sovereign+Constructive+Timescale stack already synthesized on aum-bomt concept; its HoldCo-alignment section fed the new hybrid page). acted-on + compiled.
- `Milestones Per Diffs Threshold.md` → **hole-fill only** (small — gamified diffs-milestone thresholds 100k→20M for client-facing AUM visibility; pairs with aum-bomt concept / Flow OS UI). acted-on + compiled, backlog noted.
- **Index: 14 pages (13 concepts + 1 entity).** No SSOT promote (hybrid is a recommended strategic lens/direction, not a locked decision — Path 1+2 sequencing + Ventures trigger + dual-class are open questions for Jay).
- Queue still large (~87 loose root notes) — draining cap 3 ongoing; most are evergreen quotes/one-liners that will hole-fill only.


### [2026-08-06] root-triage | NFC anti-counterfeit + Exo-Ext wiki + Framework hole-fill (cap 3)
- `steel concepts.md` → **appended** `## Appendix — 2026-08-06 (NFC Anti-Counterfeit Defense)` to `concepts/steel-by-exo-ecosystem.md`. NFC vs QR (non-clonable UID), five anti-counterfeit mechanisms with loophole fixes (NTAG 424 DNA secure-element + dynamic auth vs replay; server-side validation w/ master keys; anti-ghost-shift UID whitelist + "First Tap" rule; digital passport ledger; tamper-evident VOID + in-material embedding), industry analogs, Steel relevance. Directly supports the Steel Card's AES-128 anti-counterfeit claims — flagged to wire into spec/marketing as proof-of-defense. Research frontmatter + acted-on/compiled.
- `Exo-Ext (Flow OS -or- Exo AI Browser Extension).md` → **Wiki** `concepts/exo-ext-browser-extension.md` (new). Flow OS browser sidebar capture/command layer; flagship **SOP Capture** (tabCapture/desktopCapture → multimodal AI → structured SOPs); **department-aware intelligence** per namespace; auto-diffs feed data-gravity moat (`namespace:academy`); middleware strategy validated (don't train models, own workflow data); pricing tiers (Self-Service $20–50/user/mo, Concierge $500–2,000+/SOP); BOMT front-door. Confidence medium; source's strategic-sharpening section blank + pricing under review. **Index: 13 pages (12 concepts + 1 entity).**
- `Framework— $$$.md` → **hole-fill only** (blank Alex-template content placeholder, no content). Below page threshold; marked acted-on + compiled, backlog false.
- No SSOT promote (NFC defense is technical direction supporting an already-canon Steel claim; Exo-Ext is product brainstorm not yet a locked build decision — both backlog-grade).
- Queue still large (~90 loose root notes) — draining cap 3 ongoing; most are evergreen quotes/one-liners that will hole-fill only.

### [2026-08-06] root-triage | AUM/hybrid-holdco source validation + email-stack hole-fill (cap 3)
- `AI INVESTORS CHAT.md` → **hole-fill only** (Berkshire vs traditional roll-up distinction + "Permanent Decentralized Roll-Up": autonomous operating hubs, playbook synergies, mini-float, frictionless cash recycling). Already listed as a **source** on `concepts/aum-bomt-intelligence-compounding-vehicle.md`, and Berkshire-vs-rollup + mini-float are in-depth on `concepts/exo-hybrid-holdco-strategy.md` — no new page needed. Added type research/categories/acted-on/compiled; backlog notes residual (one-page investment thesis for partners; first-acquisition target criteria).
- `Exo AUM + Investment AI Convo.md` → **hole-fill only** (third-party Google AI read of Exo model: 90-Day Program, Flow OS, agents, workflow automation; "infinite memory" = continuous vector-context + diff timeline / State of All Things; Nudge system = prediction engine; Permanent Decentralized Roll-Up + mini-float + frictionless cash recycling). Already listed as a source on the aum-bomt concept page; content absorbed. Added research frontmatter + acted-on/compiled; backlog (Flow OS vector-DB mapping; ideal niche vertical).
- `Grok Open Ship Opensource Email Convo.md` → **hole-fill only** (lead-gen email stack best-practices: cold layer Instantly/Smartlead/Saleshandy vs warm layer Mailchimp/Brevo with "reply GUIDE" lead-magnet handoff; skip self-hosted email OpenShip/Postal for cold outreach due to deliverability). Below page threshold; pairs with Ops Bottleneck Audit lead-magnet delivery plan. Added research/categories/acted-on/compiled; backlog (pick cold tool + warm-domain budget; Zapier reply→Mailchimp).
- No new wiki pages, no index change (0 additions). No SSOT promote (all directional / already-sourced).
- Queue still large (~86 loose root notes) — draining cap 3 ongoing; most are evergreen quotes/one-liners that will hole-fill only.

### [2026-08-06] root-triage | AUM competitive scape + pricing/harness hole-fill (cap 3)
- `Another AI CHAT.md` → **enriched** `concepts/aum-bomt-intelligence-compounding-vehicle.md` §5 with a *market-leader data-engine scape* table (Palantir Ontology/CDC+decision traces, CrowdStrike Global Threat Graph, Databricks Lakehouse, Roper VMS) — the single genuinely-new asset: **CrowdStrike's cross-client feedback loop as the model for aum's Tension-1 "anonymized global brain."** The regret-graph / decentralized-vertical-intelligence framing was already canonical in §5. acted-on + compiled, backlog notes residual. Source added to concept page.
- `Google AI Pricing Model v0.1.md` → **hole-fill only** (full 4-layer value-capture hybrid + 90-day BOT engine + backend monetization already synthesized as `concepts/post-ai-pricing-architecture.md`, which lists this file as source). Added missing frontmatter (acted-on + compiled). No new page, no duplicate.
- `Updated Harnesses Transcript.md` → **hole-fill only** (file-trees-over-frameworks abstraction argument already fully synthesized in aum-bomt §21 incl. self-improving-tree automation + moat framing, source quote present). acted-on + compiled.
- No new wiki pages, no index change (0 additions). No SSOT promote (nothing new locked; all directional). 
- Queue still large (~89 loose root notes) — draining cap 3 ongoing; most are evergreen quotes/one-liners that will hole-fill only.

### [2026-08-06] root-triage | Flow OS UI audit wiki + 2 AUM hole-fills (cap 3)
- `FLOW OS ANALYSIS.md` → **Wiki** `concepts/flow-os-ui-audit.md` (new). Full route-by-route audit of the running frontend vs the Diffs Engine + BOM-T: /memory = crown jewel (perfect concept, all fake data — priority real-data win), /admin-internal = the standard (real Supabase, the REACT phase, don't break), /launch + /subscribe = outright model-misaligned (hide/rebuild), /academy built for wrong (consumer EdTech) audience, /flowstate undefined, /settings billing contradicts BOM-T. Build-order signals already canonical in Reservoir `state/tasks/flow-os-build-order.md` (P1 /memory data, P2 /academy+/settings, P3 /launch+/flowstate, P4 /subscribe) — no duplicate task. Research frontmatter + acted-on/compiled + backlog checklist on the note.
- `AUM — Reframe - 3.md` → **hole-fill only** (already a listed source on `aum-bomt` concept — Intel Inside / Anonymized Global Brain / JV transfer structures + BOMT evolution all synthesized, §14 Custody Framework). Set acted-on true + compiled; resolved the note's embedded HIPAA/data-custody side-quest: the Data Custody Premium lives at `agent-workspace/Exo Enterprise/strategy-notes/strategic-notes-holdco-ev-nfc.md` point 6, already absorbed into `AUM + BOMT Model Commitment.md` §5 (diffs table = compliance audit trail by design).
- `AUM Part 2 — Flow OS + Exo.md` → **hole-fill only** (Capital-as-Code / data-for-software / data-equity-as-asset-class fund lens + three transfer structures already on `aum-bomt` concept, which lists the sibling notes as sources). Prepend full frontmatter (had none) + acted-on/compiled; backlog flags venture-studio/PE-angle as candidate concept enrichment if Jay wants it formalized.
- **Index: 15 pages (14 concepts + 1 entity).** No SSOT promote (audit is build-grade direction already in Reservoir task; AUM refinements are lens-grade).
- Queue still large (~106 loose root notes) — draining cap 3 ongoing; most are evergreen quotes/one-liners that will hole-fill only.
## [2026-08-07] root-triage | ExoCare pair + Giveaway attraction offer (hole-fill, cap 3)
- `Exo Care Insurance Thoughts.md` → **hole-fill**. Full ExoCare offer synthesis: SLA as Warranty/Maintenance (NOT regulated insurance — legal trap avoided), two OTO windows (Care Standard/Care+ $4.8k–$12k/yr), SLA response tiers by severity, Limitation-of-Liability clause draft, per-incident pricing matrix ($1,500 no-care emergency vs $500 Care+), 5/15-workflow caps to prevent unprofitable scaling. **Already confirmed as TIER 3 (Post-Engagement) in OFFER-BIBLE.md** — verified no duplicate. Hole-filled frontmatter (acted-on + compiled + backlog: draft conditional-close script, define 'Major Rebuild' boundary, sync SLA tiers to offer SSOT).
- `Exo Care — Insurance Mini OTO.md` → **hole-fill** (thin supplement: AppleCare-style one-time upfront payment idea). Same offer as above — absorbed; acted-on + compiled, backlog kept.
- `Giveaway Attraction Offer.md` → **hole-fill** (thin: give away free department as attraction offer). Pairs with `Exo Dept Lead Magnet Quiz Funnel.md` / lead-magnet funnel; below page threshold. acted-on + compiled + backlog.
- No new wiki pages, no index change (0 additions). No SSOT promote (ExoCare already canonical in offer SSOT; all directional).
- Queue remaining large (~80 loose root notes / mostly evergreen one-liners) — draining cap 3 ongoing.
## [2026-08-07] root-triage | Buzz agent-native honest take (wiki enrich) + Flow OS features + Steel Polymath teleporter (hole-fill, cap 3)
- `Buzz UI functionality into Flow OS — agent-native honest take.md` → **appended** `## Appendix — 2026-08-07 (Agent-native honest take)` to `concepts/flow-os-team-surface.md`. Honest self-score (live `8355e0e`): architecture ~8/10 agent-native, **agent-in-product ~3/10**, human SaaS ~5–6/10. Locked build-order disciplines: postMessage is a UI boundary not the ledger (optimize Phase C/D); Buzz log ≠ Diffs Engine → bridge 1–2 event types only, not until chat works in embed (`team_bridge` not first); every *decision-grade* change (not cursors/keystrokes) → prevents slop ledger; Tauri `invoke` JSON chokepoint later. **Agent-native success test** (observe→act→vocab diff+why→arc→replayable trail, no Jay pasting into Telegram). Priority: Part-C daily-diff workflow > worker v0.2 (real LLM) > Team bridge v0 > agent identity. Frontmatter acted-on/compiled.
- `Exo Flow Os Extra Features.md` → **hole-fill** (thin feature brainstorm). Exo AI proactive goals-backward-walking (inputs/outputs to target), live company monitoring with realtime nudges ("close 2 more leads = +33%"), employee shoutouts/direct voice motivation. **Open design flag: gate to AURA namespace/upsell, or gatekeep only the motivational pushes.** Below page threshold; prepended full frontmatter (type idea) + acted-on/compiled + backlog.
- `Steel Polymath Teleport-er.md` → **hole-fill** (thin). Steel Global content "teleport" feature — cross-World connective piece (e.g. Culture → Fashion via floating steel.global logo + tooltip hook) connecting multidisciplinary interests for users. Below page threshold; pairs with `steel-by-exo-ecosystem` concept. Frontmatter topic filled + acted-on/compiled + backlog.
- No new wiki pages, **no index change** (appended to existing concept, 0 new pages). No SSOT promote (all directional build/feature grade, nothing newly locked).
- Queue still large (~83 loose root notes) — draining cap 3 ongoing; most evergreen quotes/one-liners will hole-fill only.
## [2026-08-07] root-triage | Reflex Arc data infra wiki-create + Exo-Ext dev path + authority platforms (cap 3)
- `AI.md` → **Wiki** `concepts/reflex-arc-data-infrastructure.md` (new). DB-layer options for the diffs engine: **Constructive** (agentic-db + pgpm, AST-based, RLS-in-engine so an LLM physically can't read unauthorized rows) + **TimescaleDB** hypertables (diffs+why as time-series, ~90% columnar compression, continuous aggregates for mem-drift) + **Supabase-or-sovereign-VPS** hosting; pgpm versioned schema migrations; BOM/T payoff (sovereign Docker stack = transferable unit → Manage/Transfer becomes high-margin license handover, Option B "absolute winner"); agent schema-drift guardrails (write-not-execute migrations, isolated branch, human review, no-ALTER/DROP role). **Not a locked build decision** — sits under [[emit_diff Chokepoint — Scale Without Slop]]; Supabase+pg_partman is the cheap pre-revenue start, Constructive+Timescale sovereign is the transfer-built path. Added research frontmatter + acted-on/compiled + backlog (A→B decision, agentic-db vs own diffs schema, drift guardrails).
- `AI Generated - Exo.md` → **wiki-update + hole-fill**. Contains genuinely-new build path appended to `concepts/exo-ext-browser-extension.md`: **fork Alibaba Page-Agent.js** (MIT, in-page DOM GUI agent, client-side) → add emit_diff() capture (DOM change = Tier 1, agent action = Tier 2) + mid/post "why" annotations (Tier 3) → brand it → prototype the capture→diff→annotation loop in ~2–4 weeks. Clean split from Reflex Arc SENSE layer. Source added to concept. acted-on true + compiled, backlog (fork decision if Phase 1, migrate Desktop source files into workspace).
- `AI Authority Building Platforms.md` → **hole-fill only** (thin — Maven.com + DeepLearning.AI as authority-building resource list for Exo/Steelspeaks/EXA content). Below page threshold; prepended light frontmatter (type idea) + acted-on/compiled, backlog false.
- **Index: 17 pages (16 concepts + 1 entity).** No SSOT promote (data-infra is direction-grade build thinking, not a locked decision; Exo-Ext dev path is backlog until Phase-1 greenlight).
- Queue still large (~80 loose root notes) — draining cap 3 ongoing; most evergreen quotes/one-liners will hole-fill only.
## [2026-08-08] root-triage | Confidential Computing wiki-create + Steel Dynamic Profiles + Ad (cap 3)
- `AI Conversation Regarding Build.md` → **Wiki** `concepts/confidential-computing-bomt.md` (new). Loose root (no frontmatter) but rich: sandboxing modes (Local Brain / Remote Brain / Hybrid "Local Senses, Remote Reasoning"), TEE Confidential Computing (AWS Nitro/SGX) as the "best of both worlds" — AI sees data, human sees math; converts the **BOM/T Transfer** phase from revenue loss into a high-margin software license via the Control/Data plane split + "Golden Handcuffs" (tethered EIF, phone-home license, weights streaming); Federated Learning + Differential Privacy for eyes-off training; OpenClaw security red-flag + **Moltworker = blueprint-not-product** (single-user, no multi-tenancy, fork the architecture). Prefixed full frontmatter (type research) + acted-on/compiled + backlog (TEE-ready modular split, local-remote hybrid allocation, Moltworker-vs-LangGraph eval). **Index: 18 pages (17 concepts + 1 entity).**
- `Dynamic Digital Steel Card.md` → **appended** `## Appendix — 2026-08-08 (Dynamic Profiles)` to `concepts/steel-by-exo-ecosystem.md`. Dynamic Profiles UX idea (real-time card profile updates via Steel Global dashboard, rated 10/10). Hole-fill + acted-on/compiled.
- `Ad — Exo.md` → **hole-fill only** (Hormozi-adopted ad excerpt: "clone your best people… hand you the keys". Below wiki threshold — ad copy, not framework). acted-on/compiled, backlog: polish into full ad variant.
- No SSOT promote (Confidential Computing is architecture direction feeding BOM/T Transfer, not a locked build decision; Dynamic Profiles is a feature candidate; Ad is copy).
- Queue still large (~40 loose root notes) — draining cap 3 ongoing; most evergreen quotes/one-liners will hole-fill only.

- `5 Stages of Awareness.md` → **hole-fill.** Content raw-thought (Hormozi 5-stages awareness marketing framework, IG-reel ref). Below page threshold; added type idea + acted-on/compiled + open questions. Format path not started.
- `Business Replication.md` → **hole-fill.** Content raw-thought — thesis: work at a big company (ideally the one you're trying to start) and replicate best practices incl. culture; underrated method vs founding blind. Below page threshold; added type idea + acted-on/compiled + backlog (format path, sharpen POV).
- `Alex Hormozi on Training Anything.md` → **hole-fill.** Link-only capture (IG reel). Added type idea + frontmatter + open questions (expand thesis on review). backlisted.
- No new wiki pages, **no index change** (0 additions; all below page threshold). No SSOT promote (all directional content-idea grade).
- Queue still large (~40 loose root notes remaining) — draining cap 3 ongoing; most evergreen quotes/one-liners will hole-fill only.
