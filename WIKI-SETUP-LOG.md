---
tags:
  - vault-guide
  - system-update
created: 2026-07-07
type: system
---

# WIKI Setup Log — 2026-07-07

> **What happened:** The vault's wiki system was restructured into a proper `WIKI/` folder, following Karpathy's LLM Wiki pattern adapted for this vault's property-based organization.

---

## The Problem

The vault had a half-built Karpathy wiki started by AI sessions (May 13, then June 24) and never polished. Four competing wiki artifacts sat loose among 88 personal notes at vault root:

- `index.md` (May 13 — hand-curated, actually decent)
- `vault-index.md` (June 24 — auto-generated, mostly empty YAML fields, broken)
- `log.md` (May 13 — 3 entries about "Phase 0")
- `vault-log.md` (June 24 — 1 entry)

Two different AI sessions, two different implementations, neither aware of the other. No SCHEMA.md existed. The `raw/` folder held Jay's Q&A drafts, not source materials. The Karpathy source notes that inspired the system were trapped in `agent-workspace/NOTEPAD/Exo-Vaults/` — disconnected from the vault they were meant to configure.

Meanwhile, the old vault rule said "no folders for organization — use properties instead." That rule prevented the wiki from having a home.

## What Changed

### 1. Created `WIKI/` folder at vault root

The wiki now has a proper home. The old "no folders" rule is relaxed — folders are fine where they serve a clear structural purpose. Personal notes still live in root and self-organize through properties. `WIKI/` holds what properties can't: compiled knowledge, immutable sources, and wiki configuration.

### 2. Consolidated wiki artifacts

| Before | After |
|--------|-------|
| `index.md` (root) | `WIKI/index.md` (canonical content catalog) |
| `log.md` (root) | `WIKI/log.md` (canonical action log, updated with restructure entry) |
| `vault-index.md` (root) | **Deleted** (broken auto-generated duplicate) |
| `vault-log.md` (root) | **Deleted** (1-entry duplicate) |

### 3. Created `WIKI/SCHEMA.md`

The key configuration file Karpathy's pattern requires but was missing. Defines:
- Wiki domain (Exo Enterprise, Flow OS, personal growth, content, strategy)
- Three-layer architecture (raw sources → compiled wiki → personal notes)
- Conventions (file naming, frontmatter, cross-references)
- Tag taxonomy
- Page thresholds (when to create vs update vs split)
- Operations (ingest, query, lint)
- Relationship to Vault-Directions.md, CLAUDE.md, Exo-Vaults, and the Hermes llm-wiki skill

### 4. Fixed `raw/` layer

- Moved `raw/Q-A AI CODING SYSTEM DRAFT.md` and `raw/Q-A BUILDING THE ACTUAL SOFTWARE.md` to vault root (they're Jay's thinking notes, not sources)
- Removed old root-level `raw/` directory
- Created `WIKI/raw/` as the proper immutable source layer (empty, ready for sources)

### 5. Moved Karpathy source notes

- `WIKI/references/` (originally `WIKI/README/`) holds the canonical copies of:
  - `llm-wiki.md` — Karpathy's full LLM Wiki pattern document
  - `llm-knowledge-base.md` — Karpathy's shorter KB notes
- These are the source materials that inspired this system. They live in the vault now, not trapped in agent-workspace.
- The agent-workspace copies (`NOTEPAD/Exo-Vaults/llm-wiki.md`, `llm-knowledge-base.md`) remain as duplicates. The Exo-Vaults README now points to the vault's `WIKI/references/` as canonical.

### 6. Updated vault guides

- **`Vault-Directions.md`** — Section 5 "Removed: Folders for Organization" → "Folders Are Fine (Updated 2026-07-07)". Documents WIKI/ as a structural folder.
- **`agents/CLAUDE.md`** — Added WIKI/ to Folder Organization section with pointer to SCHEMA.md.

## The Resulting Structure

```
jay-obsidian-main/                     ← THE VAULT
├── WIKI/                              ← The compiled wiki (AI-maintained)
│   ├── SCHEMA.md                      ← Wiki conventions + config (NEW)
│   ├── index.md                       ← Content catalog (consolidated)
│   ├── log.md                         ← Action log (consolidated + updated)
│   ├── raw/                           ← Immutable sources (empty, ready)
│   └── references/                    ← Karpathy source notes (canonical)
│       ├── llm-wiki.md
│       └── llm-knowledge-base.md
├── [88 personal notes]                ← Jay's capture layer (unchanged)
├── Categories/                        ← Hub files with Bases (unchanged)
├── Templates/                         ← Note templates (unchanged)
├── References/                        ← External content (unchanged)
├── Daily/                             ← Timestamped notes (unchanged)
├── Attachments/                       ← Media (unchanged)
├── EXO Company HTML/                  ← Website pages (unchanged)
├── agents/                            ← AI guides (CLAUDE.md updated)
├── Vault-Directions.md                ← Human guide (updated — folders allowed)
└── .obsidian/                         ← App config (unchanged)
```

## How Two Systems Work Together

1. **Steph Ango property-based notes** (vault root) — Jay captures thoughts, brain dumps, evergreen notes. They self-organize through YAML frontmatter, Categories, and Bases. This is the human-facing layer.

2. **Karpathy LLM Wiki** (`WIKI/`) — The AI compiles raw sources into interlinked knowledge pages. It maintains index.md, log.md, entity/concept pages. This is the AI-facing layer.

They don't compete. The vault root is capture. `WIKI/` is compile. The AI reads root notes as context, reads `WIKI/raw/` as sources, and writes compiled knowledge into `WIKI/`.

## What's Next

- **First ingest:** Drop source materials into `WIKI/raw/` (articles, transcripts, research). The AI will compile them into entity/concept pages.
- **Create entity/concept pages:** The `WIKI/entities/` and `WIKI/concepts/` folders don't exist yet. They get created when the first wiki pages are compiled.
- **Cross-link:** Wiki pages should link to relevant root-level personal notes via `[[wikilinks]]`. This connects the compile layer to the capture layer.
- **Lint:** Periodic health checks once the wiki has 10+ pages.
- Use tagging system already implemented in vault
