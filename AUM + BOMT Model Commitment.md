---
categories:
  - "[[Dumps]]"
project:
  - "[[Exo]]"
topic: AUM + BOMT Model — strategic commitment
type: dump
created: 2026-07-09
review_date:
tags:
  - brain-dump
  - aum
  - bomt
  - strategy
acted-on: true
compiled: 2026-08-05
attachments:
backlog: false
# synthesized into WIKI/concepts/aum-bomt-intelligence-compounding-vehicle.md (2026-08-05)
---

## Quick Thoughts

Full breakdown of the AUM + BOMT model — how difficult it is, whether it's worthwhile, what "instrumentation" really means, what counts as a "decision," and what a provable value-share saving looks like. This is the strategic commitment note — the model is confirmed as the vehicle.

---

## 1. How Difficult + Worthwhile Is the AUM + BOMT Model?

**Worthwhile: absolutely. One of the best vehicles for an entrepreneur who is also an aspiring investor.**

> *"You are effectively running a venture studio or private equity fund, but instead of buying equity with cash, you are buying operational data equity with software and labor."*

**Traditional PE:** deploy cash → buy equity → hope the team executes → exit in 5–7 years → 6–10% annual returns.

**AUM + BOMT:** deploy software + labor → capture operational data → data compounds into prediction engine → client can't leave without corporate amnesia → you retain data rights or runtime license → exit multiple times (Transfer fee + SaaS royalty + equity stake + anonymized global model weights).

### Why it's a better boat

| Dimension        | Traditional PE/VC             | AUM + BOMT                                                |
| ---------------- | ----------------------------- | --------------------------------------------------------- |
| Capital required | Millions per deal             | Software + labor (sweat)                                  |
| Dilution         | You give up cap table equity  | Non-dilutive — you keep 100%                              |
| Due diligence    | Months per deal               | The engagement IS the diligence                           |
| Risk             | Bet wrong → capital locked up | Bet wrong → you still learned from the diffs              |
| Return ceiling   | Capped by equity %            | Uncapped via value-share + runtime license + global model |
| Speed            | Months to deploy              | Days to deploy Flow OS                                    |
| Moat             | Capital (anyone can raise)    | Proprietary operational data (nobody can replicate)       |

**The BOMT wrapper is what makes it sellable.** Pure AUM (permanent lock-in) triggers enterprise fear. BOMT solves this: "We'll build your brain, run it, and hand you the keys — for a price." The client gets ownership eventually; you retain the data rights, the runtime license, or the anonymized model weights. Three Transfer structures from the AUM Reframe note:

- **Option A: "Intel Inside"** (strongest) — they own the content of the brain, but Flow OS remains the operating system required to run it
- **Option B: Anonymized Global Brain** — they get 100% of their system back; you retain perpetual license to anonymized, aggregated weights to train global models
- ~~**Option C: JV Spin-Out** — spin the operational unit into a new AI-native JV; you retain equity + AUM management fee~~ **KILLED 2026-08-06** — new entity, shared cap table, and governance overhead on every deal.
- **Option C (v2): Royalty + Distribution** — the department stays inside the client's own entity. No new entity, no cap table, no board seat. Exo retains a perpetual royalty on the department's throughput, plus passive non-voting equity only where the client offers it. Same yield as the JV, none of the corporate overhead.

**Difficulty: high, but not where you think.** The hard part isn't the business model. The hard part is the product (Flow OS instrumentation).

**For Jay specifically as entrepreneur + aspiring investor:** this model converts operational work into investable assets. Every X-Scale engagement can become:
- Cash flow (build fee + operate retainer)
- AUM (transaction + value-share revenue)
- Equity (Exo Ventures — equity-for-services)
- Data equity (the diffs table — anonymized global model weights)

You're building a portfolio of assets that compound, not just a consulting pipeline that resets every month.

---

## 2. The Instrumentation Question — What Is It Really, and How Hard Is It?

### What "instrumentation" actually means

Instrumentation = **wiring Flow OS into a client's existing systems so it can hear every state change, react to it, and log it as a diff.**

Concretely, for one client, it means:

