---
title: emit_diff Chokepoint — Scale Without Slop
created: 2026-08-04
updated: 2026-08-04
type: concept
tags: [flow-os, architecture, database, infrastructure]
sources: ["emitt-diff talk.md"]
confidence: medium
---

# emit_diff Chokepoint — Scale Without Slop

> Crystallized from root dump `emitt-diff talk.md` (2026-08-04). Live runtime facts stay in [[agent-workspace]] `state/flow-os.md` — this page is the *scaling / vocabulary-growth* thinking.

## One-liner
`emit_diff()` stays the **only write door** into `diffs`. Scaling means **async + batch + local fast-fail** — not removing the chokepoint. Vocabulary grows via sandbox → cluster → promote, not free-form strings.

## Why a chokepoint is intentional
Central control (vocabulary law, RLS, uniform logging, Reflex Arc hot path) beats "every writer inserts freely." Risk is real: sync PowerShell + per-event HTTP + row-by-row inserts will jam under load. Fix the **implementation**, not the doctrine.

## Current path (prototype)
```
Agent / session
  → build/emit-diff.ps1 (workspace chokepoint)
    → validate vs diff-vocabulary.md (local)
    → Supabase emit_diff() RPC (DB validates again)
    → diffs row → realtime → Reflex Arc
  fallback: log/diffs.jsonl (sink:fallback)
```

Live production arc/worker: VPS systemd — see Reservoir `state/flow-os.md`.

## Scale pattern (target)
1. **Local queue** — agent writes near-zero-latency to memory/disk queue (sticky-note board), not wait on RPC.
2. **Batch flush** — worker packs N events → one bulk RPC / bulk insert.
3. **Offline validation** — vocabulary cache in-process; pocket dictionary, not round-trip.
4. **UI** — can read local queue via IPC for snappy feed; cloud remains SSOT after flush.

## Vocabulary growth without slop
Three-stage lifecycle:
| Stage | Name | Job |
|---|---|---|
| 1 | Sandbox | Unknown events allowed-but-tracked (`validation: unmapped` / sandbox stream) — don't crash hot path |
| 2 | Forge | Periodic cluster of near-duplicates; propose one canonical `domain.entity.action` |
| 3 | Lexicon | Promote into `diff-vocabulary.md` + in-DB `vocabulary` table; refresh local cache |

Constraints: namespace hierarchy only; frequency threshold before promote; similarity guard against near-dupes.

## Links
- [[AUM + BOMT — The Intelligence Compounding Vehicle]] — diffs as moat
- [[Flow OS Desktop Shell — Tauri + Company Pulse Theater]] — UI surfaces that *read* diffs
- [[Flow OS Team Surface — humans + agents]] — chat noise ≠ diffs
- Reservoir: `Exo Enterprise/product-PRD/diff-vocabulary.md`, `state/flow-os.md`

## Open (not decided here)
- [ ] When to build local queue daemon (Rust/Go vs keep ps1 for dogfood)
- [ ] Sandbox table vs jsonl for unmapped events
- [ ] Frequency threshold numbers for lexicon promote
