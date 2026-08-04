# Wiki Schema

> **The configuration file for this wiki.** Tells AI agents how the wiki is structured, what conventions to follow, and what workflows to run when ingesting sources, answering questions, or maintaining the wiki. Co-evolve this over time.
>
> Based on [Andrej Karpathy's LLM Wiki pattern](references/llm-wiki.md). Adapted for this vault's property-based organization system.

---

## Domain

Jay Steel's personal + business knowledge base. Covers:
- **Exo Enterprise** — AI consulting + software holdco (Exo, Steel, SteelSpeaks)
- **Flow OS** — Exo's product (sovereign AI department platform)
- **Personal growth** — mindset, philosophy, Solomon Talks
- **Content creation** — ideas evolving across formats
- **Business strategy** — ICP, offers, delivery, pricing

## Architecture — How This Wiki Works

This vault merges two systems:

1. **Steph Ango's property-based note system** — notes live in root, self-organize through YAML frontmatter and Categories/Bases. This is the human-facing capture layer.
2. **Karpathy's LLM Wiki pattern** — the AI compiles raw sources into interlinked knowledge pages inside `WIKI/`. This is the AI-facing compile layer.

**The vault root is the capture layer. `WIKI/` is the compile layer. They work together.**

### Three Layers (Karpathy adapted)

| Layer              | Where                                                        | What                                                                       | Who writes it                            |
| ------------------ | ------------------------------------------------------------ | -------------------------------------------------------------------------- | ---------------------------------------- |
| **Raw sources**    | `WIKI/raw/`                                                  | Immutable source documents — articles, papers, transcripts, clippings      | Human drops sources; AI never modifies   |
| **Compiled wiki**  | `WIKI/` (index.md, concept pages, entity pages, comparisons) | AI-generated synthesis, cross-references, summaries                        | **AI writes and maintains; human reads** |
| **Personal notes** | Vault root (88 .md files)                                    | Jay's own thinking — brain dumps, evergreen notes, content ideas, strategy | **Human writes; AI analyzes and links**  |

### Folder Structure

```
jay-obsidian-main/                     ← THE VAULT (Obsidian)
├── WIKI/                              ← The compiled wiki (AI-maintained)
│   ├── SCHEMA.md                      ← This file — wiki conventions + config
│   ├── index.md                       ← Content catalog (every wiki page listed)
│   ├── log.md                         ← Action log (append-only, chronological)
│   ├── raw/                           ← Immutable source documents
│   ├── references/                    ← Pattern source notes (Karpathy's originals)
│   ├── entities/                      ← (future) Entity pages: people, orgs, products
│   ├── concepts/                      ← (future) Concept/topic pages
│   └── comparisons/                   ← (future) Side-by-side analyses
├── [personal notes]                   ← Jay's capture layer (property-organized)
├── Categories/                        ← Hub files with Bases (queryable views)
├── Templates/                         ← Note templates + Bases
├── References/                        ← External content (books, people, articles)
├── Daily/                             ← Timestamped daily notes
├── Attachments/                       ← Images, PDFs, media
├── EXO Company HTML/                  ← Website page drafts
├── agents/                            ← AI agent guides (CLAUDE.md, AGENTS.md)
├── Vault-Directions.md                ← Human-facing vault philosophy + usage
└── .obsidian/                         ← Obsidian app config
```

## Conventions

### Wiki pages (inside WIKI/)
- File names: lowercase, hyphens, no spaces (e.g., `exo-delivery-architecture.md`)
- Every wiki page starts with YAML frontmatter (see below)
- Use `[[wikilinks]]` to link between pages and to root-level personal notes
- Minimum 2 outbound links per page
- When updating a page, always bump the `updated` date
- Every new page must be added to `index.md`
- Every action must be appended to `log.md`

### Personal notes (vault root)
- Follow existing property-based system (see `Vault-Directions.md`)
- Use `categories` property for organization
- Tags describe (`#brain-dump`, `#0🌲`), categories organize (`[[Content]]`, `[[Dumps]]`)
- AI may add `vault-context` tags and cross-references to WIKI/ pages, but should not restructure root notes without asking

### Frontmatter for wiki pages

```yaml
---
title: Page Title
created: YYYY-MM-DD
updated: YYYY-MM-DD
type: entity | concept | comparison | query | summary
tags: [from taxonomy below]
sources: [raw/articles/source-name.md]
# Optional quality signals:
confidence: high | medium | low
contested: true
contradictions: [other-page-slug]
---
```

### Frontmatter for raw sources

```yaml
---
source_url: https://example.com/article
ingested: YYYY-MM-DD
sha256: <hex digest of body>
---
```

## Tag Taxonomy

Wiki pages use tags from this list. Add new tags here BEFORE using them.

**Business:** exo, steel, steelspeaks, flow-os, delivery, pricing, icp, offer
**People/Orgs:** person, company, partner, competitor
**Product:** architecture, feature, ui, api, database, infrastructure
**Strategy:** marketing, sales, content, positioning, roadmap
**Meta:** comparison, timeline, controversy, prediction, decision

## Page Thresholds

- **Create a wiki page** when an entity/concept appears in 2+ sources OR is central to one source
- **Add to existing page** when a source mentions something already covered
- **DON'T create a page** for passing mentions or minor details
- **Split a page** when it exceeds ~200 lines
- **Archive a page** when fully superseded — move to `_archive/`, remove from index

## Operations

### 1. Ingest (when Jay drops an **external** source)

1. Save source to `WIKI/raw/` with descriptive name + raw frontmatter
2. Read the source, discuss key takeaways with Jay
3. Check `index.md` for existing pages on mentioned entities/concepts
4. Write or update wiki pages (entities/, concepts/, comparisons/)
5. Cross-reference: every new/updated page links to 2+ other pages
6. Update `index.md` — add new pages under correct section
7. Append to `log.md`: `## [YYYY-MM-DD] ingest | Source Title`
8. Report every file created or updated

**`WIKI/raw/` is immutable external sources only** (transcripts, articles, PDFs).  
**Do NOT put Jay's brain dumps in raw/** — those stay at vault root and use §1b.

### 1b. Root capture triage (dumps **and** loose root notes → compile / holes / Reservoir)

**Inbox = vault root `.md` files, NOT `WIKI/raw/`.**  
Includes formal dumps **and** loose root notes (untitled chats, Grok convos, half-named thinking) that never got `type: dump`.

**Queue selector** — root-level `.md` only (never Categories/, Templates/, Daily/, Attachments/, WIKI/, agents/, .obsidian/):

Include if **any**:
- `type: dump` OR tag `brain-dump` OR `categories` contains `Dumps`
- OR loose root note: not agent-maintained, and (`acted-on` false/missing OR `compiled` empty/missing OR mtime newer than last `WIKI/log.md` triage/compile stamp)

**Always exclude from queue:**
- `WIKI/**`, `Templates/**`, `Categories/**`, `Daily/**`, `Attachments/**`, `agents/**`, `.obsidian/**`
- Files that are pure evergreen already `acted-on: true` with fresh `compiled` and no newer mtime
- Binary/media

For each note in the batch (**cap 3 per heartbeat** unless Jay requested a full pass):
1. Read note + `index.md` (+ relevant existing concept pages)
2. Classify: `ignore` | `hole-fill` | `wiki-update` | `wiki-create` | `task-atom` | `promote-candidate` (combine when needed)
3. **Hole-fill on the root note** (additive only — never delete Jay's body):
   - set `acted-on: true` when triage finished
   - set `compiled: YYYY-MM-DD` when wiki was touched
   - fill `backlog` with a markdown checklist of residual opens, OR `backlog: false`
   - if missing type/categories on a loose note: infer lightly (`type: dump` or `idea` / `research`) — don't force-fit
   - add `## Open questions` / `## Decisions implied` if missing and content warrants
4. **Wiki:** create/update concept pages per Page Thresholds; ≥2 wikilinks; bump `index.md` + append `log.md`
5. **Reservoir (agent-workspace):** only if actionable — `state/tasks/<slug>.md` and/or `state/decisions-open.md`. Never paste full note bodies into the workspace.
6. **Promote** when KNOWLEDGE-SYSTEM §2 criteria hit: write Reservoir SSOT/state first, then set `promoted-to: "agent-workspace/<path>"` on the note
7. Log: `## [YYYY-MM-DD] root-triage | <Note Title> → <outcomes>`

Owner: Hermes heartbeat (`HEARTBEAT.md` Owned checks), model-pinned for maintenance. Manual: `/vault triage`.

### 2. Query (when Jay asks a question)

1. Read `index.md` to find relevant pages
2. For 100+ pages, also `search_files` across all .md files
3. Read relevant pages
4. Synthesize answer with citations: "Based on [[page-a]] and [[page-b]]..."
5. File valuable answers back as new pages (comparisons/, queries/)
6. Update `log.md` with the query

### 3. Lint (periodic health check)

1. **Orphan pages** — no inbound `[[wikilinks]]`
2. **Broken wikilinks** — `[[links]]` pointing to non-existent pages
3. **Index completeness** — every wiki page in `index.md`
4. **Frontmatter validation** — all required fields present
5. **Stale content** — pages not updated in 90+ days
6. **Contradictions** — pages on same topic with conflicting claims
7. **Source drift** — recompute sha256 for raw/ files, flag mismatches
8. **Page size** — flag pages over 200 lines
9. **Tag audit** — flag tags not in taxonomy
10. **Log rotation** — if log.md exceeds 500 entries, rotate to `log-YYYY.md`

Append to log: `## [YYYY-MM-DD] lint | N issues found`

## Resuming an Existing Wiki (CRITICAL — every session)

1. Read `SCHEMA.md` (this file)
2. Read `index.md`
3. Scan recent `log.md` (last 20-30 entries)

Only after orientation should you ingest, query, or lint.

## Relationship to Other Systems

- **`Vault-Directions.md`** — human-facing guide to the vault's note-taking philosophy. This SCHEMA is the AI-facing companion.
- **`agents/CLAUDE.md`** — AI interaction guide for the vault. Points here for wiki operations.
- **agent-workspace `Exo Enterprise/Exo-Vaults/`** — Exo's client delivery system. Each client vault uses the same Karpathy pattern (raw/ + wiki/ + SOPs-configs/) but scoped to a single client engagement. This vault is Jay's personal wiki; client vaults are separate instances.
- **Hermes `llm-wiki` skill** — the skill that implements this pattern programmatically. If using Hermes, set `WIKI_PATH` to this `WIKI/` directory.

## Folders Are Fine

The old rule was "no folders for organization — use properties instead." That rule is relaxed. Folders are fine where they serve a clear structural purpose:
- `WIKI/` — the compiled knowledge layer
- `WIKI/raw/` — immutable sources
- `WIKI/references/` — pattern documentation
- `Categories/`, `Templates/`, `References/`, `Daily/`, `Attachments/` — existing structural folders

Personal notes still live in root and self-organize through properties. Folders don't replace properties — they hold things properties can't (compiled knowledge, immutable sources, app config).