1. **Database triggers** — Postgres triggers on the client's operational tables. When `leads.status` changes from `cold` to `qualified`, the trigger fires, calls `emit_diff()`, and Flow OS logs it.
2. **CDC (Change Data Capture)** — If the client has a database you can't add triggers to, you use CDC to stream row-level changes into Flow OS without touching their schema.
3. **Webhooks** — The client's existing tools (HubSpot, Stripe, internal APIs) fire webhooks at a FastAPI endpoint. Flow OS receives the payload, maps it to a diff, and logs it.
4. **API polling** — For systems that don't support webhooks or CDC, Flow OS polls their API on a schedule and diffs the state.

### How hard is it?

Plumbing, not rocket science. But fiddly, client-specific plumbing.

| Pattern | Difficulty | Why |
|---|---|---|
| Webhooks | Easy | Modern SaaS tools fire them natively. One FastAPI endpoint per tool. |
| API polling | Easy-Medium | Write a connector, diff against last state. Time-consuming per tool, not hard. |
| CDC | Medium | Needs access to client's DB write-ahead log. Some clients won't have this. |
| DB triggers | Medium | Requires write access to client's Postgres + DBA cooperation. |

**The real difficulty isn't any single integration. It's the volume.** Each client uses 5–15 tools. Each needs a connector. Each needs maintenance when APIs change.

### Can agents speed this up?

**Partially.**

Agents CAN: auto-generate connectors from API docs, auto-discover state changes from DB schemas, map tool events to your diff vocabulary, and test instrumentation. All with human review.

Agents CAN'T: get the client to grant database access (trust/sales conversation), handle custom internal tools with no API docs (human must reverse-engineer), navigate client IT politics (approvals, whitelisting, DBA cooperation), or decide which state changes are meaningful "decisions" vs noise (business judgment).

> **Jay's note:** SOP documentation needs to be a constant, not an afterthought. Perfect bridge to EXA (Exo Academy Namespace — NotebookLM-inspired department).

**Google's managed agents / Gemini agent builders** — useful as a speed tool for writing connectors faster, but don't solve the core problem (access + judgment).

**Constructive's pgpm + agentic-db** — the real leverage point. Package your diffs schema + Reflex Arc + `emit_diff()` as one pgpm module → deploy into any client's Postgres in minutes. Auto-generated APIs, RLS baked in, version-controlled.

**BUT theoretical only.** CURRENT-STATE.md confirms `emit_diff()` doesn't exist as a working chokepoint yet — the error service writes directly to the diffs table. No foundation to package yet.

### The honest timeline

**First 2–3 clients: tough.** 2–4 weeks of manual instrumentation per client. Custom connectors, learning edge cases, no templates yet.

**Client 3–5 onward: dramatically easier.** You'll have a connector library, templated checklist, pgpm package working, and an agent auto-generating 70% of new client connectors.

**Key insight:** instrumentation is a **one-time cost per client that produces recurring revenue forever.** Upfront friction is the price of the AUM model. It's plumbing, not deep tech — you need a delivery playbook, not a research team.

---

## 3. What Counts as a "Decision" — Best Setup for Cashflow

Four-tier framework from the AUM Reframe note:

| Tier | What It Is | Example | Who Creates It | Volume | Value |
|---|---|---|---|---|---|
| **Tier 1: System Triggers** | Passive state changes from DB/webhook | `lead.status: cold → qualified` | Client's existing systems | High (thousands/day) | Foundation — proves Flow OS is watching |
| **Tier 2: Agent Actions** | Autonomous actions by Flow OS agents | Agent reroutes a shipment, auto-assigns a lead | Flow OS Reflex Arc | Medium (hundreds/day) | Operational velocity — what the client pays for |
| **Tier 3: Human Whys** | Human approves/overrides an agent action with a reason | Manager rejects vendor switch, says "wrong champion" | Client's team | Low (tens/day) | The moat — proprietary data that trains prediction engine |
| **Tier 4: Predictions** | Flow OS generates a forecast from diff history | "This deal closes in 14 days based on 200 patterns" | Prediction engine | Low (few/day) | Value-share proof — what you charge a percentage of |

