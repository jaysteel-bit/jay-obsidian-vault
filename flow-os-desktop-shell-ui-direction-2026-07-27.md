---
type: notepad
topic: Flow OS desktop shell / UI direction
date: 2026-07-27
status: draft-for-lock — awaiting Jay confirm
sources:
  - CHATGPT-UI refs (Desktop Codex)
  - HERMES-UI refs
  - FLOW-OS - UI (Company-pulse.JPG, flow-HQ.JPG)
  - Grok session (flow-os repo)
related:
  - Exo Enterprise/departments/product/flow-os/DESKTOP-SHELL-UX.md
  - flow-os/AGENTS.md (three homes + desktop routing)
project:
---

# Flow OS Desktop Shell — UI Direction Note (full)

> Written so Jay can re-read later. Includes original Hermes/Codex teardown **plus** correction: **Company Pulse = mini system bar + rotating hero headlines**, not status-bar-only.

---

## 0. Context

Jay: visual founder, dogfooding blocked by “webapp trapped in a desktop window.”  
Likes Hermes Agent Desktop + ChatGPT/Codex app feel.  
Wants IDE-native chrome while keeping Flow OS template DNA.

**Three homes (locked in flow-os AGENTS.md):**

| Home | Path | Role |
|------|------|------|
| Code | `C:\Users\viole\Desktop\flow-os` | Product software |
| Reservoir | `C:\Users\viole\Desktop\agent-workspace` | Decisions + SSOT |
| Forge | `C:\Users\viole\Desktop\jay-obsidian-main` | Raw thinking |

---

## 1. ChatGPT / Codex references (what they do)

**Files:** `Desktop/02 - UI References & Screenshots/CHATGPT-UI/`

| Pattern | What it does |
|--------|----------------|
| **OS chrome is real** | Titlebar + File · Edit · View · Help — installed app, not browser tab |
| **Near-flat dark** | Almost no glass/glow/marketing orbs — calm charcoal |
| **Left = simple IA** | New task, Scheduled, Plugins, Chat + Pinned / Projects / Tasks |
| **Empty state intentional** | Soft mark + one question + **4 intent cards** |
| **Composer is the product** | Bottom floating input: context chip, mode, model, mic, send |
| **Profile dock** | Bottom-left account |
| **No telemetry status bar** | Consumer calm over ops IDE |

**Steal:** calm empty language, intent cards (as optional layer), composer-as-primary, flat density, native menu/title chrome.  
**Don’t steal:** pure chat-app IA (Flow OS has HQ / Memory / Workflows / Depts).

---

## 2. Hermes references (what they do)

**Files:** `Desktop/02 - UI References & Screenshots/HERMES-UI/`

| Pattern | What it does |
|--------|----------------|
| **Three-zone workbench** | Left sessions · center conversation · right workspace tree |
| **Status bar = “this is software”** | Gateway · Agents · Cron · branch · tokens · version |
| **Ambient art, not UI** | Classical painting *behind* chrome; content still readable |
| **Utility titlebar** | Layout / volume / settings / theme next to window controls |
| **Empty state = branded typography** | “HERMES AGENT” + one line + composer |
| **Composer dock** | Bottom-center, model + send |
| **Setup progressive** | Installer → “HERMES IS READY” |

**Steal:** status bar idea, ambient-behind-chrome, right panel as context, utility titlebar, branded presence that still feels like work.  
**Don’t steal:** left rail as *only* chat history — left stays **product surfaces** (HQ / Workflows / Memory / Depts).

---

## 3. FLOW-OS own HQ / Company Pulse (critical keep)

**Files:** `Desktop/02 - UI References & Screenshots/FLOW-OS - UI/`

- `Company-pulse.JPG`
- `flow-HQ.JPG`
- (+ screen recordings for motion)

### What “Company Pulse” actually is (Jay correction)

**Not only** the mini stop-sign / pill bar.  
**Company Pulse = two layers that work together:**

