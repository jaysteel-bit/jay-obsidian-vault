---
title: Reflex Arc Data Infrastructure — Sovereign Stack
created: 2026-08-07
updated: 2026-08-07
type: concept
tags: [flow-os, architecture, database, infrastructure]
sources: ["AI.md"]
confidence: medium
---

# Reflex Arc Data Infrastructure — Sovereign Stack

> Crystallized from loose root note `AI.md` (2026-08-07) — a Grok conversation exploring how to build the **Diffs + Why** storage and Reflex Arc orchestrator on a database-first, zero-lock-in stack. This is the *data-layer / DB-choice* thinking behind the diffs engine; the scale/vocabulary doctrine lives on [[emit_diff Chokepoint — Scale Without Slop]].

## The core idea
`diffs` + `why` annotations are **time-series event streams** (logs of state change over time). Store and query them with a database-first stack that keeps the AI agent productive without sacrificing security or portability — and packages the whole thing as a **sovereign, transferable unit** (BOM/T-ready).

## The stack (three layers, one story)

| Layer | Tool | Role |
|---|---|---|
| Infrastructure | Supabase (hosted) or bare VPS Postgres | Storage engine; RLS; realtime/websockets; auth |
| Schema / app | **Constructive** (`agentic-db` + `pgpm`) | Native-Postgres, AST-based schema as versioned NPM-like packages; auto type-safe SDK; RLS baked into the engine, not a middle tier |
| Time-series | **TimescaleDB** | Hypertable sharding + ~90% columnar compression + continuous aggregates for agent metrics |

**Hierarchy:** FastAPI Reflex Arc orchestrator (Sense → React → Remember) on top → Constructive schema layer (agentic-db memory + custom Diffs/Why modules) → native Postgres engine (Supabase or self-hosted with Timescale) → VPS / client cloud.

## Why this combination
- **RLS-in-engine security:** auth + row-level security live inside Postgres, so an LLM agent `physically cannot` read rows it shouldn't, even if it hallucinates an exploit — the security guarantee for multi-tenancy.
- **AST all the way down:** code, schema, and UI are trees; the system syncs/optimizes without brittle mapping. Constructive auto-generates the client SDK + React components + GraphQL/REST from the DB AST.
- **pgpm migrations:** schemas become versioned distributable packages (install/update/rollback like npm), avoiding the sequential-SQL migration-conflict mess when agents and humans edit together.
- **Diffs + Why as time-series:** `agent_state_diffs` table → Timescale hypertable; continuous aggregate computes token-velocity, error-rate, memory-drift signals without lagging the live table.
- **Zero vendor lock-in:** Constructive is just native Postgres schemas + a Node/TS package manager — swap Supabase for raw VPS Postgres by changing a connection string.

## The BOM/T payoff (why Jay flagged Option B as "the absolute winner")
The sovereign Docker stack (Caddy reverse proxy → FastAPI orchestrator → Supabase services → Timescale+Constructive Postgres) is a **single transferable git repo + compose file**. In the Manage/Transfer phase you hand the client this self-contained unit — turning Transfer from "loss of revenue" into a high-margin software-license handover. Option A (hosted Supabase + pg_partman) is the cheap pre-revenue start; Option B (self-hosted sovereign stack) is the transfer-phase delivery.

## Agent-codeguardrails (the foot-gun)
Context drift is the real maintenance risk. Rules: (1) agents *write* migrations, never execute them directly; (2) route agent schema changes to an isolated branch; (3) human reviews before pgpm deploys; (4) strict DB role without ALTER/DROP. Plus ops hygiene: disk-space cron, backup-restore testing monthly, reverse-proxy (Caddy) exposure / port hardening.

## Decision status / open
- **Not yet a locked build decision** — this is the DB-layer option space for the diffs engine. Exo currently dogfoods `emit_diff()` on hosted Supabase (see [[emit_diff Chokepoint — Scale Without Slop]] and Reservoir `state/flow-os.md`).
- [ ] Decide: hosted Supabase + pg_partman (start cheap) vs Constructive + Timescale sovereign stack (build toward transfer) — or phased A→B.
- [ ] Whether to adopt Constructive's agentic-db memory tables vs Exo's own diffs schema.
- [ ] Timescale via Supabase is license-restricted on shared tiers — the sovereign/self-host path is what unlocks it.

## Links
- [[emit_diff Chokepoint — Scale Without Slop]] — the write-door / scale doctrine this storage sits under
- [[Flow OS Desktop Shell — Tauri + Company Pulse Theater]] — UI that reads the diffs stream
- [[AI-as-Dev — Multi-Agent Orchestration]] — agent schema-drift guardrails pair with this
- [[AUM + BOMT — The Intelligence Compounding Vehicle]] — diffs as the moat this data feeds
- Root note: `AI.md`
