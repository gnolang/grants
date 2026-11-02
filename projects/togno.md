# TOGNO — A General-Purpose Tokenization and Asset Platform on Gno.land

- **GitHub handle:** [BHIIKTOR](https://github.com/BHIIKTOR)
- **Email:** victor@pues.dev
- **Links:** [X](https://x.com/BHIIKTOR) · [LinkedIn](https://www.linkedin.com/in/victor-pe%C3%B1a-01a6553a8/) · [Website](https://www.zilinlabs.com/) · [Additional GitHub](https://github.com/victorh-doi)

The [Full proposal](./togno/PROPOSAL.md) and [Legal research](./togno/LEGAL.md) are the companion documents; the full proposal governs scope, budget and acceptance.

## Project summary

TOGNO is a planned general-purpose tokenization and asset platform on Gno.land for representing, issuing and managing assets and associated rights. It is intended to serve financial and non-financial assets, real-world and digital, through two distinct products — one controlled/permissioned and one open — that share code per layer while running as separate backend and onchain deployments, configurations, state and authorities under one operations and support team. That breadth is design intent, not verified universal support for every asset type, standard or rights model.

The funded work is a reusable, public asset-workflow core: representation and issuance, configurable policy, asset-family lifecycle, off-chain attestations, settlement boundaries and test token interfaces, with tests, threat model, documentation and reproducible reference applications.

### Goals and deliverables

- Reusable Gno components for asset representation, issuance, policy, lifecycle, attestation and settlement coordination.
- Tests, documented behaviour, threat model and reproducible setup.
- Bounded reference applications and separate controlled/open deployments, including a bounded provider/buyer integration to demonstrate M2.
- Bounded provider and buyer adoption work, including paid acquisition in M3 only after readiness, and lean operations.
- A $2,000 conditional continuation reserve inside the base for months 13–24, where spending or use requires written funder permission.

The first reference case is a **single whole synthetic B2B trade receivable**: a payment claim from a fictional supplier against a named fictional debtor, with the invoice as supporting evidence rather than the asset itself, and fictional assignment, identities, attestations and test funds. Acquisition and test settlement of the claim are distinct from debtor repayment; no fractionalisation, pooling, interest or secondary market is proposed. Two further reference cases — a prepaid service entitlement and an identified warehoused-goods claim — are selected as staged extensions. The first receivable reference is part of the base M1 scope. The second and third are not assumed funded inside the base; whether they are included in the submitted scope is to be confirmed, and any included extension requires its own estimate, milestone allocation and funding.

**Funding.** $48,000 over 12 months, comprising $40,000 compensation and $8,000 growth and operating cash, requested as four $12,000 quarterly tranches with human funder review before continuation and release. One consolidated revision round is permitted within remaining phase budget and time; no automatic extension. A code audit of $5,000–$10,000 is optional and additional, giving $53,000–$58,000 only if separately funded. If it is not funded, base components and required internal checks continue without any audited claim, and any real-customer release or acquisition dependent on audit remains paused or needs an explicit user-and-funder revised scope. No automatic reallocation from the base is proposed. Production TOGNO issuance, an unrestricted production rollout, all asset types and all client surfaces are outside this request; the grant implements test token interfaces only.

### Impact on gno.land’s developer ecosystem

The output is intended as public, reusable infrastructure: Gno packages and stateful realms that other builders can study, run and adapt, with documented primitives rather than a claim of novel coin issuance. Where a standard is referenced, `gno.land/p/nt/grc20/v0` is treated as a candidate fungible reference only, subject to version, licence and compatibility checks; no verified deployment, universal compatibility or liquidity is claimed.

Licensing is proposed as Apache-2.0 for newly authored funded components, subject to actual rights, dependency compatibility, programme agreement and the unresolved Gno network terms and CLA applicability described in the legal research. No licence file or compatibility assurance is asserted.

### Timeline and milestones

Targets, not validated schedule or cost estimates:

- **M1 (months 1–3):** a tested end-to-end slice for the synthetic receivable — issuance, policy, lifecycle, settlement records and attestations — with a bounded specification, environment and feasibility settled before dependent implementation.
- **M2 (months 4–6):** integrated controlled and open provider/buyer/holder flows, internal hardening, an independently reviewable candidate, and an external review only if separately funded.
- **M3 (months 7–9):** bounded, measured provider and buyer/holder acquisition, only after readiness.
- **M4 (months 10–12):** documentation, operational handoff and a conditional continuation plan.

A second gate requires the first live offer, jurisdiction, legal basis, custody, payment and operational readiness to be settled before live activities and before M2→M3. Funder approval is grant approval, not legal permission. Privacy duties begin with the first real personal-data collection, including presence and networking, even while assets are fictional. The legal research is a dated reference, not clearance.

Meaningful M1/M2 outcomes include prohibited lifecycle transitions failing, allowed transitions producing defined states, attestation signer authority and replay handling having defined result states, and unauthorized writes failing across deployments and any chosen shared test resource. Full criteria are in the proposal. No tests have run yet.

## Contributions or related work for gno.land (if applicable)

The Gno implementation would be new work. No prior Gno contributions are claimed, and no Gno deployment, integration or ecosystem participation is asserted.

## Why are you and your team well-suited for this project?

I am Victor Peña (BHIIKTOR), with 25+ years in software engineering and technical leadership: Rust/CosmWasm/Cosmos work at Backbone Lab and Eclipse Launchpad, CTO responsibilities at AstroMint from concept to MVP, plus Solidity/EVM, backend systems, testing and CI/CD, and additional Go experience.

That background includes work on tokenization and private-credit systems at a prior employer. It informs the design, but NDA-covered or proprietary material from that work is not automatically reused or published and would require actual rights.

This is a solo application. No team members, partners, issuers or customers are claimed.

## Referrals or examples of past work

- [SAISO](https://github.com/BHIIKTOR/saiso) — developer tooling.
- [Additional GitHub](https://github.com/victorh-doi) — a secondary public account.

No referrals, testimonials, audited results or independent verification of past work are claimed.