#### Layer A — System Pulse (mini bar / telemetry chip)

From refs:

- Pill: **SYSTEM PULSE** · green live dot · **&lt;5ms EFFICIENCY**
- Sits at top center of HQ (hero zone)
- “Is the machine alive / fast?” — operational health

#### Layer B — Rotating hero headlines (the HERO vibe)

From refs / current HQ code:

- Large centered rotating copy, e.g.:
  - “Your team reclaimed 41 hours this week”
  - “Exo Launch published 12 posts automatically”
  - “$340k pipeline moved to Closed-Won”
  - “Sarah closed onboarding for Acme Co — 6 days faster”
- Subline: “Real-time intelligence from the Exo Neural Network”
- **This is the emotional company pulse** — narrative, not just ms latency
- Creates the HQ *theater* Jay wants to dogfood against (visual founder surface)

#### Layer C — Pulse metrics row (HQ board)

From `flow-HQ.JPG`:

| Card | Example |
|------|---------|
| Hours reclaimed | 167 ↑23% |
| Revenue influenced | $1.2M ↑41% |
| Content published | 84 ↑19% |
| Company memory events | 12,847 |

Plus: Active Workflows rail, CTAs (New Flow, Open Recent Memory, Unlock Next Department), B.O.T. progress.

#### Layer D — Atmosphere

- Spline / 3D Exo orb behind hero type
- Soft light (or dark) field — brand, not clutter *if* type stays readable

### Implication for shell direction

Earlier draft risked **killing the rotating headlines as “marketing hero.”**  
**Wrong frame.** For Flow OS, that rotation *is* Company Pulse narrative layer — product identity on HQ, not disposable SaaS fluff.

Revised rule:

> **Keep HQ as Pulse Theater** (pill + rotating headlines + KPI row + ambient).  
> **Make the chrome around it IDE-native** (titlebar, activity bar, status bar, agent rail, density).  
> Don’t demote pulse to status-bar-only chips.

What *can* still change without killing pulse:

- Window chrome no longer “browser tab”
- Left nav denser / icon-default on desktop
- Right rail tighter, less filler charts
- Optional **global** status bar for arc/client/last-diff (Hermes-style) **in addition to** HQ pulse theater — not as a replacement for rotating words
- Focus mode can dim ambient; Atmosphere keeps Spline + hero glow

---

## 4. Gap vs Flow OS today

```
Codex:   calm app + composer-first
Hermes:  IDE workbench + status + ambient brand
Flow OS: multi-surface ops product — HQ pulse is intentional theater,
         but chrome still reads “website in a window”
```

| Already have (keep) | Still missing (shell) |
|---------------------|------------------------|
| X-like left nav | Flat density + integrated title utilities |
| Right collapsible rail | Feels like **context panel**, not wide glass filler |
| Spline ambient | Behind work; Focus vs Atmosphere |
| **Company Pulse full stack** (pill + rotating hero + KPIs) | Must survive shell revamp |
| Custom titlebar | Still thin strip over web content |
| HQ / Memory / Workflows IA | Same IA inside denser workbench |

---

## 5. Recommended blend (updated after pulse correction)

```
┌─ titlebar: Flow OS · ⌘K · [layout][settings][theme] · ─ □ × ─┐
├─ activity (X icons) ─┬─ workbench ─────────────────┬─ agent rail ─┤
│  HQ / Flows / Memory │  HQ = PULSE THEATER         │  chat + ctx  │
│  Depts…              │    · System Pulse pill      │  collapse OK  │
│                      │    · Rotating hero headlines│              │
│                      │    · KPI cards + workflows  │              │
│                      │  Other routes = dense panels│              │
├──────────────────────┴─────────────────────────────┴──────────────┤
│ optional global status: arc · client0 · last diff · namespace ─────│
└───────────────────────────────────────────────────────────────────┘
```

