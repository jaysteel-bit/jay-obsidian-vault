# Wiki Log
*Append-only. Format: `## [YYYY-MM-DD] action | description`*
*AI maintains this. Never delete entries — only append.*

---

## [2026-08-10] root-triage | T-Bills + Steve Jobs Poke Life + Leetcode.com (cap 3)
- `T-Bills.md` → **hole-fill (stamp only).** Raw content idea (YouTube short reference only, no formed thesis). Below wiki threshold. Stamped acted-on/compiled/backlog:false.
- `Steve Jobs — Poke Life.md` → **hole-fill (stamp only).** clip-captured short-form quote (Steve Jobs "poke life" excerpt) — polished quote already in-body, no synthesis needed. Stamped acted-on/compiled/backlog:false.
- `Leetcode.com.md` → **hole-fill (stamp).** Hiring idea (Leetcode-style SWE competence baseline via Roy Lee referral) — actionable but parked (no active hiring loop). Inferred minimal frontmatter (type:idea, vault-context:business). Stamped acted-on/compiled/backlog:false. No reservoir task (no active hiring workflow).
- No new wiki page, no SSOT promote (raw-content captures, not locked decisions).
- Queue remaining: ~3 loose root notes (Copy Enhancing [empty], Guinness world record 2002, Its-not-about-the-money) + test/system junk excluded. Draining cap 3 ongoing.

## [2026-08-10] root-triage | Steel Tag + Steel App UX + Steel Product Model (cap 3)
- `Steel Tagged.md` → **wiki-append.** Steel Tag as content-attribution-aggregator (tag profiles in universe; recycle existing social-media infra via T&C; two/three-prong: attribution + constant content pool + unified all-platform feed). Appended to `WIKI/concepts/steel-by-exo-ecosystem.md` Appendix 2026-08-10 (Steel Tag block). Stamped acted-on/compiled.
- `Steel App UX - Add On.md` → **wiki-append.** Steel App UX add-ons (AI connected-messaging with presets; "sent with Love/by Steel" branded send footer = viral coefficient with download link). Appended as Steel App connected-messaging + viral-send Appendix 2026-08-10 to same ecosystem page. Stamped acted-on/compiled.
- `Steel Product Model Page.md` → **hole-fill (stamp only).** Thin 2-line draft (products-come-short-form-content idea); below wiki threshold. Stamped acted-on/compiled, backlog false.
- No new page (all fold into existing steel ecosystem concept); no SSOT promote (drafts, not locked).
- Queue remaining: ~8 loose root notes (Steel Card/Tagged done; still: Copy Enhancing, Guinness world record, Its-not-about-the-money, Leetcode, Steve Jobs Poke, Success Has Enemies, T-Bills, Steel App UX (done), plus test/system junk excluded).

## [2026-08-10] root-triage | Solomon 1-28 + Solomon Talk 01-21 + Steel App Prompt (cap 3)
- `Solomon 1-28 + 2-1.md` → **hole-fill (stamp).** Personal weekly journaling (vault-context: personal) — meeting-reunion reflection + Solomon's staying-conviction nudge. Below wiki threshold (private journaling, not synthesis). Stamped acted-on/compiled, backlog false. Kept private.
- `Solomon Talk - January 21, 2026.md` → **hole-fill (stamp).** First AI-generated Solomon session (focus on clarity, not quantity; know thyself). Same classification — personal journaling, kept private. Stamped acted-on/compiled.
- `Steel App Prompt.md` → **wiki-update + task-atom.** Detailed Steel App UI/NFC spec (real NFC not mock; Recent Connections slide gesture → 3 reveal buttons; Trust gold-coin nav icon; red-shield disabled state; mobile gold-shadow bug). Appended as Steel App Appendix 2026-08-10 (UI/NFC + AI Mode "viral coefficient" full-screen card) to `WIKI/concepts/steel-by-exo-ecosystem.md`; added frontmatter (type:idea, project:Steel, acted-on/compiled). Reservoir task created `state/tasks/steel-app-nfc-spec.md`.
- No SSOT promote (spec, not locked decisions).
- Queue remaining: ~13 loose root notes (mostly Steel/Solomon/product-named files + templates — draining cap 3 ongoing).

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

