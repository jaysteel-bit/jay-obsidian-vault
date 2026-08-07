---
title: Flow OS Team Surface — humans + agents
created: 2026-08-04
updated: 2026-08-04
type: concept
tags: [flow-os, ui, architecture, product]
sources: ["Flow OS + Buzz.md"]
confidence: high
---

# Flow OS Team Surface — humans + agents

> Crystallized from root note `Flow OS + Buzz.md` (2026-08-04). Shell chrome direction still lives in [[Flow OS Desktop Shell — Tauri + Company Pulse Theater]] and Reservoir `DESKTOP-SHELL-UX.md` (locked). This page is the **Team / collab surface** decision cluster.

## Locked sentence
**Team** is a first-class Flow OS **shell** surface (evolve AX): humans + agents, shortest path, plain English. **Buzz is optional L1** under it, bridged into diffs. Not a department, not Admin, not Delivery OS, not Flowstate.

## Layers
| Layer | Job |
|---|---|
| **Team (product UI)** | Channels, DMs, agent members, threads — clients + Exo |
| **L1 Buzz (optional)** | Collab room, agent identity, signed event log — swappable relay |
| **L2 Diffs** | `emit_diff` + why — SSOT memory; **not every message is a diff** |
| **L3** | Not a department namespace (not Deal OS / Launch card) |

## Placement decisions
| Decision | Call |
|---|---|
| Client product? | Yes — per-tenant Team, not Exo-only |
| Name in UI | **Team** (never Buzz / AX for users) |
| Shell home | Evolve `/ax` → `/team` (or rename chrome) |
| Floating bar | Main tab beside Command Center |
| Right rail | Optional Team chip — not only entry |
| Admin | Rules/errors only — do **not** host Team |
| Flowstate | Leave alone; don't absorb collab |
| Delivery OS | Separate story — don't rename Buzz into it |
| Dogfood | Client-zero Team → bridge 1–2 events → HQ/Memory LIVE → tenants |

## Why it exists (sub-mission map)
Self-running enterprise needs humans + agents in one room without chain-of-command theater. Team acts → diffs remember → Reflex Arc reacts → fewer meetings.

## Links
- [[Flow OS Desktop Shell — Tauri + Company Pulse Theater]]
- [[emit_diff Chokepoint — Scale Without Slop]]
- [[Exo System Boundary Map]]
- Reservoir: `Exo Enterprise/departments/product/flow-os/DESKTOP-SHELL-UX.md`

## Open
- [ ] Route rename `/ax` → `/team` in codebase
- [ ] Which L1 relay for v1 (Buzz vs stub)
- [ ] First 1–2 event types bridged Team → emit_diff

## Appendix — 2026-08-07 (Agent-native honest take; from `Buzz UI functionality into Flow OS — agent-native honest take.md`)

**Blunt self-score (live code `8355e0e`, 2026-08-07):** Architecture story ~8/10 agent-native; **agent can actually do its job inside the product ~3/10**; human SaaS dogfood surface ~5–6/10 rising. Today an agent "using" Flow OS mainly means external Hermes/scripts call `emit_diff` / read Supabase — that is **API integration, not an agent coworker in the OS.**

**Order-of-operations disciplines (locked as build order):**
1. **postMessage is a UI process boundary, not the ledger.** The immutability is `emit_diff()` + why in Postgres — already law. Optimize host↔iframe transfer only when a profiler shows it (Phase C/D). Transferables/Arrow/Timescale are optional muscles, not Phase-A work.
2. **Buzz log ≠ Diffs Engine.** Buzz signed events are L1 commodity; the moat is vocabulary + why + multi-tenant memory + arc. If every chat line becomes a diff → slop ledger → prediction dies. **Bridge 1–2 event types only, and not until Buzz chat works in the embed** (`team_bridge` must not be written first).
3. **"Every state change" is a trap if literal.** Agent-native = every *decision-grade* state change, not keystrokes/cursors. Presence cursors must NOT hit the immutable business ledger. Decision unit still open (AUM dumps).
4. **Default Tauri `invoke` JSON is a real chokepoint — later.** Fix when a profiler shows it, not before first agent-handled escalation in prod.

**Agent-native success test (use this, not vibes):** an agent, as a Team member, can (a) observe a channel/event, (b) act with tools, (c) write a vocab-legal diff + why, (d) trigger arc/worker, (e) leave a replayable trail a human sees in Memory/HQ — **without** Jay pasting into Telegram. Until that loop is boring, it's SaaS with agent accessories.

**Priority to cross the line:** (1) one Part-C dogfood workflow emitting diffs all week (volume before binary pipes); (2) worker v0.2 — real LLM/Hermes on `agent_handle` (bigger unlock than postMessage); (3) Team bridge v0 after chat works; (4) agent identity mapping Buzz keys ↔ Flow OS actor on diffs.

Confidence: ~0.85 (repo pull + `state/flow-os.md` + Team shell source).
