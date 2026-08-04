---
categories:
  - "[[Dumps]]"
type: research
topic: flow-os-connectors
created: 2026-07-20
tags:
  - flow-os
acted-on: true
compiled: 2026-08-04
backlog: |
  - [ ] Build the Flow OS connector list tagged by integration path (Unified / Direct / SFTP)
  - [ ] Client-facing explainer for why no native Paycom connector
vault-context: business
---

Short answer: Don't build a native Paycom connector. The research is right—it's a trap.

Your Flow OS "connector" concept should have two tiers from day one:

- Tier 1 (Unified APIs): Merge, Finch, Bindbee. One integration, many HRIS/payroll backends. This is where Paycom lives for you.

- Tier 2 (Direct APIs): Reserved for clients using modern platforms (BambooHR, Gusto, Rippling) that do have OAuth/app marketplaces.

For this specific client: Let them know we're platform-agnostic. We ingest via the unified layer, not direct Paycom API. If they must stay on Paycom, SFTP drops are the pragmatic fallback.

Action item: When you build that connector list, tag each by integration path—Unified API, Direct OAuth, or SFTP/File—and note which vendors fall into which bucket. Prevents selling something engineering can't deliver cleanly.

Want me to draft the connector taxonomy or a client-facing explainer for why we don't do "native Paycom"?