## [2026-08-08] root-triage | Desktop shell + quiz funnel + AUM source-confirm (hole-fill, cap 3)
- `flow-os-desktop-shell-ui-direction-2026-07-27.md` → **source-confirm + stamp.** Already listed as a source on `concepts/flow-os-desktop-shell.md` (compiled Jul 31). Full UI direction: 3-home routing, Codex/Hermes/FlowOS chrome teardown, the **"Company Pulse is product identity, not marketing fluff"** correction (Layer B rotating hero = the emotional pulse; global status bar is additive, never a replacement). Shell stays **draft-for-lock awaiting Jay confirm** on 4 open lock questions (HQ Pulse Theater stays? global status additive? Phase 0 chrome-only first? KPI/CTA keep-kill). Added acted-on/compiled + backlog (Jay confirm → then reconcile DESKTOP-SHELL-UX.md).
- `Exo Dept Lead Magnet Quiz Funnel.md` → **hole-fill.** Department spotlight/grow quiz idea (click answers, dept cards animate and fade in background, trains prospect toward full suite). **Already planned in OFFER-BIBLE** as the "Ops Bottleneck Audit (Self-Serve)" self-assessment quiz + `00-master.md` "Exo Org. Blueprint (quiz/form funnel) — coming soon." Below wiki threshold — directional content. Prepended full frontmatter (type idea) + acted-on/compiled; backlog (delivery mechanism not chosen — Jay flagged to pick; map dept questions to the OFFER-BIBLE quiz).
- `Asset Management (AUM) Exo Model Brainstorming.md` → **source-confirm + stamp.** Already a listed source on `concepts/aum-bomt-intelligence-compounding-vehicle.md` §11 (Intelligence Onboarding, three pricing paths, Reflex Arc schema, Delta Ledger / Regret Graph UI, multi-agent SYSTEM_STATE.md supervisor). Rich but fully synthesized — no new page. Prefixed full frontmatter (had none) + acted-on/compiled; backlog (overlay Reflex Arc Delta Ledger onto existing dashboard drafts in Figma; draft full-stack FastAPI+Next.js dev role — build simulated prototype first).
- No new wiki pages, **no index change** (0 additions; all already-sourced direction). No SSOT promote (Quiz Funnel already canonical in OFFER-BIBLE; AUM + shell direction already canonical in concepts).
- Queue still large (~37 loose root notes remaining) — draining cap 3 ongoing; most evergreen quotes/one-liners will hole-fill only.

## [2026-08-08] root-triage | Flow OS moat critique (hole-fill) + VSL X-Scale script + Email lead-capture (cap 3)
- Github + Flow-OS Assessed.md -> hole-filled as source into WIKI/concepts/emit-diff-chokepoint-scale.md (add Moat-challenged section + open question); stamped promoted-to.
- VSL-New-Script.md -> stamped (no frontmatter, prepended); backlog -> Reservoir Exo Enterprise/DOCUMENTATION/VSL.
- Email Campaigns — Lead Capture Gem.md -> stamped acted-on/compiled; backlog = build lead magnet once format locked.
- No new pages; index unchanged. Queue: ~47 loose root notes remaining (mostly quote/evergreen hole-fill only).

## [2026-08-08] root-triage | Rendon lead + Obsidian vaults + Hormozi sales tips (cap 3)
- `Potential Lead - Source Facebook.md` → **task-atom / promote.** Live B2B lead (Rendon Contracting LTD, referral Josh, younger-brother owner). Added full frontmatter (type lead) + acted-on/compiled + promoted-to `agent-workspace/state/tasks/lead-rendon-contracting.md`. No outreach without Jay.
- `Obsidian Vaults Per Each Client.md` → **hole-fill.** Strategy dump on client vaults / Flow OS MCP / RAG. Already a source on `concepts/exo-vault-meta-leverage-system.md`. Set acted-on/compiled; added agent review answering the embedded RAG question (LightRAG/LlamaIndex sufficient for mid-market; no vector farm) + open question (build client-zero company vault as dogfood).
- `Hormozi - 17 Sales Tips.md` → **hole-fill.** Evergreen evergreen quote note; set acted-on/compiled + link to [[Alex Hormozi]] entity page. Below page threshold — kept as capture.
- No new wiki pages, **no index change** (0 additions). No SSOT promote (lead not ICP-confirmed). Queue still large (~34 loose root notes remaining, mostly quotes/evergreen).

