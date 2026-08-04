# Wiki Log
*Append-only. Format: `## [YYYY-MM-DD] action | description`*
*AI maintains this. Never delete entries — only append.*

---

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
