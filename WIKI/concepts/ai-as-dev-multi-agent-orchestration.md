---
title: AI-as-Dev — Multi-Agent Orchestration
created: 2026-08-07
updated: 2026-08-07
type: concept
tags: [flow-os, ai-dev, multi-agent, orchestration, pm-workflow]
sources: ["Q-A AI CODING SYSTEM DRAFT.md"]
confidence: medium
---

# AI-as-Dev — Multi-Agent Orchestration

> Crystallized from root note `Q-A AI CODING SYSTEM DRAFT.md` (2026-08-07). The playbook for a non-technical founder (CEO-as-PM) using AI agents as their engineering team, with a single source of truth coordinating multiple autonomous workers without them stomping each other.

## The two layers

**Layer 1 — Single-agent build (CEO prompt workflow).**
- Use an AI-first code editor (Cursor / Windsurf) with a strong model selected inside it.
- Never ask it "build Flow OS." Break into literal, sequential prompts: (1) backend setup against a target Supabase schema → (2) static UI layout → (3) wire UI to data with mock events.
- **The CEO rule on errors:** never fix code manually — copy the exact terminal error back into the AI and ask it to fix its own bug.

**Layer 2 — Multi-agent (task registry + folder isolation).**
- Coordinate via a single source-of-truth file, e.g. `SYSTEM_STATE.md`, with columns Backlog / In Progress (file path + Agent ID) / Blocked / Completed. No agent writes code without checking it first.
- **Isolate by folder/layer** so two agents never touch the same file: e.g. Agent-Backend (FastAPI) / Agent-Frontend-Layout (components) / Agent-Frontend-Data (data-fetch).
- **Supervisor loop** (cron / Hermes, or Aider / Devika): wake → read SYSTEM_STATE.md → evaluate a completed row → unblock the dependent agent by editing the state file → alert on agents stuck in BLOCKED.
- **CEO oversight:** don't review code; review SYSTEM_STATE.md once or twice a day and re-route via text if direction drifts. Unattended parallel agents can generate a lot of code that silently deviates from the vision.

## Why it matters for Exo
This is the exact pattern the agent-workspace itself already runs (harness state + task registry + supervisor). Deploying it on Flow OS dev lets Jay scale build velocity without hiring human devs and without becoming the bottleneck.

## Links
- [[Flow OS — UI Audit]]
- [[Flow OS Desktop Shell]]
- [[Emit-Diff Chokepoint & Scale]]

## Backlog
- [ ] Consider landing this as a Flow OS / internal engineering SOP page (promote-candidate after Jay signs).