## [2026-08-08] root-triage | Evergreen quote stamps x3 (cap 3)
- `Alex Hormozi Quote.md` → **hole-fill (stamp).** Evergreen content raw-thought (work-life-balance-as-love analogy), complete body already. Set acted-on/compiled/backlog:false. Below page threshold — kept as capture.
- `Mark Twain.md` → **hole-fill (stamp).** Evergreen quote + analysis (majority ≠ validation, via Mint), complete body. Set acted-on/compiled/backlog:false. Below threshold — kept as capture.
- `Life is poker, not chess.md` → **hole-fill (stamp).** Evergreen mindset (decisions under uncertainty), Claude analysis in place. Set acted-on/compiled/backlog:false. Below threshold — kept as capture.
- No new wiki pages, **no index change**. No SSOT promote. Queue ~41 loose root notes remaining (nearly all June-29 evergreen quotes/content tips).

## [2026-08-08] root-triage | Ideal Customer + Read-over stub (cap 3)
- `Ideal Customer.md` → **hole-fill.** Content raw-thought (Hormozi "quality > quantity" CAC quote, ref [[Lost Chapters]] / [[Alex Hormozi]]). Set acted-on/compiled/backlog:false. Below page threshold — kept as capture.
- `Read over immediately —.md` → **hole-fill / link-hub.** Stub listing AUM model brainstorming, AI, steel concepts as read-next pointers; added frontmatter + triage comment. No body to compile.
- Third slot: checked `Exo Company Folder Setup.md` / `5 Stages of Awareness.md` / `AEO Report of Exo Home Page.md` — all already triaged (acted-on/compiled set) earlier; excluded as false-positives from mtime heuristic.
- No new wiki pages, **no index change**. No SSOT promote. Queue ~44 loose root notes remaining (nearly all June-29 evergreen quotes/content tips).

## [2026-08-09] root-triage | Steel Prevents Fraud, Its not about the money, Steve Jobs — Poke Life (cap 3)

- `Steel Prevents Fraud.md` → **hole-fill (dump).** Genuine Steel product idea: optional one-time deposit-to-unlock gate, 85% reimbursed to payment method / 15% held on Steel card. Added ### Key Insights (filled), ### Decisions implied, ### Open questions (15% float rationale). Set acted-on:true. Below promote threshold (feature idea, not settled decision) — kept as capture.
- `Its not about the money, it’s who you have to become to make the money.md` → **hole-fill (stamp).** Empty content template, title-only evergreen. Set acted-on:true/compiled empty. Below threshold — kept as capture.
- `Steve Jobs — Poke Life.md` → **hole-fill (stamp).** Content note w/ embedded Jobs "poke life" quote video, hook identified, caption still needed. Bumped to content_stage: clip-captured, set acted-on:true.
- No wiki page create/update (all below Page Thresholds). No Reservoir change. Queue 39 → 36 remaining.