### Which setup makes the most cashflow?

All four tiers running, priced differently:

| Tier | Pricing Mechanism | Why |
|---|---|---|
| Tier 1 (Triggers) | Bundled — don't price separately | Infrastructure. Client shouldn't feel like they're paying per database row. |
| Tier 2 (Agent Actions) | Transaction fee per action | Where volume lives. Every autonomous action = one billable unit. |
| Tier 3 (Human Whys) | Bundled into platform fee | Don't charge for human input — you WANT annotations. This data is your moat, not a revenue line. |
| Tier 4 (Predictions) | Value-share — % of proven impact | Uncapped upside. "We predicted the supply chain break 6 days early. Saved $40k. Our 20% = $8k." |

**The cashflow-maximizing setup:**

```
Monthly platform fee (covers Tier 1 + Tier 3 + infrastructure)
  + Transaction fee × Tier 2 volume (agent actions)
  + Value-share % × Tier 4 impact (predictions that saved money)
```

**Why this is best:** Platform fee covers base costs (predictable). Transaction fee scales with volume (client grows → you grow). Value-share captures upside (uncapped). Human whys are free (maximizes data moat).

**The definition that drives revenue:** A "decision" = **a Tier 2 agent action or a Tier 4 prediction with provable financial impact.** Tier 1 triggers and Tier 3 annotations are infrastructure, not billable units.

---

## 4. What a "Value-Share Provable Saving" Looks Like

A provable saving is a **Tier 4 prediction or Tier 2 agent action where you can draw a straight line from Flow OS's action to a dollar amount, with an audit trail the client's CFO can't argue with.**

### Example 1: Supply Chain (High Value)

**Before:** Procurement team manually monitors shipments. Finds out about delays 3 days late. Loses $40k in idle factory labor.

**After Flow OS:**
- Day 1: Instruments procurement database + supplier API
- Day 14: Predicts "Supplier A shipment will delay by 4 days" (Tier 4)
- Day 14: Auto-drafts reroute to Supplier B with cost comparison (Tier 2)
- Day 14: Manager approves — "Supplier B is 5% more expensive but prevents shutdown" (Tier 3)
- Day 18: Original shipment would have arrived late. Flow OS reroute arrived on time.

**Audit trail:**

| Diff | Event | Value Before | Value After | Why Annotation |
|---|---|---|---|---|
| #4521 | `prediction=shipment_delay` | `supplier: A, ETA: Day 18` | `predicted_delay: 4 days` | Pattern matched from 200 historical diffs |
| #4522 | `action=reroute_supplier` | `supplier: A` | `supplier: B` | 5% higher cost, prevents $40k shutdown loss |
| #4523 | `human_approval=reroute` | `status: pending` | `status: approved` | "Correct — Supplier B prevents shutdown" |

**Value-share claim:** "Flow OS predicted the delay 4 days early and auto-routed to Supplier B. Without it, you would have lost $40k in idle labor. Our 20% = $8k."

**Why the CFO can't argue:** Prediction was made BEFORE the delay (diff timestamp). Reroute was approved by their own manager. Cost of alternative is documented. Avoided loss is calculable.

### Example 2: Sales Pipeline (Medium Value, High Volume)

**Before:** Sales team manually qualifies leads. 15% close rate. Deals that close take 45 days. Deals that won't close waste 30 days of SDR time.

**After Flow OS:**
- Instruments CRM (HubSpot/Salesforce)
- After 90 days of baseline, learns: "Leads from source X with company size Y that reach 'demo' within 7 days close at 42% in 14 days"
- Auto-tags new leads with predicted close probability + days-to-close
- SDR team focuses only on high-probability leads

**Audit trail:**

| Diff | Event | Value Before | Value After | Why Annotation |
|---|---|---|---|---|
| #8921 | `prediction=deal_close_probability` | `lead: ABC, stage: demo` | `probability: 42%, days: 14` | Trained on 1,200 historical diffs |
| #8922 | `prediction=deal_close_probability` | `lead: XYZ, stage: demo` | `probability: 8%, days: N/A` | Trained on 1,200 historical diffs |
| #8923 | `action=priority_reassign` | `lead: ABC, priority: normal` | `priority: high` | Auto-promoted based on 42% prediction |

