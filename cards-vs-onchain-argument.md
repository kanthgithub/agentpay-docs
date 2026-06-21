

## Provisional take on cards (subject to the deep-research findings)

The "every agent is going card mode" observation is half-right and half-misleading. Half-right: in 2026 the card rail is the easiest distribution surface, so every well-funded competitor adds cards as soon as they have BIN-sponsor capital. Half-misleading: that's not because cards = PMF — it's because card volume is the only metric a 2026 fintech investor recognises. Card-issuing is investor-driven, not user-driven.

That distinction matters because of your two-stage pitch path:

**Stage 1 — partner pitch to Etherspot / ZeroDev / Pimlico** These guys make money from UserOps. They want products that drive UserOp volume on their stacks. Cards do not run on AA — card auths live entirely off-chain (issuer webhook → Lithic ASA → Visa). So a card-included pitch tells Etherspot: "by the way, half our payments will skip your validators." For partner pitch, less cards = better fit. AgentPay's leverage is "we'll route enterprise agent UserOps through your stack — help us land the first 10 design partners." Cards don't help that pitch.

**Stage 2 — investor pitch (post-beta, post-userbase)** Here cards are a hedge against weak x402 merchant adoption. But your competitor doc already calls this trap: "if you do what KleePay does, you become KleePay-with-extra-steps." The Quadrant III lane (self-custodial × on-chain) is the only place where AgentPay isn't fungible with the next better-funded competitor. Going Cards-First (Option D) or Cards-Phase-1.x (Option C) abandons Quadrant III for nothing in return — Quadrant I has Lithic, Stripe, Rain, KleePay, Sponge, Crossmint, Mastercard AP4M, Visa IC, Catena Labs, Marqeta, Highnote, Brex, Ramp, Mercury, Privacy.com, and Bilt all ahead of you with more capital and more partners.

**My honest provisional lean is Option B** — Phase 2 secondary rail, ship v1 + v1.1 crypto-only, ship cards in months 4–6 as a coverage extension once we have 6 months of x402 data. With one explicit hard trigger that 05-roadmap.md doesn't currently have: "add cards if x402 monthly active merchants drops below X by month 4." That makes the card-add a data decision, not an anxiety decision.

**But: the research agent has to prove or disprove three things before I'd lock this:**

Did Skyfire (no cards initially) grow slower than Crossmint (cards from day 1)?
Did adding cards correlate with user-count spikes at Stripe Agent Toolkit, Crossmint, Catena Labs?
Are pure-Quadrant-III players (Lit/Vincent, Catena Labs pre-cards) growing or stalling?
If the data shows Quadrant III is dead, Option B is too aggressive and we revisit. If it shows Q-III players are growing, Option B locks. I'll come back to Q1 with the data once it lands.

## What we can lock right now (independent of cards)
The USP question is foundational AND independent of the card decision — every other choice (BIN sponsor, KYC scope, hero copy, partner pitch) flows from "who are we and what do we sell." It also feeds straight into your Stage 1 partner pitch, which you said is happening soon. So let me ask Q8 first, then we'll pick up the v1 crypto-core questions (Q3 AA stack, Q4 MPP timing, Q5 MCP transport) while research runs.
What's the one-line USP we commit to in v1 docs, partner pitch, and (post-beta) investor pitch? Pick the framing that best maps to the customer you actually want — different framings imply different ICPs, different homepage hero, and different flow stories.