## [2026-08-09] root-triage | Steel referral virality + Citizen/Visitor positioning (cap 3)
- `Steel Share Feature Thoughts.md` → **appended** `## Appendix — 2026-08-09 (Referral Virality + Citizen/Visitor Distinction)` to `concepts/steel-by-exo-ecosystem.md`. Onboarding virality (3–5 click $5–10 referral credit, PayPal-style exponential, abuse risk parked), partner-access fee tiers ($99/105–110/500+), no-charge basic "Facebook-style" membership with the physical Card's **verified badge** as the differentiator. acted-on true + compiled.
- `Steel Global 03-07.md` → **appended** to same new appendix. "Visitor Pass vs Diplomatic Passport" positioning: Cross-World metadata bridges, Contribution Ledger cross-pollination badge, Free=links / Citizen=World-integration (counters Linktree dilution), **Dynamic Permissioning** (context/time-aware profile) + Live Feed of Activity as the Linktree disruptor, closed-universe echo-chamber sustainability risk. acted-on true + compiled.
- `Dump - Exo Charity & Social Impact.md` → **hole-fill (stamp).** Distinct Exo mission capture (charity = AI-literacy/education angle, not generic donations; "Be Extraordinary" tie-in; decide revenue-portion vs free-tier-donation mechanism). Below wiki threshold — kept as capture. Added acted-on true + compiled.
- Steel Tap-to-Features stamped (compiled 2026-08-09) — its NFC/Tap content already synthesized by the 2026-08-06 NFC appendix + Dynamic Profiles; no duplicate.
- **No new wiki pages, index unchanged (1 appendix on existing concept).** No SSOT promote (Steel growth mechanics + positioning are direction-grade feature/strategy thinking, not a locked decision — pricing/launch sequencing remain open).
- Queue still large (~33 loose root notes remaining, mostly June-29 evergreen quotes/content tips).

## [2026-08-09] root-triage | Lukas Mullen IG, Dan Koe Content, Exo bio draft (cap 3)
- `Lukas Mullen on Building A World on Instagram for STEEL.md` → **hole-fill (stamp).** Link-stub (IG reel) on Mullen's community/"world"-building play; mapped to STEEL's owned-audience + SteelSpeaks angle. added type:idea + acted-on/compiled. Backlog: watch reel, extract framework, decide STEEL fit.
- `Dan Koe Content.md` → **hole-fill (stamp).** Empty raw-thought template (title + reel link only). Repaired malformed frontmatter from patch. Backlog: transcribe reel, evolve per WORKFLOW, decide if generalizes into Exo content engine.
- `Exo bio draft.md` → **hole-fill (stamp).** Bio/offer hook ("we run the system, now we're teaching it") gated to private WhatsApp group lead capture. Cross-ref lead-magnet / quiz-funnel angle. Kept as copy iteration, not locked message.
- No new wiki pages (all below Page Thresholds), index unchanged. No SSOT promote. Queue ~30 remaining (mostly June-29 evergreen quotes/content tips).

## [2026-08-09] root-triage | Polymath article + 2 evergreen stamps (cap 3)
- `Exo—Polymath Article (Reasoning).md` → **hole-fill (research).** Substantive APU Edge excerpt on why modern orgs suppress polymaths (vertical silos, no cross-training, need-to-know info sharing; hiring specs demanding 10-20yr specialists; society-as-dilettante stigma). Direct relevance to Exo's generalist/"sovereign AI department" framing + Flow OS cross-department knowledge model. Prefixed full frontmatter (type research, topics polymath/positioning). Below wiki threshold (single external quote, not yet woven across 3 sources) — kept as capture. Backlog: sharpen into Exo positioning/recruiting POV.
- `Success Has Enemies.md` → **hole-fill (stamp).** Evergreen content raw-thought (fully formed caption: "Success has enemies. What are you gonna do.. Be unsuccessful?" + refined variant "Success comes with enemies but so does being unsuccessful, but you would be your worst one"). Set acted-on/compiled; content ready for format build on IG/X. Below threshold — kept as capture.
- `Enterprise Value.md` → **hole-fill (stamp).** Empty raw-thought template (YT short link only, no body). Set acted-on/compiled; backlog: watch clip, extract thesis. Below threshold — kept as capture.
- No new wiki pages, index unchanged. No SSOT promote (positioning/quote content, directional only).
- Queue still large (~30 loose root notes remaining, mostly June-29 evergreen quotes/content tips — draining cap 3 ongoing).

