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
acted-on: false
attachments:
backlog: true
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

**WORKFLOW:** This is a capture zone for business thoughts and tangents. When an idea hits, create a new dump note. Review periodically (weekly recommended) to extract insights into Projects, Ideas, or Admin tasks. Once reviewed, update `review_date` and archive by moving to a completed state.

**User to Agent**: Can’t we use an open source software out there to act as a wrapper for us and brand ourselves (Exo Ext) = Exo Browser Extension? using something like Hermes browser feature that dropped … now that I thibk about it provides isnt open sourced like the actual hermes project… but this one is actually a possibility— ([Page-Agent.js](https://github.com/alibaba/page-agent)) = Our Own Nearly Identical Spin-off + diffs capture and mid/post why annotation 