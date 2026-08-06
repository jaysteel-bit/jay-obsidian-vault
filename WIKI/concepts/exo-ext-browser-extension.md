---
title: Exo-Ext — Flow OS Browser Extension
created: 2026-08-06
updated: 2026-08-06
type: concept
tags: [flow-os, product, sop, captures, delivery-os, browser]
sources: ["Exo-Ext (Flow OS -or- Exo AI Browser Extension).md"]
confidence: medium
---

# Exo-Ext — Flow OS Browser Extension

> Crystallized from root note `Exo-Ext (Flow OS -or- Exo AI Browser Extension).md` (2026-08-06). A browser-extension capture/command layer that embeds Flow OS's "Department-in-a-Box" directly into the user's daily browsing. Not a standalone app — a side panel where users live.

## The core idea
A sidebar/side-panel in Chromium browsers (Chrome, Edge, Brave, Arc). Talks to the Flow OS backend over standard API calls; sends captured context (screenshots, selected text, URLs) and displays responses inline — preserving the **diffs-based architecture** that powers the reflex arc engine.

## Flagship feature: SOP Capture
- **Real-time workflow documentation** via Chrome `tabCapture` + `desktopCapture` APIs.
- User clicks "Start SOP Recording," narrates steps in natural language, clicks "Stop."
- Multimodal AI (Claude 3.5 Sonnet / Grok / user choice) processes video frames + audio transcription → clean, structured SOPs (numbered steps, screenshots, instructions).
- Turns messy ad-hoc knowledge into documented, repeatable processes that survive team turnover — **a top ICP pain point**.

## Department-aware intelligence
Detects which Flow OS namespace the user is in (by URL, tab content, or selection) and formats output accordingly:
- CRM (Deal OS) → sales process SOPs with deal stages
- Project management (Flow OS) → workflow templates
- Customer support (Support OS) → support playbooks / CS focus
- Onboarding/training → EXA keeps new hires up to speed in their tabs

Every captured SOP auto-creates diffs in the eternal schema (`namespace:academy`, `entity_type:sop`, `event:created`…) — **feeds the data-gravity moat with proprietary human judgment and workflow knowledge.** It's the front door to the BOMT (Build-Operate-Manage-Transfer) delivery model.

## The middleware strategy (validated)
Positioning as a **catch-all assistant that plugs into frontier models** rather than training its own:
- Capital efficiency (avoids $100M+ training)
- Best-of-breed models through one interface
- Defensible moat = workflow data + department-specific reflex arcs, **not** the underlying LLM
- Aligns with the Flow OS thesis: learn from workflows, build data defensibility through structured diffs

## Business model (under review — "pricing needs one more pass")
| Tier | Price | What it is |
|---|---|---|
| Self-Service | $20–50/user/mo | Teams record + generate their own SOPs autonomously |
| Exo Concierge | $500–2,000+/SOP or retainer | Pro documentation sessions, multi-stakeholder interviews, multi-format SOPs (video/PDF/playbooks), QA |

Mirrors the BOM/T hybrid: start with software (extension), layer in services (Concierge), compound value via Exo Academy (all captured SOPs feed the knowledge-synthesis engine).

## Open / notes
- Agent "critical thoughts and enchantments / overhaul" section in source is blank — the concept's strategic sharpening is not yet done.
- Pricing needs a deliberate reconsideration (flagged in source).
- Positioning as the capture front-door for BOMT raises the dependency-lock for clients — strategic strength, worth cons labeling in an offer review.

## Links
- [[Flow OS Desktop Shell — Tauri + Company Pulse Theater]] (capture layers sit on the same Flow OS backend)
- [[Exo Launch — Creative Ops]] (another front-door/UI surface of the same engine)
- [[AUM + BOMT — The Intelligence Compounding Vehicle]] (SOP-capture feeds the data moat / § Academy)
- Root note: `Exo-Ext (Flow OS -or- Exo AI Browser Extension).md`
