---
title: Confidential Computing + Sandboxing — the BOM/T Transfer Brain
created: 2026-08-08
updated: 2026-08-08
type: concept
tags: [architecture, security, delivery, infrastructure, database]
sources:
  - root: AI Conversation Regarding Build.md
confidence: medium
---

# Confidential Computing + Sandboxing — the BOM/T Transfer Brain

How to keep the AI "smart" (full data access) while guaranteeing a customer you can't see their data — and convert the **Transfer** phase of BOM/T from a revenue loss into a high-margin software license.

## The core dilemma

- **See data** → smarter AI, but high liability (GDPR/SOC2/HIPAA) and can't sell to regulated industries.
- **Never see data** → "dumb AI" with no learning loop.

**Confidential Computing (TEE)** resolves both: the AI runs inside a hardware-secured vault (AWS Nitro Enclaves, Intel SGX) where data decrypts *only inside* — the AI sees everything, but no human (you, the cloud, the OS admin) can peek. IP is protected too (model weights encrypted, only unlock in the vault).

## Sandboxing architecture — where the "brain" lives

| Mode | Sandbox location | Privacy | Capability | Cost | Best for |
|---|---|---|---|---|---|
| **Local Brain** | User's browser (WASM/JS) | High (data stays on device) | Limited by browser APIs | Low (user pays compute) | Simple tasks, high privacy (medical/legal) |
| **Remote Brain** | Your server (Docker/Firecracker VM) | Medium (data traverses your server) | Unlimited | High (you pay GPU) | Complex workflows, enterprise control |
| **Hybrid** | Split: Senses local, Reasoning remote | High (raw data local) | High | Mixed | **B2B SaaS winner** |

**Hybrid rule of thumb** — "Local Senses, Remote Reasoning":
- **Local:** data capture (voice/screen/keystrokes), sidebar Q&A, credential storage, zero-latency raw-privacy things.
- **Remote sandbox:** unpredictable code execution, complex planning, third-party API integration (server acts as security broker → audit logs).
- The extension is a **Secure Gateway**: local captures context → remote processes → local displays; destructive actions trigger Human-in-the-Loop confirmation.

## How this powers the BOM/T *Transfer* phase ("Golden Handcuffs")

The Transfer step stops being "hand over the code and lose the customer." Instead:

1. **Build & Operate (multi-tenant cloud):** fast iteration, full data visibility for model training. Standard security (SOC2).
2. **Transfer (Confidential BYOC):** package the AI "Brain" as a tethered, encrypted **Enclave Image (EIF)** the client runs in *their* AWS account. It's cryptographically tethered to your **Control Plane** — it "phones home" for license validation + latest model weights.
3. **The recurring hook:** if they stop paying, you stop sending weights/keys. The container becomes a useless brick. Revenue = **license fee + "brain update" fee**, and *they* pay the GPU bill.

**Control Plane (yours)** = billing, updates, orchestration, model weights — sees metadata only.  
**Data Plane (theirs)** = heavy models, raw recordings — lives in their VPC, their security team is happy.

## Model improvement without data access

- **Federated Learning + Differential Privacy:** devices upload *weight updates* (mathematical learnings), not raw data; DP noise prevents reverse-engineering.
- **Eyes-off training in the enclave:** model learns inside the vault and exports only gradients.

## Key decisions / open questions

- **Build modular now:** keep AI reasoning code separate from UI/database code (agent as a distinct microservice). You can add TEE later *only* if the brain is decoupled — adding it to a monolith is a re-packaging, not a toggle.
- **TEE reality check:** TEEs are intentionally hard — no network, no disk (RAM/CPU only), vsock proxy for I/O. TEE-capable = worth it for enterprise tier, not day-one.
- **OpenClaw / Moltworker:** OpenClaw = security red flag for B2B (universal file+internet+code access, shadow-IT reputation). **Moltworker** (Cloudflare's sandboxed OpenClaw) = the *blueprint*, not the product — single-user, no multi-tenancy; **fork the architecture** (Workers→Sandbox SDK wiring), strip OpenClaw to approved skills, later swap the brain for a LangGraph/CrewAI agent.

## Related

- [[AUM + BOMT — The Intelligence Compounding Vehicle]] — BOM/T delivery model; this is the Transfer-phase "sovereign transferable unit" mechanism.
- [[Exo-Ext — Flow OS Browser Extension]] — the local-senses/remote-reasoning split is exactly the Exo-Ext architecture.
- [[Reflex Arc Data Infrastructure — Sovereign Stack]] — sovereign stack + transfer-built path (Constructive+Timescale) connects to the transferable high-margin license.
