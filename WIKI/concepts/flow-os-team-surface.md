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
