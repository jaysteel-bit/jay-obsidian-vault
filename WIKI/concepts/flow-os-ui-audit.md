---
title: Flow OS UI Audit — route-by-route vs Diffs vision
created: 2026-08-06
updated: 2026-08-06
type: concept
tags: [flow-os, ui, product, roadmap, architecture]
sources: ["../../FLOW OS ANALYSIS.md"]
confidence: medium
---

# Flow OS UI Audit — route-by-route vs the Diffs vision

> A full route-by-route audit of the running Flow OS frontend against the Diffs Engine vision, the BOM-T delivery model, and what a real client needs. Source: vault root `FLOW OS ANALYSIS.md` (2026). **Overall verdict: the UI is polished — the problem is that most of it runs on fake demo data, and two routes outright contradict the business model.**

## The one-sentence takeaway

The audit's biggest issues are **not** UI quality — it's that (1) most routes run on hardcoded demo data, (2) `/launch` and `/subscribe` are misaligned with the model to the point they should not be shown to clients, and (3) `/academy` was built for a different (consumer EdTech) audience. The **Memory page is the closest to the actual vision and should be the next thing wired to real data.**

## Route-by-route verdict

| Route | Alignment | Real data? | Keep / Fix / Cut |
|---|---|---|---|
| `/` HQ | ✅ Strong | Partial | Keep — wire Diffs data (rotating headline IS the Diffs Engine; B.O.T. phases map to BOM-T; "Unlock Next Department" nails the namespace-unlock model) |
| `/workflows` | ✅ Good | ✅ Yes | Keep — reframe from "generic Zapier" to the **REACT layer of an immutable diff log** (Reflex Arc SENSE→REACT→REMEMBER is invisible); template gallery = hidden sales/onboarding gem |
| `/memory` | ✅ Perfect concept | ❌ All fake | **Priority fix — needs real Diffs.** The crown jewel: diff cards with before/after, department namespacing, timeline scrubber to replay company history. This page alone is worth showing to clients once wired. |
| `/academy` | ❌ Wrong audience | ❌ All fake | **Redesign for Transfer-phase operators.** Built as consumer EdTech (locked $2,500 tier, leaderboard, Fortune-500 logos) — Exo Academy's real job is certifying a client's BOM-T Transfer operators. |
| `/ax` | 🟡 Right concept | ❌ All fake | Fix — align agents to real Flow OS namespaces (Deal OS, Launch, Academy, AURA); "Steel Security" badge suggests stale Steel-brand thinking; wire ≥1 real agent |
| `/deal-os` | 🟡 Partial | ❌ All fake | Keep pipeline/revenue view; **move Script Dojo (memorization game) to Academy or cut it** — wrong nav for a sales dashboard |
| `/flowstate` | ❓ Undefined | ❌ All fake | Define purpose first — reads like a dev/power-user console, not a client-facing view; shouldn't be in main sidebar nav without definition |
| `/launch` | ❌ Wrong entirely | ❌ All fake | **Rebuild from scratch or hold.** Current = a toy ComfyUI/Midjourney canvas with one hardcoded prompt. Exo Launch should be a creative **department OS** (campaign gen, brand enforcement, multi-format repurposing, approval). "Do not show this to anyone." Cross-ref [[Exo Launch — Creative Ops (Air.inc map + ComfyUI ladder)]]. |
| `/settings` | 🟡 Fine structure | ❌ All fake | Fix billing tab — shows consumer monthly SaaS ($29/$99/$3,000) that **contradicts BOM-T**; a client in a $40k engagement shouldn't see "Upgrade to Pro." API keys/webhooks sections are genuinely important (Slack/HubSpot/etc.) |
| `/subscribe` | ❌ Wrong model | — | **Remove or hide** — implies Flow OS is self-serve SaaS ($15–60k BOM-T program is how it's actually sold). Would confuse/undervalue the product in front of a client |
| `/admin-internal` | ✅ Perfect | ✅ Yes | **Leave it — this is the standard.** Error tracking + Rules Engine are the REACT phase, backed by real Supabase data. The model for how the rest gets built. |

## What this means (build-order signal)

The **Rules Engine/admin-internal** is proof that "real-data route" is achievable — it's the reference implementation. The next real-data candidate is **`/memory`** (the crown jewel). Everything else is either (a) already directionally right and just needs data, or (b) misaligned and should be hidden/rebuilt before any client sees it (`/launch`, `/subscribe`, `/academy`).

Open items for Jay / [[Flow OS Desktop Shell — Tauri + Company Pulse Theater]]:
- Prioritize wiring real Diffs into `/memory` (the single highest-leverage real-data win).
- Define `/flowstate`'s purpose (internal eng tool, client power-user view, or cut) before it stays in nav.
- Decide whether a self-serve SaaS tier exists at all; if not, remove/hide `/subscribe`.
- Rebuild `/launch` as a real creative department OS or hold it.
- Point `/academy` at BOM-T Transfer operator certification, not consumer EdTech.

## Related Pages

- [[Flow OS Desktop Shell — Tauri + Company Pulse Theater]] — the shell/Company Pulse decision; audit is the route-level layer beneath it
- [[Flow OS Team Surface — humans + agents]] — AX surface; audit's `/ax` verdict feeds it
- [[emit_diff Chokepoint — Scale Without Slop]] — the Diffs engine underneath all this UI
- [[Exo Launch — Creative Ops (Air.inc map + ComfyUI ladder)]] — `/launch` rebuild reference
- [[AUM + BOMT — The Intelligence Compounding Vehicle]] — the delivery model the audit measures against
