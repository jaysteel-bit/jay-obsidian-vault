---
title: Flow OS Connector Taxonomy — Tier 1 unified / Tier 2 direct / SFTP
created: 2026-08-04
updated: 2026-08-04
type: concept
tags: [flow-os, architecture, delivery, exo, decision]
sources: ["Paycom Flow Integration— Seven Hills B2B Insight.md"]
confidence: medium
---

# Flow OS Connector Taxonomy — Tier 1 unified / Tier 2 direct / SFTP

> How Flow OS connects to third-party HRIS/payroll/ops backends without over-building. The stance: **never write a native connector to a closed ecosystem like Paycom; route through a unified API layer.** Compiled from the Seven Hills B2B insight note (Jul 2026).

## The Rule: Two Tiers + A Fallback

| Tier | Path | Example vendors | When to use |
|------|------|-----------------|-------------|
| **Tier 1 — Unified API** | Merge, Finch, Bindbee — one integration, many backends | Paycom, most legacy HRIS/payroll | Default. Client on a closed or long-tail platform. |
| **Tier 2 — Direct API** | First-party OAuth/app marketplace | BambooHR, Gusto, Rippling | Client on a modern platform with a real API |
| **Fallback — SFTP/File** | Scheduled file drops | Paycom holdouts, locked-down enterprises | When the client insists on staying on a closed platform |

## Why No "Native Paycom"

A native Paycom integration is a trap: a closed, slow-moving API with low leverage and high maintenance for a single client. One unified-API integration unlocks many backends at once — same engineering cost, far more addressable surface. You stay **platform-agnostic** and sell promises engineering can actually deliver.

## The Connector List Discipline

Every connector in the Flow OS list gets tagged by integration path — `Unified`, `Direct`, or `SFTP` — so nobody sells a native integration for a vendor that only exists behind a unified layer. The taxonomy prevents the build-order from promising what the connectors can't cleanly deliver.

## Status

- Stance is decision-grade for the Flow OS build order; not yet wired into a client-facing connector list.
- Open: build the tagged connector list (see `agent-workspace/state/tasks/flow-os-connector-taxonomy.md`).

## Related

- [[Flow OS Team Surface — humans + agents]] — the delivery surface connectors feed
- [[Exo System Boundary Map]] — which repo owns the connector code (Flow OS repo, not the vault or Reservoir)
