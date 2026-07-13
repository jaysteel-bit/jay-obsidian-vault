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
