---
tags:
  - system
  - flow-os
  - milestone
  - diff-write-contract
created: 2026-07-14
type: milestone
project:
  - "[[Exo]]"
---

# Flow OS Diff Write Contract — Parts A + B COMPLETE (2026-07-14)

> The foundation the entire Exo thesis rests on — clean diffs at one door, reflexes reacting in real time, agent escalations queuing and resolving — is now live 24/7 on the Contabo VPS. Parts A (Diff Write Contract), B.1 (Arc), B.2 (Rules), B.3 (Hermes Handoff), and B.4 (24/7 Deploy) are all done.

## What's Live

| Component | Status | Location |
|---|---|---|
| **Supabase project** | `jdjyiyeddpfzpgrqffav` (free tier, us-east-1) | hosted Supabase |
| **emit_diff() RPC** | SECURITY DEFINER, vocabulary-validated, RLS on client_id | Supabase |
| **Client Zero** | `e0000000-0000-4000-8000-000000000001` (fixed UUID) | DB |
| **Vocabulary** | ops 10 (1 retired) + sales 5 + brand 8 = 23 events | `vocabulary` table |
| **Tables** | diffs, annotations, rules, rule_executions, agent_escalations, workflows, tasks, clients, vocabulary | 8 tables, 5+ indexes |
| **Reflex Arc** | FastAPI, async Supabase client, realtime on diffs, 5 rules | `flow-os/backend/main.py` |
| **Escalation Worker** | Polls agent_escalations every 5s, processes, writes back via emit_diff() | `flow-os/backend/worker.py` |
| **Systemd services** | flow-os-arc + flow-os-worker, Restart=always, Linger=yes | `~/.config/systemd/user/` |
| **Docker** | Dockerfile + docker-compose.yml ready for Hetzner migration | `flow-os/` |
| **Migrations** | 6 versioned SQL files | `flow-os/supabase/migrations/` |

## Verified End-to-End

```
Diff #17: task=completed (status=failed)
    ↓ Arc detects via realtime (~1s)
    ↓ Rule "Failed Task Escalation" matches (action=agent_handle)
    ↓ Loop guard: metadata.escalated_to_hermes=true
    ↓ Escalation queued in agent_escalations
    ↓ Worker polls → processes → emits result
Diff #18: task=escalated_handled (~5s total)
    ↓ Arc picks up #18 → no rule match (different event) → no loop ✅
```

Restart resilience confirmed: `systemctl --user restart` → both services come back automatically, arc reconnects to realtime, worker resumes polling.

## What's Next

- **B.3 v0.2:** Replace deterministic handler with real Hermes reasoning (LLM calls)
- **C.2–C.4:** Wire a second real workflow → add reflex rules → run a week → verify data is model-trustworthy
- **Hetzner migration:** When ready, `git clone + docker compose up -d` on the new box
- **Token rotation:** When stable — rotate Supabase access token, DB password, service key

## Related

- [[aum-bomt-intelligence-compounding-vehicle]] §22 — the executor loop this backend unblocks
- [[Exo System Boundary Map]] — where Flow OS sits in the architecture
