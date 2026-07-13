---
tags:
  - system
  - agent-handoff
  - flow-os
  - backend
created: 2026-07-13
type: handoff
next-session-focus: Diff Write Contract B.3 (Hermes agent_handle) + B.4 (24/7 VPS deploy)
project:
  - "[[Exo]]"
---

# Handoff — Flow OS Backend: Diff Write Contract A + B.1/B.2 LIVE (2026-07-13)

> For the next agent picking up Flow OS backend work. The foundation the whole
> Exo thesis rests on — clean diffs at one door, reflexes reacting in real time —
> went live this session. Full session record: `agent-workspace/log/2026-07-13-session-diff-write-contract.md`.

## What is now true (verified, not aspirational)

- **Supabase project `jdjyiyeddpfzpgrqffav`** (us-east-1, free tier) is the live data layer. The old project (`rvbzkfnxunfdtxrqkjbx`) was deleted by Supabase after a 90-day pause; the Dec-2025 backup was deliberately NOT restored (it held the error-handling-detour schema). Fresh schema from versioned migrations.
- **`emit_diff()` is the one door.** SECURITY DEFINER RPC; validates against the in-DB `vocabulary` table (rejects unknown events, retired events like `handoff=updated`, unregistered clients). Direct INSERT on `diffs` is revoked for client roles. RLS on `client_id`.
- **Client zero = Exo** — `e0000000-0000-4000-8000-000000000001` (fixed UUID, all internal emitters use it). The zero-UUID stub era is over.
- **Reflex Arc v1 runs** — FastAPI at `flow-os/backend/` (run instructions in its README). SENSE (realtime on diffs) → REACT (deterministic rules, no LLM) → REMEMBER (`rule_executions`). Verified ~1s end-to-end; 3 live ops rules.
- **The workspace chokepoint (`agent-workspace/build/emit-diff.ps1`) writes to the DB** — jsonl only as marked fallback. 7 historical jsonl rows backfilled. 14 diffs in the moat as of session close.
- Vocabulary: ops 10 (1 retired) + sales 5 + brand 8 — mirrored in `diff-vocabulary.md` (LAW file) and the `vocabulary` table.

## Where things live

| Thing                                      | Path                                                                                                                      |
| ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------- |
| Task spec (B.3/B.4 unchecked)              | `agent-workspace/state/tasks/diff-write-contract.md`                                                                      |
| Migrations (4, versioned)                  | `flow-os/supabase/migrations/`                                                                                            |
| Reflex Arc + run instructions              | `flow-os/backend/` (`main.py`, `README.md`)                                                                               |
| Chokepoint caller                          | `agent-workspace/build/emit-diff.ps1`                                                                                     |
| Live-state summary                         | `agent-workspace/state/infra.md` → "Flow OS Data Layer"                                                                   |
| Superseded-state notes                     | `CURRENT-STATE.md` (2026-07-13 update block at top) — update current-state.md to reflect the current state since 07-13-26 |
| Credentials (git-ignored, NOT in chat/git) | `agent-workspace/.env.supabase`, `flow-os/backend/.env`, `flow-os/.env.local`                                             |

## Next session (B.3 + B.4)

1. **B.3 — Hermes hand-off:** add an `agent_handle` action to the arc — escalation path where Hermes reasons, acts, and writes results back via `emit_diff()`. Arc v1 actions deliberately emit NO diffs; loop-guards must land with this (an action that emits a diff that triggers the action = infinite loop).
2. **B.4 — 24/7 deploy:** Docker `restart: always` on the Contabo VPS (147.93.181.36) -OR- **Hetzner** so the arc survives reboots and loses zero diffs. Until then the arc only runs when started manually, which should be dealt with soon.

## Open cautions

- Free tier auto-pauses after ~7 idle days. Session-close emits are the heartbeat; jsonl fallback catches gaps; the sovereign Hetzner stack (already locked as roadmap) is the permanent fix.
- The Flow OS TypeScript error-handling engine still inserts into `diffs` directly — now blocked by the revoke. Reconcile it to `emit_diff()` when rewiring the UI to the new project.
- Jay: rotate the Supabase access token (it touched chat this session), then update `.env.supabase`.
- A `db_cluster-16-12-2025@…backup.gz` sits at the agent-workspace root — move it out (`.gz` is not git-ignored).

## Suggested skills (next agent)

- `handoff` (workspace `SKILLS/handoff/`) — session-close ritual; emit diffs through the new chokepoint.
- `limiting-factor` — if unsure whether B.3/B.4 or selling is the right next move, run the constraint check first.
- `diagnosing-bugs` — if the realtime subscription or RPC misbehaves during B.3.

## Related

- [[Exo System Boundary Map]] · [[Exo Vault Meta-Leverage System]]
- `aum-bomt-intelligence-compounding-vehicle` §22 — the executor loop this backend unblocks (diffs `metadata` + `actor` columns were designed for it).