## [2026-08-09] root-triage | New SKILL for Growth + Content Tips + Book List (cap 3)
- `New SKILL.md for Growth.md` → **hole-fill (idea).** EXA-in-FlowOS employee skill for orgs running Steel frameworks; working name `/personal` vs `/steel` slash-command unresolved. Body is a placeholder awaiting Grok breakdown. Added type:idea + acted-on/compiled + open questions. Below wiki threshold — kept as capture.
- `Content Tips.md` → **hole-fill (idea).** Evergreen proofreading workflow (read aloud, sub-3rd-grade vocab, sentence-level removal test, short > long). Personal/content-engine. Added frontmatter + acted-on/compiled, backlog false. Below threshold.
- `Book List.md` → **hole-fill (reference).** Framing/persuasion bookshelf (Luntz, Hutton, Keren, Madrid). Personal copywriting reference. Added type:reference + acted-on/compiled; backlog: curate into offer-stack/content-engine framing reference. Below threshold.
- No new wiki pages, index unchanged. No SSOT promote (all below Page Thresholds; directional content/reference).
- Queue remaining: ~24 loose root notes (mostly June-29 evergreen quotes/content tips).

## [2026-08-09] root-triage | Steel anti-fraud page update + 2 stamps (cap 3)
- `Steel Prevents Fraud.md` → **wiki-update.** New anti-abuse design (deposit-to-unlock gate, 85% back / 15% held on Steel card, proof-of-personhood, ~90% free baseline preserved) appended to `WIKI/concepts/steel-by-exo-ecosystem.md` as Appendix 2026-08-09 (Anti-Fraud Deposit Gate); sources updated. Stamped acted-on/compiled.
- `Steel Share Feature Thoughts.md` → **hole-fill (stamp).** Referral virality + verified-badge stance already synthesized on steel-by-exo-ecosystem.md (Appendix 2026-08-09) — source-confirmed, stamp only, no new page.
- `Update Exo Vault (Lead Magnet -Hub Center).md` → **hole-fill (stamp + backlog).** Exo vault (vault.exoent.co) UI lift + populating lead magnets is actionable but gates on locked lead-magnet deliverable format — pointed backlog at existing `state/tasks/lead-magnet-concepts.md` (blocked); no duplicate task spawned.
- No new wiki pages (Steel page updated, index unchanged). No SSOT promote (ideation, not locked decisions).
- Queue remaining: ~27 loose root notes (mostly June-29 evergreen quotes/content tips — draining cap 3 ongoing).

## [2026-08-10] root-triage | Uncertainty + Iteration + Your probably right + beliefs (cap 3)
- `Uncertainty + Iteration.md` → **hole-fill (evergreen).** Strong entrepreneurial raw-thought on tolerating uncertainty ("Run. I'll tell you when to stop") — maps directly to Exo's positioning (decision throughput / sticking with the process) + personal mindset content. Stamped type evergreen/acted-on/backlog. Below wiki threshold (single capture, no synthesis) — kept as capture; backlog: build into content-engine long-form.
- `Your probably right.md` → **hole-fill (evergreen).** Solomon-paradox theme (most business owners could 10x by following their own advice; "you're probably right but not acting"). Complements Solomon 1-28 capture. Stamped acted-on/backlog. Below threshold — kept as capture; backlog: fold into decision/action content.
- `You're only as big as your beliefs.md` → **hole-fill (stamp).** Evergreen mindset with existing Claude analysis (pattern-recognition limiting possibility, beliefs-as-ceiling). Content-ready: stamped acted-on, backlog false. Below wiki threshold — kept as capture, ready for format build.
- No new wiki pages, index unchanged. No SSOT promote (mindset/evergreen directional content).
- Queue remaining: ~21 loose root notes (mostly June-29 evergreen quotes/content tips — draining cap 3 ongoing).