| From Codex | From Hermes | From Flow OS (sacred keep) |
|------------|-------------|----------------------------|
| Flat density, profile dock | Utility titlebar, optional global status | **Full Company Pulse (pill + rotation + KPIs)** |
| Composer pattern (agent) | Ambient-behind-chrome | X left nav, right rail, Memory |
| Intent cards *as secondary* on non-HQ or empty subviews | 3-column when agent open | Spline Atmosphere, HQ theater |

**One-line product fit:**  
*Hermes chrome + Codex restraint around a Flow OS HQ that remains Company Pulse theater (telemetry chip + rotating narrative + metrics), not a stripped status strip.*

---

## 6. Moves (proposed — not locked)

### Move 1 — Reference lock (docs)
- This NOTEPAD note (done)
- Reconcile `DESKTOP-SHELL-UX.md` after Jay confirms (explicit: pulse = pill + rotation + KPIs)

### Move 2 — Phase 0 shell (code, visual dogfood)
1. Integrate titlebar utilities (⌘K, theme, settings)
2. Density pass on chrome only (not gutting HQ hero)
3. Activity bar icon-default on Tauri; profile bottom-left
4. Agent rail ~22–24rem; remove filler productivity chart
5. Atmosphere / Focus for Spline
6. Optional thin **global** status bar (arc/client/diff) — **does not replace** HQ pulse theater

### Move 3 — Phase 1 HQ (careful)
- **Preserve** System Pulse pill + rotating headlines + KPI row + orb
- Wire real data into rotation/KPIs over time (dogfood: last diffs, rule_executions as headlines)
- Active workflows + CTAs stay; tighten layout density around theater, don’t delete theater
- Optional bottom composer: “Ask / annotate / emit test diff”

### Move 4 — Don’t do yet
- Full File/Edit/View menu (later)
- Rewriting every department page
- Hermes session list as primary left nav
- Killing Spline / X-nav / right rail
- **Killing rotating hero as “marketing”**

---

## 7. Success criteria (updated)

- [ ] Tauri open does not feel like a browser tab
- [ ] **Company Pulse still hits:** pill + rotating words + KPIs still create HQ hero vibe
- [ ] Jay can dogfood pulse + memory + rail without fighting layout
- [ ] Same IA (HQ / Workflows / Memory / Depts) &lt;2 clicks
- [ ] Part C outcomes can eventually feed rotating headlines / KPIs / global status
- [ ] Keep-list intact (nav, rail, ambient, memory, **full pulse**)

---

## 8. Open for Jay confirm (then lock)

1. **HQ Pulse Theater stays** as the emotional center — yes/no?  
   *(Grok read: yes, per this correction.)*
2. **Global Hermes-style status bar** as *additive* chrome — yes / no / later?
3. **Phase 0 shell first** (chrome only, HQ theater untouched) — yes?
4. Any kill/keep changes on KPI cards or bottom CTAs?

**Status:** Draft for lock. Do not implement shell until Jay confirms.

---

## 9. Related paths

| Artifact | Location |
|----------|----------|
| This note | `agent-workspace/NOTEPAD/flow-os-desktop-shell-ui-direction-2026-07-27.md` |
| Shell direction doc | `agent-workspace/Exo Enterprise/departments/product/flow-os/DESKTOP-SHELL-UX.md` |
| HQ page | `flow-os/app/(dashboard)/page.tsx` |
| Layout shell | `flow-os/app/(dashboard)/layout.tsx` |
| Titlebar | `flow-os/components/desktop/titlebar.tsx` |
| Left / right | `flow-os/components/flow-os-sidebar.tsx`, `flow-os-right-sidebar.tsx` |
| Refs Codex | `Desktop/02 - UI References & Screenshots/CHATGPT-UI/` |
| Refs Hermes | `Desktop/02 - UI References & Screenshots/HERMES-UI/` |
| Refs Flow HQ | `Desktop/02 - UI References & Screenshots/FLOW-OS - UI/` |
