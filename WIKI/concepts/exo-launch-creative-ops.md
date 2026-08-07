---
title: Exo Launch — Creative Ops (Air.inc map + ComfyUI ladder)
created: 2026-08-05
updated: 2026-08-05
type: concept
tags: [flow-os, exo, architecture, feature, roadmap]
sources: ["Exo Launch - Air Build.md"]
confidence: medium
---

# Exo Launch — Creative Ops (Air.inc map + ComfyUI ladder)

> Crystallized from root dump `Exo Launch - Air Build.md` (triaged 2026-08-05).  
> Shell/Tauri decisions already locked on [[Flow OS Desktop Shell — Tauri + Company Pulse Theater]] — this page owns **Launch as creative department** + **generation backend ladder**.

## One-liner
**Exo Launch** = Flow OS creative namespace (briefs, brand, approvals, multi-format output). **Air.inc** is the competitive/capability map (DAM + collab + multiplication). **ComfyUI** is the execution engine behind a swappable API wrapper — not a fork into the OS.

## Role split
| Layer | Job |
|---|---|
| Exo Launch | Orchestration — prompts, brand rules, approvals, multi-format |
| Flow OS | Control plane — diffs, memory, multi-tenancy, Reflex Arc |
| ComfyUI (or peer) | Asset execution — generate pixels/video |

## Air.inc → Launch capability map
| Dimension | Air.inc | Exo Launch direction |
|---|---|---|
| Ingestion | AI tag + video transcription (Paige) | Parse/search (Docling / OpenNotebook class tools) |
| Workflow state | Visual Kanban + versions | Reflex Arc + workflow state diffs |
| Content scaling | Generative resize/reformat + many models | Multi-format multiply; custom models via trainer path (e.g. LTX) |
| Audit | Version stack | Diffs Engine + human why annotations |
| External handoff | Upload forms + permissioned boards | Client portals without email chaos |

Worth building; not easy. Proofing comments → diffs is the moat move (human *why* on creative revisions).

## ComfyUI integration ladder
| # | Path | When | Verdict |
|---|---|---|---|
| 1 | **Comfy Cloud API** | MVP / dogfood | **Phase 1 default** — zero infra, validate orchestration + diffs |
| 2 | **RunPod/Vast + Comfy API** | Custom LoRAs / client models / volume | **Phase 2** — same workflow JSON, swap endpoint |
| 3 | **Comfy MCP (agentic)** | Autonomous dept later | Phase 3 — less deterministic; brand risk if LLM builds graphs ad hoc |
| 4 | **Fork ComfyUI** | Never default | **Avoid** — maintenance + violates vendor-independent abstraction |

**Abstraction rule:** Launch talks to a standard generation wrapper. Backend can move Cloud → RunPod → MCP without rewriting UI or diffs.

## Tauri (cross-link only)
Early “Launch-only desktop” framing **rejected** — wrap **all of Flow OS** (see desktop shell page). Data stays cloud; desktop is thick client. Local Comfy via `localhost` is a hybrid bonus, not a reason to split namespaces.

## Links
- [[Flow OS Desktop Shell — Tauri + Company Pulse Theater]]
- [[emit_diff Chokepoint — Scale Without Slop]]
- [[AUM + BOMT — The Intelligence Compounding Vehicle]]
- [[Exo System Boundary Map]]
- Reservoir (locked shell): `Exo Enterprise/departments/product/flow-os/DESKTOP-SHELL-UX.md`

## Open (not locked)
- [ ] Commit Phase 1 = Comfy Cloud for dogfood assets?
- [ ] First hero workflow JSON + Launch inject path
- [ ] When RunPod account exists → Phase 2 gate
- [ ] Agency must-haves: Figma/Adobe + Slack first (see UVP gap table)

## UVP gaps vs Air (research 2026-08-05) — copy *selectively*

Already covered in dump/wiki: DAM/tag, video chapters/transcripts, pin-on-asset proofing, Kanban status, multiply/resize, guest upload forms, permissioned boards.

**Underweighted in our dump — worth stealing for Launch UVP:**

| Gap | Air pitch | Launch / Flow OS angle |
|---|---|---|
| **Creative intelligence + conversational search** | Find by color/face/object/“however you remember it”; auto tags/summaries/chapters on ingest | NL search over library + transcripts; not folder archaeology |
| **Performance loop** | Library ↔ **ad performance** so you make more of what works | Diffs + campaign outcomes → brief the next gen (AUM-adjacent) |
| **Canvas / brand kit in multiply** | 50+ models, brand kit baked into bulk edit | Multiply only from **approved** masters + brand rules as hard constraints |
| **Desktop sync** | Local FS sync; open in native tools; save back | Tauri thick client already planned — local heavy files without full cloud hop |
| **Intake → delivery one flow** | Creative ops = memory of versions/approvals/decisions, not just storage | Same story as diffs: system of record for creative *decisions* |
| **Visual-first status** | Thumbnail + status + version + feedback at a glance | HQ/Launch surfaces must show state on the asset, not only ticket lists |
| **Stack integrations** | Figma, Adobe, Slack, Canva, Asana, Notion, Zapier | Agency adoption hinges here more than “another model picker” |
| **Time-to-value** | Hours to deploy, week to fluency | BOMT dogfood must feel this — not 6-month DAM program |
| **Enterprise** | SSO, custom permissions | Multi-tenant Flow OS already; don’t forget guest vs seat model |

**Do not copy blindly:** Air is creative-ops SoR for *files*. Our wedge is **department OS + diffs/why + agents**. Use Air’s file UX patterns; win on cross-dept memory and automation.

## Reservoir task
- `agent-workspace/state/tasks/exo-launch-comfy-cloud-phase1.md`