## [2026-08-10] root-triage | Evergreen-notes example + AP×Swatch content + Worth The Wait (cap 3)
- `Example - Evergreen notes turn ideas into objects that you can manipulate.md` → **hole-fill (reference).** Steph Ango's evergreen-notes method (title-as-distilled-idea, composable, ideas-as-objects) — the foundational philosophy the whole WIKI/Forge system runs on. Added type:reference + acted-on/compiled, backlog false. Below page threshold (external essay, single-source) — kept as capture/reference.
- `Audemars Piguet x Swatch.md` → **hole-fill (content).** Content idea with a two-sided take (business + culture) + contrarian angle (agree with collab, dispute the low-price detractors) + B-roll checklist. Actionable short-form material but mid-draft (some placeholder links). Added type:content + acted-on/compiled, backlog true (complete B-roll links + write). Below threshold — kept as capture.
- `Worth The Wait.md` → **hole-fill (content).** Raw-thought clip link only, no thesis extracted. Added type:content + acted-on/compiled, backlog true (watch clip, extract thesis). Below threshold — kept as capture.
- No new wiki pages, index unchanged. No SSOT promote (content/reference, directional).
- Queue remaining: ~16 loose root notes (mostly Steel/Solomon/product-named files + templates — draining cap 3 ongoing).

## [2026-08-11] root-triage | Steel Card + Copy Enhancing + Guinness record (cap 3)
- `Steel Card.md` → **source-confirm + stamp.** Frontmatter-only stub (no body); Steel Card (NFC anti-counterfeit, deposit-to-unlock anti-fraud gate, verified-badge, referral virality, Citizen/Visitor positioning) already fully synthesized on `WIKI/concepts/steel-by-exo-ecosystem.md` (Appendices 2026-08-06/09). Added type:idea + acted-on/compiled + promoted-to pointer. Backlog false.
- `Copy Enhancing.md` → **hole-fill (stamp).** Empty template placeholder (title only, 0 bytes body). No content to compile. Added type:idea + acted-on/compiled, backlog false. Kept as title-keyed evergreen slot.
- `Guinness world record 2002.md` → **hole-fill (stamp).** Raw content-resource idea (Guinness 2002 book as reference for record-setting/extremity content angles). Below wiki threshold. Added full frontmatter (type:content) + acted-on/compiled, backlog false.
- No new wiki pages, index unchanged. No SSOT promote (all source-confirm / below-threshold captures).
- Queue remaining: ~1 genuine loose root note (`HERMES AGENT.md` — large reference doc, untriaged) + system/test junk excluded (Test 2, Markdown Test, Vault-Directions, WIKI-SETUP-LOG).

## [2026-08-11] root-triage | HERMES AGENT.md (last genuine loose note)
- `HERMES AGENT.md` → **hole-fill (stamp).** Reference doc (Nous Research Hermes Agent overview/roadmap). No frontmatter existed; prepended full block (type:reference + acted-on/compiled, backlog false). Below wiki threshold (single external reference source) — kept as capture/reference, not wiki'd.
- Queue remaining: **0 genuine loose root notes.** All dumps (Onboarding/Steel Concepts/Mission-Vision/Charity) confirmed acted-on. Only system/test junk at root (Test 2, Markdown Test, Vault-Directions, WIKI-SETUP-LOG) excluded.

## [2026-08-12] root-triage | Its-not-about-the-money + Steel Pants/Belt (cap 2)
- `Its not about the money…md` → **hole-fill (stamp only).** `vault-context: personal` content-capture template (empty raw-thought pattern note, evergreen quote premise). Stamp-only per personal rule; kept private. Stamped `compiled: 2026-08-12`.
- `Steel Pants + Steel Belt.md` → **hole-fill (stamp only).** Business dump (dual/hidden belt loops + horizontal dagger belt-tip ideation), already triaged 08-04 in-body (no concept page — below 2-source threshold). `compiled:` was empty → backfilled `compiled: 2026-08-12`. Residual backlog intact (prototype sketch + belt dagger design brief).
- No new wiki page, no SSOT promote (personal template + ideation only).
- Queue remaining: 0 genuine loose root notes (remaining `comp=MISS` are system/test junk: Markdown Test, Test 2, Vault-Directions, WIKI-SETUP-LOG).
