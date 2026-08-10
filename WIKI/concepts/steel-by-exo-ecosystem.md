---
title: Steel by Exo — Identity Ecosystem
created: 2026-08-05
updated: 2026-08-09
type: concept
tags: [steel, offer, positioning, roadmap, product]
sources: ["Steel by Exo Ecosystem.md", "Steel Share Feature Thoughts.md", "Steel Global 03-07.md", "Steel Prevents Fraud.md"]
confidence: high
---

# Steel by Exo — Identity Ecosystem

> Crystallized from root note `Steel by Exo Ecosystem.md` (2026-08-05). Consumer-facing sub-brand of Exo Enterprise: a **premium identity ecosystem** built around physical NFC artifacts + digital identity. Exo builds the engine; Steel is the luxury identity product line. Part of the holdco identity/passport / CAC layer.

## Locked sentence
**Steel is not a tech startup — it's a premium identity brand.** The card is the acquisition event; the profile and membership are the retention moat; the Linktree disruption (steel.id) is the entry wedge, not a side feature.

## The v0.1 chain
*Steel Card (digital-first / physical-later) → Steel Profile → Steel Global Citizenship → World Participation*

## Product lines (confirmed)
| Product | Role | Status |
|---|---|---|
| **Steel Card** | NFC metal card, digital version first; invitation/application-only; no visible numbers/chips/stripes; dynamic tokens, AES-128/256; 304 stainless gunmetal. First-10k waitlist, Q4 2026 target. | Spec'd to chip/manufacturing detail |
| **Steel App** | Mobile-first identity; card within; NFC tap-to-share/network, steel.id link, analytics, context-aware profile modes (Professional/Creative/Network/Public). Future: product-NFC taps surface rarity/brand culture. | High-leverage, leverage here |
| **Steel Profile (steel.id)** | Verified digital identity / Linktree killer for creators, founders, professionals. Differentiated by verified-membership weight + NFC bridge + Steel Global integration. | Core wedge |
| **Steel for Teams** | Enterprise / agency tier (B2B adjacent). | — |
| **Steel Bracelet/Wearables** | Modular NFC wearable, Phase 2+; flagship Veblen item. **Deferred — card-first.** | Deferred |
| Steel Ecomm | Streetwear / Veblen goods. | Underdeveloped |

**Brand tiers:** Steel (standard) → Steel+ (premium) → Steel++ (luxury/Veblen flagship, anchors prestige). *(Note flags this as brainstorming, not locked.)*

**Revenue model (not finalized):** DTC physical, digital subscription (App/steel.id premium), Steel Global membership, B2B licensing.

## Steel Global — the community/culture layer
\"Curating the unimaginable.\" Polymathic membership universe where each **World** is a vertical (Business, Fashion, Culture, AI, Cinema, Photography, Design, Futurism, Venture) with its own editorial voice + community. Site: steelglobal.us (live, early; Business World only). The Foundry: steelglobal.us/foundry.

- **Worlds** — curated editorial + community, taste is the filter (not feeds).
- **Steel Citizenship** — earned tier system (Member → Contributor → Featured → Editor). Earned, not purchased.
- **Steel Tag** — attribution tied to Steel Profile, not social handle; reputation on verified identity not follower count.

---

## Steel App — UI / NFC spec (Appendix 2026-08-10)
> From root note `Steel App Prompt.md`. Implementation-facing spec for the Steel App mobile surface. Core requirement: **NFC must be real hardware function, not just UI.**

- **NFC foundation**: real NDEF tags / CoreNFC settings up-front, not mock. (Apple: developer.apple.com/documentation/corenfc.) Unlocked foundation before UI polish.
- **Recent Connections slide gesture**: per-connection slide brings profile pic to far right, descriptions collapse, reveals 3 action buttons:
  1. ⋯ (three-dot) → per-connection settings (trash, settings, etc.)
  2. Hide (collapse/hide recent connection)
  3. 💬 chat-icon → opens the **AI** section (context-aware assistant per connection)
- **Trust icon**: new icon in the bottom nav (between Venues and Events) — gold coin icon for "Trust".
- **Card disabled state**: red shield icon replaces green active button.
- **Bug**: gold shadow not visible on mobile in active state (fine on desktop) — must render on mobile.
- **Deferred/next**: AI section behavior TBD (will be explained); follow-up files to attach for CoreNFC context.
- **Content 3-layer** — Steel Editorial (owned, Quartr-style) / Member Content (community) / Curated Embeds (best of internet framed in Steel context).
- **B2B adjacent** — World Sponsorship (brand-sponsor world editorial, not banner ads); Steel Ventures (investment/operator arm; concept stage).

**Legal/structure:** Steel Global is a **Private Membership Association (PMA)** — not public accommodation, not licensed entity, operates under common-law rights. Charter generated 2026-05-16. Jay Steel sole founder, super-voting rights. Two-class membership: Board Members (governance) + Associate Members (benefits, no votes).

**Growth flywheel:** world-first content → audience discovers universe → Steel Card real-world viral loop → visible membership creates aspiration → waitlist grows → new members create more world content.

## Open decisions (parked, all same uncertainty level)
- Full Steel++ flagship product portfolio
- Revenue model + downsell structure
- Launch sequencing (Card → App → Global → physical — confirm order)
- Marketing / channel strategy (essentially blank)
- Distribution (DTC only / boutique / invitation-only)
- Membership pricing
- Editorial team / World editor recruitment

## Links
- [[AUM + BOMT — The Intelligence Compounding Vehicle]] (holdco identity/passport / CAC layer role)
- [[Post-AI Pricing Architecture]]
- Root note: `Steel by Exo Ecosystem.md` · related Steel captures: `steel concepts.md`, `Steel Global 03-07.md`

