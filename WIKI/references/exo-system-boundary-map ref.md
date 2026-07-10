---
title: Exo System Boundary Map
created: 2026-07-10
updated: 2026-07-10
type: concept
tags: [exo, architecture, decision, flow-os, delivery]
sources:
  - "conversation:2026-07-10-vault-meta-leverage"
  - "agent-workspace/KNOWLEDGE-SYSTEM.md"
  - "agent-workspace/Exo Enterprise/Exo-Vaults/README.md"
  - "agent-workspace/Exo Enterprise/Exo-Vaults/Strategy/two-layer-execution-handoff.md"
  - "agent-workspace/Exo Enterprise/company-ssot/07-exo-delivery-os.md"
confidence: high
---

# Exo System Boundary Map

This page exists to prevent confusion between the four major systems: `agent-workspace`, Jay's Obsidian vault, client vaults, and Flow OS.

## The Clearest Boundary

| System | Question it answers | Primary role |
|---|---|---|
| `agent-workspace` | How does Exo-the-agent operate? | Agent operating system, skills, runtime rules, infra, execution memory, namespace-specific AI agents |
| `jay-obsidian-main` | What is Jay/Exo thinking, deciding, building, and learning? | Founder + company knowledge graph; the place where the business becomes legible and rich |
| Client vaults | What does this client's company know, do, own, and need? | Client-specific business brain, delivery record, SOPs, portal source, sovereignty artifact |
| Flow OS | What is happening right now, and what changed? | Live operational state, diffs, task queues, dashboards, metrics, agent run logs |

## Core Rule

The vault is where the business itself becomes legible and rich as a knowledge graph. It can contain company-SSOT-style knowledge, but it should not become the place where agent runtime state lives.

`agent-workspace` is for Exo AI's own operating system: the agent constitution, skills, memory-of-record, infrastructure state, and namespace-specific AI agents.

Flow OS is for live state and execution.

Client vaults are for client-owned durable context.

## What Not To Duplicate

Avoid copying the same truth into every layer. Each system needs a winning responsibility.

| Truth type                                                      | Winner                                                                  |
| --------------------------------------------------------------- | ----------------------------------------------------------------------- |
| Agent rules, skills, harness behavior, infra facts              | `agent-workspace`                                                       |
| Jay's raw thinking, company synthesis, business knowledge graph | `jay-obsidian-main`                                                     |
| Stable Exo operating/company decisions during current phase     | `agent-workspace/Exo Enterprise/` until authority is deliberately moved |
| Client-specific SOPs, configs, business context, deliverables   | Client vault                                                            |
| Realtime events, diffs, queue state, metrics                    | Flow OS                                                                 |

The vault can reference or compile from other systems, but compilation is not the same as authority. If an item is a legal, operational, or runtime source of truth, explicitly name the canonical owner.

## Flow OS Harness + Client Vaults

Client vaults can become the durable context layer for Flow OS harnesses.

This is similar to how an AI workspace has files like:
- `AGENTS.md`
- `MEMORY.md`
- `SOUL.md`
- `USER.md`
- `DESIGN.md`
- `BRAND.md`

A client vault could eventually include:

```text
client-[slug]-vault/
  AGENTS.md
  COMPANY.md
  USER.md
  BRAND.md
  MEMORY.md
  WORKFLOWS.md
  SOPs-configs/
  wiki/
  raw/
  deliverables/
```

Flow OS desktop app UI, terminal configs, and namespace-specific harnesses can read from these files to operate with client-specific context. The client vault becomes the company's constitution, memory, SOP layer, and durable operating map.

Flow OS should not freely mutate the whole vault. It should update through narrow API/MCP rails:
- emit live diffs into Flow OS first
- propose vault updates when live behavior changes durable knowledge
- write only approved/context-safe sections automatically
- preserve logs and source links so the vault remains trustworthy

## Exa / External Intelligence Role

Exa-like search/research tooling can plug into this architecture as a namespace-specific intelligence backend.

Possible roles:
- import web research into `WIKI/raw/`
- enrich company, competitor, market, ICP, or lead pages
- monitor external changes and propose updates
- feed Flow OS agents with current outside-world context
- support client-specific research namespaces

Boundary: external research should enter as raw source material or proposed updates first. It should not silently overwrite canonical decisions.

## The Bigger Picture

The four systems are not competitors. They form a layered operating system:

1. `agent-workspace` gives Exo-the-agent identity, tools, memory, and execution rules.
2. `jay-obsidian-main` makes Jay and Exo's thinking/business map legible.
3. Client vaults instantiate the same business-brain pattern for each client.
4. Flow OS turns the durable context into live operations and records what changes.

This is the meta-leverage model: one knowledge pattern improves founder clarity, internal company operations, client delivery, sales proof, and future software architecture.

## Related Pages

- [[Exo Vault Meta-Leverage System]]
- [[Four Ways to Scale a Service Business]]
- [[Exo Delivery OS (External Face) - First Draft]]
