---
title: Flow OS Desktop Shell — Tauri + Company Pulse Theater
created: 2026-07-31
updated: 2026-07-31
type: concept
tags: [flow-os, architecture, ui, exo, roadmap, decision]
sources: ["flow-os-desktop-shell-ui-direction-2026-07-27.md", "Flow OS Desktop UI-UX.md", "Exo Launch - Air Build.md"]
confidence: high
---

# Flow OS Desktop Shell — Tauri + Company Pulse Theater

> Why Flow OS ships as a **desktop app**, what the shell should feel like, and the one thing that must survive the revamp. Compiled from three vault notes (Jul 26–27, 2026): the Grok Tauri-vs-Electron conversation, the full UI direction note, and the Exo Launch / Air.inc teardown. **Exo Launch creative/Comfy path:** see [[Exo Launch — Creative Ops (Air.inc map + ComfyUI ladder)]].

## The Problem It Solves

Jay is a visual founder, and dogfooding stalls when the prototype feels like "a webapp trapped in a desktop window." The shell isn't cosmetics — the product only gets exercised daily if it feels native enough to live in. That makes chrome a **loop-closure** issue, not a design preference.

## Decision 1: Tauri, not Electron

| | Tauri | Electron |
|---|---|---|
| Bundle | 5–20 MB (system WebView) | 100–200 MB (bundles Chromium) |
| Resource use | Low — matters when local AI agents run alongside | Higher |
| Backend | Rust | Node |
| Why it fits | Lean installer suits the B.O.M.T. transfer moment; native file access for local ComfyUI/GPU work | Faster if the team is JS-only |

Hermes Agent's desktop app uses Electron — the reference Jay started from — but its reason was that the team already had web + Python. Tauri wins here on bundle size, resource headroom, and the "professional installed software" feel that justifies high-ticket B2B pricing.

**Key insight — no data is lost by going desktop.** A Tauri app is a thick client. The Supabase database, the FastAPI Reflex Arc, and the Diffs Engine all stay in the cloud; the app makes the same API and WebSocket calls a browser tab would. It actually *gains* data leverage: OS-level permissions a browser blocks (local files, global shortcuts, active-app context) mean richer "why" context in the Diffs Engine.

## Decision 2: Wrap Flow OS itself, not just one namespace

An early framing wrapped only **Exo Launch** (the creative department) in Tauri, since creative work touches large local files. That was rejected: splitting Launch into a desktop app while Deal OS and Academy stay in the browser reintroduces exactly the context-switching fragmentation Flow OS exists to destroy. The whole OS gets the shell, or none of it does.

## Decision 3: Company Pulse is product identity, not marketing fluff

The critical correction in the direction note. An earlier draft treated the rotating hero headlines on HQ as disposable SaaS marketing and proposed replacing them with a Hermes-style telemetry status bar. **Wrong frame.**

Company Pulse is four layers working together:

| Layer | What | Answers |
|---|---|---|
| A — System Pulse | Pill: `SYSTEM PULSE · <5ms EFFICIENCY` + live dot | "Is the machine alive and fast?" |
| B — Rotating hero headlines | "Your team reclaimed 41 hours this week" · "$340k pipeline moved to Closed-Won" | "What did the machine *do* for me?" |
| C — KPI metric row | Hours reclaimed · Revenue influenced · Content published · Memory events | "Is it compounding?" |
| D — Atmosphere | Spline Exo orb behind hero type | brand presence |

Layer B is the **emotional** pulse and the reason HQ creates theater at all. The revised rule: **keep HQ as Pulse Theater; make the chrome around it IDE-native.** A global status bar (arc · client · last diff) is *additive*, never a replacement.

## The Blend

```
┌─ titlebar: Flow OS · ⌘K · [layout][settings][theme] · ─ □ × ─┐
├─ activity (icons) ─┬─ workbench ──────────────┬─ agent rail ─┤
│  HQ / Flows /      │  HQ = PULSE THEATER      │  chat + ctx  │
│  Memory / Depts    │  Other routes = dense    │  collapsible │
├────────────────────┴──────────────────────────┴──────────────┤
│ optional global status: arc · client0 · last diff · namespace │
└───────────────────────────────────────────────────────────────┘
```

- **Steal from Codex/ChatGPT:** flat density, calm empty states, intent cards as a secondary layer, composer-as-primary, real OS chrome.
- **Steal from Hermes:** utility titlebar, status bar, ambient art *behind* chrome, right panel as context.
- **Don't steal:** chat-history-as-primary-left-nav from either. Flow OS's left rail stays product surfaces (HQ / Workflows / Memory / Departments).

## Where the Dogfood Loop Closes

The rotating headlines and KPI cards are currently hardcoded. The payoff arrives when they read real data — last diffs and `rule_executions` rows becoming the headlines. That connects this shell work to the Diff Write Contract: the same diffs that make [[AUM + BOMT — The Intelligence Compounding Vehicle]] a prediction engine are what make HQ's theater *true* rather than decorative.

## Status and Boundaries

- Direction doc is **locked**: `agent-workspace/Exo Enterprise/departments/product/flow-os/DESKTOP-SHELL-UX.md`
- Phase 0 = chrome only (titlebar utilities, density pass, activity bar, agent rail, Atmosphere/Focus). HQ theater untouched.
- Explicitly **not yet**: full File/Edit/View menus, rewriting department pages, Hermes-style session list as primary nav, and — emphatically — killing the rotating hero.
- Code lives in the third home, the Flow OS repo — not this vault and not the Reservoir. See [[Exo System Boundary Map]] for which repo owns what.

## Related

- [[Exo System Boundary Map]] — the three homes (Code · Reservoir · Forge) this work spans
- [[AUM + BOMT — The Intelligence Compounding Vehicle]] — why real diffs behind the pulse metrics matter
- [[Exo Vault Meta-Leverage System]] — the vault-as-business-brain pattern the Memory surface exposes
