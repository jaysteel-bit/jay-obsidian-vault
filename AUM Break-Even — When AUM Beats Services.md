---
categories:
  - "[[Dumps]]"
project:
  - "[[Exo]]"
topic: AUM break-even — when does AUM revenue beat services revenue
type: dump
created: 2026-07-09
review_date:
tags:
  - brain-dump
  - aum
  - break-even
  - strategy
acted-on: true
compiled: 2026-08-05
attachments:
backlog: true
---

## Quick Thoughts

The core question: **what volume of decisions per month does a client need to produce for the AUM model to beat the services model?**

---

## The Services Model (baseline)

Pure services: trade hours for dollars. Fixed amount. Capped by what you charge. Doesn't compound — next month starts from zero.

**Per-client services revenue = (monthly fee) × (months engaged)**

## The AUM Model

Revenue = platform fee + (transactions × price) + (value-share % × proven savings). Transaction volume grows without more work. Value-share grows as predictions improve.

**Per-client AUM revenue = platform fee + (decisions/mo × price/decision) + (savings/mo × value-share %)**

## The Break-Even Formula

```
AUM revenue > services revenue (same client, same month)

platform fee + (decisions × price) + (savings × %) > services fee

Solve for decisions:

decisions > (services fee - platform fee - (savings × %)) / price per decision
```

## Concrete Example (hypothetical, structural — not real prices)

| Variable                             | Value      | Why                                            |
| ------------------------------------ | ---------- | ---------------------------------------------- |
| Services fee (pure consulting/mgmt)  | ~$5,000/mo | Opportunity cost — what you'd make the old way |
| Platform fee (AUM base subscription) | ~$1,500/mo | Covers infrastructure, Tier 1 + Tier 3         |
| Avg savings proven/mo (Tier 4)       | $8,000     | Supply chain or sales optimization             |
| Value-share %                        | 15%        | Of proven savings                              |
| Price per Tier 2 decision            | $0.50      | Per agent action                               |

**Value-share revenue = $8,000 × 15% = $1,200/mo**

```
decisions > ($5,000 - $1,500 - $1,200) / $0.50
decisions > $2,300 / $0.50
decisions > 4,600/month
```

**Break-even: ~4,600 Tier 2 agent actions per month.**

Below that → AUM earns less than services. Above that → AUM earns more, and the gap widens every month.

## Can the ICP Generate 4,600 Decisions/Month?

ICP: founder-led businesses, $2M–$15M ARR.

| Scenario | Decisions/Mo | Above Break-Even? |
|---|---|---|
| 1 namespace (sales only), low activity | 500–1,000 | ❌ No — AUM loses to services |
| 1 namespace (sales only), high activity | 1,500–3,000 | ❌ Close but no |
| 2 namespaces (sales + ops), moderate | 3,000–6,000 | ✅ Yes — AUM starts winning |
| 3 namespaces (sales + ops + finance), moderate | 6,000–15,000 | ✅ Yes — AUM dominates |
| 1 namespace, but high-value (supply chain) | 1,000–2,000 decisions, but $20k+/mo savings | ✅ Yes — value-share carries it |

## Two Paths to Beating Services

1. **Volume path:** 2+ namespaces instrumented, 5,000+ decisions/mo. Transaction fees carry the model. Works for ops-heavy clients.

2. **Value path:** Fewer decisions, but each touches big money. 1,000 decisions/mo but $20k/mo in proven savings. Value-share carries the model. Works for supply chain, procurement, sales pipeline clients.

**Best clients have both** — high volume AND high value. A $5M ARR agency with sales + ops + finance instrumented, each generating 3,000 decisions/mo at $0.50/decision + $15k/mo proven savings at 15% = $4,500 + $2,250 = $6,750/mo from one client. Already above a $5,000/mo services fee, and it grows.

## The Honest Answer

**A single namespace won't beat services.** You need either:
- 2+ namespaces per client (volume path), OR
- 1 high-value namespace where each decision touches real money (value path)

**For the ICP ($2M–$15M ARR):**
- Year 1 with 1 namespace: AUM revenue likely **below** services revenue. OK — capturing baseline data.
- Year 2 with 2–3 namespaces: AUM revenue **crosses above** services revenue. Compounding begins.
- Year 3+: AUM revenue **dominates**. Prediction improves, savings grow, value-share grows. Services revenue looks tiny by comparison.

**Strategic implication:** Year 1 clients on Path B (Hybrid Premium) — standard build/operate fees keep cash flowing while AUM base builds. Don't force Path C (pure value-share) in Year 1 — decision volume isn't there yet. Transition to Path C in Year 2 when namespaces expand and data justifies it.

---

## Key Insights

- Break-even ≈ **4,600 Tier 2 decisions/month** (at hypothetical pricing — the number changes with price, but the structure doesn't)
- **One namespace won't get there.** Need 2+ namespaces or 1 high-value namespace.
- Year 1: AUM revenue < services revenue. This is expected and fine — you're building the base.
- Year 2: the crossover. This is when the model proves itself.
- Year 3+: AUM dominates. The compounding flywheel is real but requires patience through Year 1.
- The model rewards **namespace expansion** — every new department wired = exponential decision growth, not linear.

---

## Action Items / Next Steps

- [ ] Pick first namespace to instrument — `sales:` recommended (closest to revenue, easiest to prove value)
- [ ] Model a real break-even with actual pricing once Path B pricing is confirmed
- [ ] Identify which ICP clients are most likely to have 2+ high-activity namespaces (target those first)
- [ ] Track decision volume from Day 1 of first client — this is the metric that tells you when to transition from Path B to Path C

---

## Notes

**Context:** This was modeled during the 2026-07-09 AUM brainstorming session. All numbers are structural/hypothetical — not real pricing. The formula is what matters, not the specific dollar amounts. Re-run with real pricing once confirmed.