## Open
- [ ] Confirm launch sequencing card-first (Card → App → Global)
- [ ] Resolve Steel++ flagship item list + downsell
- [ ] Membership pricing + distribution model

## Appendix — 2026-08-06 (NFC Anti-Counterfeit Defense)
*Crystallized from `steel concepts.md` (root note). Directly supports the Steel Card's physical NFC authenticity claims (AES-128/256, tamper-evident).*

**Why NFC beats QR for authenticity:** QR codes are photocopyable; NFC chips carry a globally-unique, non-clonable UID. Chip not copyable; server decides legitimacy.

**Five anti-counterfeit mechanisms (with loophole fixes):**
1. **Secure-element hardware (NTAG 424 DNA)** — AES-128/ECC keys; dynamic one-time auth code per tap kills replay attacks (a cloned static copy of a prior scan is rejected).
2. **Server-side validation** — move source of truth off the tag to a private cloud DB. Manufacturer gets limited/scratch keys; Exo holds master keys on home server. Counterfeiters can't reach final auth logic.
3. **Anti-overproduction / "ghost shifts"** — whitelist authorized UIDs in DB pre-production; replica UID fails. "First Tap" rule: if a "new" unit scans as already-activated in another city → flag as suspected fake/stolen.
4. **Digital passport (blockchain or in-house ledger)** — immutable chain of custody: Created → Shipped → Sold. Unit not "Released" in ledger reads as unauthorized.
5. **Physical security** — tamper-evident VOID tags; embed chip inside lining/material so removal destroys the item (can't reuse genuine packaging).

**Industry analogs:** luxury fashion (bags/shoes/jewelry), wine & spirits (tamper-evident caps), pharmaceuticals (pkg integrity), sports gear (resale protection).

**Steel relevance:** this is the technical backbone behind the Steel Card's anti-counterfeit claim — worth wiring into Steel Card spec/marketing as proof-of-defense, not just stated AES-128.

## Appendix — 2026-08-08 (Dynamic Profiles)
*From `Dynamic Digital Steel Card.md` (root). Small UX feature candidate, rated 10/10 by Jay.*

**Dynamic Profiles:** the digital card is not static. Via the **Steel Global dashboard**, the user updates links/portfolio/"World" affiliations in real-time; changes reflect instantly on the next NFC tap. Turns the card from a fixed business card into a live identity surface — pairs naturally with the steel.id profile (the moat) and the Steel Global earn tiers.

## Appendix — 2026-08-09 (Referral Virality + Citizen/Visitor Distinction)
*From `Steel Share Feature Thoughts.md` + `Steel Global 03-07.md` (root dumps). Growth mechanics + positioning sharpening, both genuinely-new.*

**Onboarding virality (`Steel Share Feature Thoughts.md`):**
- In the first 3–5 onboarding clicks, user shares profile externally (messages/social) and gets **$5–$10 credited "on us"** — spendable at partner locations or as Steel Credit for Steel products. Deliberate PayPal-style referral bacteria / exponential replication.
- Flagged risk: if it scales, virality introduces its own class of problems (abuse/gaming) — parked for "when we get there."
- **Partner angle:** charge partners for access to the customer base ($99 / $105–110 / $500+ tiers) — a separate partner onboarding fee, likely competing with/or over the referral cost. Could be an upsell later; not yet decided.
- **Membership stance:** do NOT charge basic members — "anyone can join" Facebook-style for the basic SHARE use case; the physical Steel Card (future) carries a **verified badge** as its differentiation.

**Positioning sharpening (`Steel Global 03-07.md`) — the "Visitor Pass vs Diplomatic Passport" move:**
- Solves the **Discovery vs Depth** tension. Treat Steel Global as urban-planning infrastructure, not a feed.
- **Cross-World metadata:** in the Business world, subtly surface how Steel Cinema aesthetics shape branding — the value is the *bridge* between worlds, not the worlds themselves.
- **Contribution Ledger:** a cross-pollination badge — citizen's business insight helping a Cinema creator gets recorded on the Steel Card as polymathic-influence proof.
- **Free Profile = Visitor Pass, Citizen Profile = Diplomatic Passport:** free users get links; Citizens get "World" integration (showing *which* Worlds they inhabit/influence) — counters Linktree-style brand dilution.
- **Dynamic permissioning (the disruptor vs Linktree):** profile changes by context/time — tap at a business conference → LinkedIn/portfolio prominent; tap at a film screening → Cinema contributions/Instagram top. Plus a **Live Feed of Activity** across the Steel Universe instead of a dead link list ("I just published a critique in the Cinema World", not "I have a Twitter").
- **Sustainability risk (closed-universe echo chamber):** needs a constant flow of high-quality "missions"/collaborative projects to keep Citizens engaged.

## Appendix — 2026-08-09 (Anti-Fraud Deposit Gate)
*From `Steel Prevents Fraud.md` (root dump). Steel app onboarding anti-abuse design — genuinely new, not yet synthesized elsewhere.*

**Deposit-to-unlock fraud gate:**
- To use Steel features, user deposits an amount to their account; **85% reimbursed** directly back to the original payment method, **15% held on the Steel card** (redeemable/sendable at any time). One-time.
- Purpose: authenticates real human vs robot/bad actor — a proof-of-personhood mechanism, not a fee.
- **Free baseline preserved:** ~90% of the Steel app remains usable for free without the gate; the deposit unlocks 100% of features.
- **Open question (flagged):** is the retained 15% a genuine staking/float mechanism or a disguised cost to users? Ratio rationale unconfirmed.
