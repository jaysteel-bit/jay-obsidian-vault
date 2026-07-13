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