**Value-share claim:** "Flow OS identified 12 leads with >40% close probability. Your team closed 5 in 14 days instead of 45. That's $150k in accelerated revenue + 120 hours of SDR time saved. Our 15% = $24.3k."

### What makes a saving "advantageous to Exo"

| Characteristic | Why It Favors Exo |
|---|---|
| Predictive, not reactive | Flow OS predicted before it happened. Client can't say "we would have caught it" — diff timestamp proves otherwise. |
| Audit trail from Day 1 | Baseline captured before Flow OS did anything. "Before" state is undeniable. |
| Client's own manager approved | Human "why" annotation = client's team validated the decision. Can't claim Flow OS forced a bad call. |
| Dollar amount is calculable | Cost = exact labor cost × hours. No "we think it saved about..." — it's "$40,000 in idle labor at $500/hr × 80 hours." |
| Prediction improves over time | Month 1: saves $8k. Month 6: $15k. Month 12: $25k. Value-share grows without doing anything new. AUM compounds. |

---

## 5. Data Custody / Regulated Industries (Side-Quest)

Found in `Exo Enterprise/strategy-notes/strategic-notes-holdco-ev-nfc.md`, point 6:

> *"Flow OS's 'immutable diffs' architecture + 'why annotations' is exactly what enterprise compliance teams are going to be mandated to implement as AI regulation increases. Healthcare, financial services, legal — all in your ICP — are going to face regulatory pressure to audit their AI systems. Most have zero infrastructure for this. Flow OS solves this as a byproduct of how it was designed."*

This is the **Data Custody Premium** from the AUM Reframe note. Flow OS's diffs table IS a compliance audit trail by design. You didn't build it for compliance — you built it for intelligence. But in regulated industries (healthcare, finance, legal), the fact that every AI decision is logged with a "why" annotation is exactly what regulators will require. Charge a premium for this — it's a byproduct, not a feature you have to build.

---

## Key Insights

- **AUM + BOMT is the confirmed vehicle.** Not pure consulting, not pure SaaS. Asset management framing with BOMT delivery.
- **The #1 constraint is Flow OS instrumentation** — not the business model, not the pricing. If the diffs engine isn't capturing real state changes from real client systems, none of the AUM math works.
- **A "decision" = Tier 2 agent action or Tier 4 prediction with provable financial impact.** Tier 1 and Tier 3 are infrastructure, not billable units.
- **Value-share is the uncapped upside.** The audit trail makes it irrefutable. The prediction improves over time. AUM compounds without new work.
- **Instrumentation is plumbing, not deep tech.** First 2–3 clients: tough (2–4 weeks each). Client 3–5 onward: dramatically easier (connector library + pgpm package + agent auto-generation).
- **Data Custody Premium** — Flow OS's diffs table is a compliance audit trail by design. Regulated industries (healthcare, finance, legal) will pay a premium for this as AI regulation increases.

---

## Action Items / Next Steps

- [ ] Define the break-even point: how many Tier 2 decisions/month does a client need for AUM revenue to exceed pure services revenue?
- [ ] Build `emit_diff()` as the single chokepoint — without it, no AUM foundation exists
- [ ] Pick the first namespace to instrument (recommend `sales:` — closest to revenue, easiest to prove value)
- [ ] Prototype the Reflex Arc using Google managed agents (weekend test — SENSE → REACT → REMEMBER loop)
- [ ] Structure the Transfer clause: confirm "Intel Inside" model as default (they own the content, Flow OS remains the runtime)
- [ ] Update company docs to reflect AUM + BOMT as the committed model (see task: `aum-model-migration`)

---

## Notes

**WORKFLOW:** This is a capture zone for business thoughts and tangents. When an idea hits, create a new dump note. Review periodically (weekly recommended) to extract insights into Projects, Ideas, or Admin tasks. Once reviewed, update `review_date` and archive by moving to a completed state.
