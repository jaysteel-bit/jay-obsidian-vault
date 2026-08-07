---
categories:
  - "[[Dumps]]"
project:
  - "[[Exo]]"
topic: Exo AI browser extension — AI-generated summary from local files
type: dump
created: 2026-07-09
review_date:
tags:
  - brain-dump
  - exo-ext
  - browser-extension
acted-on: true
compiled: 2026-08-07
attachments:
backlog:
  - [ ] If Exo-Ext active in Phase 1: fork Page-Agent.js → add emit_diff() capture + why annotations → prototype the capture→diff→annotation loop
  - [ ] Migrate Exo-Ext source files from Desktop (C:\Users\viole\Desktop\EXO-EXT\) into agent-workspace for version control
---

## Quick Thoughts

AI-generated summary of Exo (the browser extension arm of Flow OS) from local Desktop files. Captured here for reference.

## Summary

Exo is the AI-powered browser extension arm of the Flow OS "Department-in-a-Box" ecosystem. It's an intelligent capture and command layer that lives inside Chromium browsers (Chrome/Edge/Brave/Arc) as a sidebar, so users interact with "Exo AI" without leaving their workflow.

### Flagship capability — SOP Capture

Uses `tabCapture`/`desktopCapture` APIs to record users' screens + narration as they work, then a multimodal backend (Claude/Grok/user's choice) turns that into clean, numbered SOPs with screenshots. Converts messy institutional knowledge into documented, repeatable processes.

### Why it's strategic

- **Department-aware intelligence** — detects the active Flow OS namespace (Deal OS → sales SOPs, Flow OS → workflow templates, Support OS → playbooks, onboarding → EXA integration) and formats output accordingly
- **Feeds the moat** — every captured SOP writes a diff into the eternal schema (`namespace: academy`, `entity_type: sop`, `event: created`), compounding proprietary workflow data into the BOMT model
- **Middleware positioning** — plugs into frontier models rather than training its own, keeping it capital-efficient and defensible through captured workflow data instead of LLM weights

### Business model

- **Self-Service Tier** — $20–50/user/month for autonomous SOP recording
- **Exo Concierge Tier** — high-touch ($500–2,000+/SOP or retainer): professional documentation sessions, multi-format output (video/PDF/interactive), QA'd and integrated into Exo Academy

### Source files (local Desktop)

1. `C:\Users\viole\Desktop\EXO-EXT\EXO-EXT Brainstorm.txt` — primary source for product description, SOP Capture, department-aware intelligence, middleware strategy, business model/pricing
2. `C:\Users\viole\Desktop\Exo Website Resources + Ai UCG Stuff.txt` — branding/website assets, UI templates, design references
3. `C:\Users\viole\Desktop\exo characters\` (directory) — logo and branding assets (JPEGs, transition videos, orb imagery)
4. Desktop shortcuts — `EXO-HTML - Shortcut.lnk` and `Exo Longterm Biz Snapshot - Shortcut.lnk`

No code repo or README found at root level — summary based entirely on brainstorm/resource text files.

### One-liner

Exo = the in-browser capture layer that turns how your clients actually work into the structured data that makes your whole Flow OS ecosystem smarter and stickier.

---

## Key Insights

- Exo Ext is the capture layer that feeds the diffs table — it's how you turn "tribal knowledge" into structured data
- Every captured SOP = a diff in the `academy` namespace = AUM base growth
- Middleware positioning (no model training) keeps it capital-efficient
- Concierge tier is the BOMT Build phase — high-touch service that installs Flow OS into the client's workflow

---

## Action Items / Next Steps

- [ ] Confirm whether Exo Ext is still in scope for Phase 1 or parked until Flow OS core is live
- [ ] If active: file paths need to be migrated into agent-workspace for version control

---

## Notes

**Source:** This note was auto-generated from a local AI conversation. The original brainstorm files live on Jay's Desktop (`C:\Users\viole\Desktop\EXO-EXT\`, `exo characters\`), NOT in the agent-workspace. If this product is activated, those files should be migrated into `Exo Enterprise/departments/product/exo-ext/` for version control and canonical ownership.

**Relationship to AUM model:** Exo Ext is the *capture layer* that feeds the diffs table. Without it, the `academy` namespace (SOPs, tribal knowledge) has no input source. It's not a standalone product — it's a sensor for the Reflex Arc.

---

**User to Agent**: Can't we use an open source software out there to act as a wrapper for us and brand ourselves (Exo Ext) = Exo Browser Extension? using something like Hermes browser feature that dropped … now that I think about it provides isn't open sourced like the actual hermes project… but this one is actually a possibility— ([Page-Agent.js](https://github.com/alibaba/page-agent)) = Our Own Nearly Identical Spin-off + diffs capture and mid/post why annotations

**Agent response:**

Yes — this is actually viable. Page-Agent.js (by Alibaba, MIT licensed) is a JavaScript in-page GUI agent that controls web interfaces with natural language. It lives directly in the browser. Here's how it maps to Exo Ext:

**What Page-Agent.js gives you out of the box:**
- In-page DOM interaction (click, type, navigate) via natural language commands
- Screenshot + narration capture during web interactions
- TypeScript-based, MIT license — you can fork, rebrand, and build on top freely
- Built on `browser-use` patterns (also MIT) — mature DOM interaction logic
- NPM package, one-line integration, works as a browser extension or embedded script

**What you'd build on top to make it Exo Ext:**
1. **Diffs capture layer** — intercept every action Page-Agent takes (click, input, navigate) and emit it as a diff to Flow OS via `emit_diff()`. Every DOM state change = a Tier 1 trigger. Every agent-initiated action = a Tier 2 decision.
2. **Mid/post "why" annotations** — after Page-Agent completes an SOP capture, prompt the user (or an LLM) to annotate WHY they took each step. This becomes the Tier 3 human "why" data that feeds your prediction engine.
3. **Exo branding** — fork the repo, strip Alibaba branding, apply Exo visual identity (orb, black/obsidian aesthetic). The MIT license allows this with attribution.
4. **Flow OS namespace detection** — detect which Flow OS namespace context is active (Deal OS, Support OS, Academy) and format the captured SOP accordingly.

**The key difference from Hermes browser feature:** Hermes Agent's browser tool is server-side (headless Chromium on the VPS) — it drives a browser remotely. Page-Agent.js is client-side — it lives IN the user's actual browser and watches THEM work. That's the right model for Exo Ext because you're capturing the human's real workflow, not automating from outside.

**What this is NOT:** This isn't the same as the Reflex Arc's SENSE layer (DB triggers, CDC, webhooks). Page-Agent.js captures the *human's browser interactions* — it's a separate capture channel for the `academy` namespace. It feeds SOPs and tribal knowledge into Flow OS, not operational state changes from the client's backend systems.

**Honest assessment:** This could shortcut Exo Ext development by months. Instead of building a screen recording + narration + SOP generation pipeline from scratch, you fork Page-Agent.js, add the diffs capture layer, add the "why" annotation prompts, and brand it. Maybe 2–4 weeks of work for a prototype vs. 2–3 months from scratch.

**Action:** If Exo Ext is in scope for Phase 1, fork Page-Agent.js → add `emit_diff()` integration → prototype the SOP capture + annotation flow. This is a weekend-scale prototype if you just want to prove the capture → diff → annotation loop works.