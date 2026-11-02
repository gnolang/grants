# A General-Purpose Tokenization and Asset Platform on Gno.land — Reusable Components and an Adoption Plan

**Draft:** 8.  
**Applicant:** Victor Peña — BHIIKTOR  
**Funding requested (base):** **$48,000 USD total**  
**Optional additional allowance:** **$5,000–$10,000** for an independent code audit; not included in the base (Section 7)  
**Delivery period:** **12 months** from the agreed start, with a conditional continuation for months 13–24  
**Stage:** Planning; Gno implementation not yet built

## 1. Executive summary

I propose a 12-month, $48,000 project combining engineering with a bounded cash allocation: reusable asset-representation, issuance, policy, lifecycle, attestation and settlement components on Gno.land, with tests, documentation, reproducible reference applications, and the bounded provider/buyer integration needed to demonstrate them.

**Funded by this grant**

- Reusable components for asset representation, issuance, policy, lifecycle, attestation and settlement coordination.
- Tests, documentation, threat model and reproducible setup.
- Bounded reference applications and separate controlled/open deployments, including a bounded provider/buyer integration to demonstrate M2.
- Bounded provider and buyer adoption work, including paid acquisition in M3 only after readiness, and lean operations.
- A $2,000 conditional continuation reserve inside the $48,000 base for months 13–24, where spending or use requires written funder permission under the conditions in Section 7.
- Public progress reporting and developer-facing examples.

**Product context**

- A general-purpose tokenization and asset platform on Gno.land, with two products — one controlled/permissioned, one open — sharing code per layer but running as separate backend and onchain deployments, configurations, state and authorities, under one operations and support team.
- Breadth across real-world and digital, financial and non-financial assets is design intent, not verified universal support.
- TOGNO is a proposed application payment token. Its economics, holder rights, backing and supply remain open.

**Outside promised grant coverage**

- The whole platform, every asset standard, all six client surfaces, or an unrestricted production rollout.
- Production TOGNO issuance. The grant implements **test token interfaces**, not a production token.

The selected first reference is a **single whole synthetic B2B trade receivable** — not an approved live offering, not the product definition, and not a move to a private-credit-only platform. Two further reference cases, a prepaid service entitlement and an identified warehoused-goods claim, are selected in principle and staged; their funded delivery depends on technical estimate and later agreement. Adoption by asset providers and by buyers and holders is the goal, not existing traction, and M3 is not replaced by developer outreach alone.

## 2. Problem and opportunity

Tokenized asset applications depend on recurring capabilities, whatever the asset family:

- Defining an asset and the rights associated with it.
- Deciding who may hold or transfer a representation of those rights.
- Recording lifecycle transitions that apply to that asset family.
- Coordinating delivery and, where relevant, payment.
- Incorporating information about assets and activity outside the blockchain, where applicable.

Purely onchain assets need not depend on offchain documents. A reusable implementation with explicit behaviour, tests and examples gives developers a starting point for controlled or open asset workflows — and pairs the components with presence, practitioner contact and bounded acquisition aimed at issuers and asset providers, and at buyers, holders and other market participants.

**Why Gno.** The work is designed to integrate existing primitives rather than claim that basic issuance is novel or missing from the ecosystem. Gno's published reusable packages and stateful realms support a component-and-configuration approach: policy rules, asset-specific lifecycle, attestation state and signer authority, and settlement coordination expressed as reusable configuration and integration examples. Gno's security guidance describes `gno.land/p/nt/grc20/v0` as a canonical reference with safe encapsulation and canonical Teller checks; it is a candidate for an appropriate **fungible** reference only, not a selected standard for all asset types, and any actual version, licence, compatibility and security boundary must be pinned before adoption. Reference: https://docs.gno.land/resources/gno-security-guide/

## 3. Proposed contribution and initial specification

### Asset representation, issuance and policy

Asset and instrument creation with a reference to the underlying asset, rights and supporting evidence, plus configurable eligibility and transfer rules. Reference configurations demonstrate how shared components support different participation policies. An open configuration does not, by itself, make unrestricted trading of a regulated instrument lawful.

### Asset lifecycle

Lifecycle states and transitions configured for the asset family, which may include maturity, redemption, expiry, settlement or closure events where applicable. No single universal state set or forced linear sequence is assumed.

### Settlement boundary

A defined boundary between delivery, payment instructions where they apply, and asset records. Not every asset operation involves monetary settlement.

### Off-chain attestations

An interface for externally attested information such as valuation data or payment confirmations. Documentation distinguishes provenance from the truth of the contents. A record or token does not automatically establish or prove legal ownership or transferability; actual effect depends on the rights and terms represented, the issuer, custody arrangements and applicable law where relevant.

### Test token interfaces

Test-only token interfaces for units, decimals and denomination. These are explicitly not production TOGNO issuance, and reusable components must not depend on a production token to function.

### Developer-facing outputs

Tests and documented behaviour; controlled and open reference configurations; synthetic-asset demonstrations; sample integrations; reproducible setup instructions; public progress updates.

Asset identity, metadata and rights references are conceptually distinct from an issued representation. Architecture, standards selection and detailed interfaces remain subject to technical specification.

## 4. Product context

The platform is intended as general-purpose infrastructure for issuing and managing assets and associated rights on Gno.land, with two distinct products:

1. **Controlled/permissioned:** asset workflows with applicable eligibility and transfer controls.
2. **Open/permissionless:** participation and issuance configurations appropriate to the assets offered.

Permissioning and asset category are separate axes: a controlled profile may apply class-specific rules, and permissionless participation does not by itself make a regulated asset lawful to offer.

Three reference cases are selected, in order:

| # | Reference case | Represented right | What it demonstrates | Status |
|---|---|---|---|---|
| 1 | Single B2B trade receivable | Payment claim against a named debtor; the invoice is supporting evidence, not the asset | Assignment, outstanding payment and dispute states | M1 anchor; synthetic |
| 2 | Prepaid service entitlement | Right to defined service or units from a named provider | Redemption, partial consumption, expiry where applicable, and fulfilment evidence | Selected; staged extension, extent unestimated |
| 3 | Identified warehoused-goods claim | Contractual right to release specified goods from a named custodian | Custody evidence, release and delivery | Selected; staged extension, extent unestimated |

All initial reference cases use fictional identities, fictional assets and attestations, and test funds — not only the first.

The thesis is one reusable asset-workflow core tested through payment claims, service entitlements and physical-goods claims — not three products, not universal coverage, and not a private-credit-only platform.

Only the first is an M1 commitment. The second and third are selected reference cases whose funded delivery, timing and milestone allocation depend on a technical estimate and on applicable user and funder scope agreement. They are neither committed inside the $48,000 as three full implementations nor deferred indefinitely. Same-component reuse is a target, not a claim that any asset works by configuration alone. Other families are future possibilities, not funded assets.

In the receivable example, acquisition and test settlement of the claim are distinct from debtor repayment. Nothing here adds fractionalisation, pooling, interest or a secondary market. Where an invoice and a goods record both appear, they represent separate underlying obligations; linked records must not imply double assignment or double financing of the same exposure.

The intended architecture uses shared codebases with separate per-product backend and onchain deployments, configuration, state and authorities. Each product would have distinct web, desktop and mobile applications over a shared base, supported by one operations and support team.

A near-1:1 port of the source platform, or six production clients, is not committed inside the funded year.

### TOGNO

**TOGNO** is a proposed application payment token, distinct from Gno's network gas currency. Holder rights, supply, backing, settlement denomination and deployment model remain unresolved, and a single shared token would be a common dependency despite otherwise separate deployments.

No token sale, token-backing, liquidity or redemption reserve funding is proposed as a use of this grant. The $2,000 marketing and automation reserve in Section 7 is a promotion continuation fund, not a token reserve.

## 5. Milestones

Target windows run from the agreed start. They are targets, not validated schedule or cost estimates, reforecast at each gate (Section 10) with no automatic extension.

**Dependency gate 1 — before dependent implementation.** The first reference family is selected: the single synthetic trade receivable. The bounded M1 slice specification, technical feasibility, environment and acceptance detail are settled before dependent implementation begins. No week-based deadline is set here.

**Dependency gate 2 — before live customer actions and the M2→M3 transition.** First offer, jurisdiction, legal basis, custody, payment and operational readiness must be settled. The applicant acts as commercial decision lead with technical advice and qualified counsel where needed. The funder approves grant funding, scope and continuation — not legal permission. If these are missing, work pauses or moves to a written revised phase or budget; it does not auto-complete, and a demo is not "usable".

### M1 — Functional first slice and evidence pack (target months 1–3)

**Outputs**

1. **Bounded slice specification, completed before dependent implementation.** Asset and instrument fields; roles and test identities; policy rules; lifecycle states with guards and invariants appropriate to the first reference family; the settlement boundary where applicable; and attestation types with allowed state effects and signer authority.
2. **Issuance, policy and lifecycle code on a pinned candidate revision**, with tests mapped to the specification.
3. **Test settlement and attestation interfaces** — units, decimals and denomination for the test token only — covering failure, replay, stale references, unknown signers and correction result states.
4. **A minimum integrated path** on a named test environment: a supplier creates a receivable record against a named debtor, a buyer/assignee passes eligibility, a fictional assignment is recorded, a test settlement record is created, and a holding and lifecycle record results.
5. **Documentation and review pack**: reproducible setup, threat model, dependencies, known issues, and an audit scope package.

**Acceptance criteria**

- Prohibited lifecycle states and transitions fail; allowed transitions produce a defined state.
- Duplicate handling is settled per operation — not every operation must be idempotent — with no unintended double application.
- Attestation signer authority, replay, stale references and corrections each have defined, validated result states.
- The published clean setup works from the pinned revision in the named environment.

**Review evidence:** specification note, pinned revision, test results against these outcomes, integrated-path demonstration, documentation pack.

**Working boundaries:** synthetic assets, test funds and the single selected receivable family. No live asset classification, jurisdiction or mainnet release is implied, and no multiple-family coverage is claimed. A CLI may demonstrate the technical path; that is not customer-ready UX.

M1 also covers digital presence, positioning and audience discovery.

### M2 — Hardening, revision and independent review (target months 4–6)

**Outputs**

1. **Separate controlled and open deployments**, with distinct state, configuration and product authorities.
2. **Revision pass** from feedback and onboarding, covering defects and security findings, with regression tests.
3. **An integrated provider/buyer release candidate** extending M1 with onboarding, eligibility, payment status, holding records, administration reporting and measurement appropriate to an approved first offer.
4. **Walkthrough evidence** covering denied eligibility, failure handling, the administrator view, and measurement with denominators and a stated window.
5. **Operations material**: support, monitoring, key rotation and recovery/incident runbooks with named human owners and rehearsals.
6. **A frozen, independently reviewable candidate**; if the optional audit is funded, an actual external report, findings, triage, scoped repairs and rechecks around the M2 gate, contingent on provider, scope, quote and availability. Scheduling is conditional, not a guaranteed month-six completion.

**Acceptance criteria**

- Unauthorized writes fail across product deployments and, where any shared test-token resource is chosen, across that resource as well; deliberately shared state, permitted callers and authority boundaries are documented and tested.
- Audit status — candidate, reviewed, remediated — is evidenced separately; a failed required criterion blocks the appropriate acceptance.
- Every expected outcome is paired with a test or evidence artifact, not a test report alone.

**Still open:** the first live offer, instrument, jurisdiction, custody and payment, which are needed before live customer actions or paid acquisition and do not block independent test work. The second and third reference cases remain unestimated extensions.

M2 continues presence, online networking and relationships with asset providers, buyers and holders.

### M3 and M4 — summary (target months 7–12)

| Phase | Outputs | Review evidence |
|---|---|---|
| **M3 — Growth and user acquisition** (7–9) | Maintained usable release improved from actual onboarding; bounded paid promotion across selected channels with comparative results | Channel spend; qualified leads; onboarding, activation and repeat use reported separately for providers and buyers, with denominators and windows |
| **M4 — Closure and handoff** (10–12) | Documentation, operational handoff, ownership, outstanding issues, final report; next-year promotion plan, reusable assets and supervised automation with cost caps and written permission for year-two spend | Handoff pack; clean-setup walkthrough; final expenditure report; continuation responsibilities |

Testing, documentation and security checks run from M1; M2 is focused hardening and revision; M4 consolidates documentation and handoff.

**"Fully usable" before M3** means a bounded first release supporting an actual permitted customer journey — rights, eligibility, payment, custody, administration, support, monitoring, recovery and disclosures appropriate to the specific offer — not merely a synthetic demonstration. It confers no real-money authority. Paid acquisition starts only after asset family, instrument, jurisdiction and channel checks, consent tracking, safe data handling, spending caps and pause rules are in place.

Administrator access permits inspection and following explicitly defined failure and recovery paths; it implies no reversal, clawback or seizure of finalised transactions.

## 6. Applicant and relevant experience

I am **Victor Peña (BHIIKTOR)**, with 25+ years in software engineering and technical leadership.

- **Backbone Lab:** CosmWasm contracts, TypeScript applications and supporting infrastructure.
- **Eclipse Launchpad:** technical leadership from development through market launch.
- **AstroMint:** CTO responsibilities from protocol concept through MVP.
- **Technical background:** Rust, CosmWasm/Cosmos, Solidity/EVM, backend systems, testing, CI/CD, additional Go experience.
- **Open-source tooling:** [SAISO](https://github.com/BHIIKTOR/saiso) and Barfer.

The proposed Gno implementation is new work; this is experience to draw on, not an existing Gno delivery record.

## 7. Budget and availability

### Quarterly receipts (requested)

| Phase | Compensation | G & O | Total |
|---|---:|---:|---:|
| Q1 (months 1–3) | $10,000 | $2,000 | $12,000 |
| Q2 (months 4–6) | $10,000 | $2,000 | $12,000 |
| Q3 (months 7–9) | $10,000 | $2,000 | $12,000 |
| Q4 (months 10–12) | $10,000 | $2,000 | $12,000 |
| **Total** | **$40,000** | **$8,000** | **$48,000** |

Payments are requested at each phase start, Q1 under the initial agreement and later tranches only after the preceding review. This is our request, not a statement of programme policy, and no award is assumed.

### Growth and operations itemisation ($8,000)

| Line | Amount | Timing |
|---|---:|---|
| Presence, introductory marketing and discovery | $1,000 | M1 |
| Continued marketing, online networking and audience development | $1,000 | M2 |
| Bounded paid acquisition channels | $2,500 | M3 |
| Continuation campaign and automation setup (external expenses) | $500 | M4 |
| Ring-fenced promotion and automation reserve | $2,000 | Months 13–24 |
| Lean operations and contingency | $1,000 | Year 1 |
| **Total** | **$8,000** | |

$7,000 of the $8,000 is growth, including the $2,000 continuation reserve; $1,000 is operations. Year-one direct cash expenditure is $6,000.

**Lean operations breakdown ($1,000):** $250 hosting and development infrastructure; $250 GNOT/ugnot gas and storage; $300 tool licences; $200 operating contingency. Network fees are real and unestimated.

All figures are planning allowances, not verified quotes or confirmed cost coverage. External cash is separate from the $40,000 compensation; no cost is counted twice.

### Optional additional code audit (not in the $48,000 base)

A **USD 5,000–10,000** allowance is optional and additional, for independent review of a bounded, frozen code candidate. No quote, auditor, exact scope, timing or payment event is settled, and the combined prospective total would be **$53,000–$58,000 only if this is separately funded on top of the base**.

No automatic reallocation is proposed. Any reallocation would require a separately agreed, named revised budget and would never be taken automatically from compensation, growth or the $2,000 continuation reserve.

**If the optional audit is not funded:** base components, reference applications and required internal checks continue within the approved baseline, with **no externally audited claim**. Any real-customer release or acquisition that depends on an audit remains paused or requires an explicit user-and-funder approved revised scope. It is not silently dropped, deferred to year two, or replaced by a safety waiver, and provider/buyer growth is not automatically replaced.

Base M2 component acceptance is distinct from the additional external-review deliverable. A report is not a pass and not a remediation. Candidate, report, triage, scoped repair and recheck are evidenced separately, with technical disposition and separate acceptance of any permissible residual risk. Mandatory safeguards are never waived.

### Continuation reserve

The $2,000 reserve is already inside the $48,000, not an additional grant — a modest continuation programme, with scheduled promotion possible within agreed caps and no promised results. Recurring cost coverage, a named human owner, spending caps, monitoring and pause conditions require agreement; automation does not remove the need for oversight.

**Written funder permission is required before spending the reserve during months 13–24 and before any carryforward of unused M1–M3 growth or operations cash.** Year-one delivery and handoff close at M4, but agreed year-two spending and reporting obligations continue under the grant terms. No automatic rollover is implied.

### Availability and capacity

Intended availability is full time for 12 months: approximately 48 hours per week, six eight-hour days, 2,496 planning hours on a 52-week basis. This is stated availability, not validated billable effort, and no free 24-month commitment is offered.

Capacity is intended across engineering, tests and documentation, adoption and operations, and audit coordination and rework. No validated hour split is asserted; a time allocation and estimate should be prepared against the first slice and bounded contract before formal commitment.

Payment currency, timing beyond the request above, fees, withholding, and treatment of spent or unspent funds remain to be agreed. Legal review, security assessment and additional staffing for ongoing support are unpriced coverage questions, not established as covered or as separately funded.

## 8. Community benefit and adoption

The reusable components are intended to help other Gno developers understand, run and integrate them independently of our products.

Adoption is a goal, not existing traction. Provider and buyer funnels are tracked separately, with denominators and time windows. Evidence includes qualified leads, onboarding completion, activation, repeat use and reasons for abandonment. No user numbers, CAC, LTV or returns are guaranteed, and paid acquisition is not developer relations in disguise.

## 9. Public progress, licensing and IP

### Legal brief

The selected reference cases are synthetic test objects. No asset, jurisdiction or operator role is cleared for live use. Classification, transfer, enforcement, custody, promotion and AML scope depend on the rights represented, the operator's activities, jurisdiction and applicable law; controlled or open participation is not an exemption; a token does not automatically establish or prove title. Grant approval or a code audit is not legal clearance.

Privacy duties can begin with the first real personal-data collection, including M1 presence and discovery and M2 networking, even when asset fixtures are fictional. Gno data is public and permanent, `private=true` is not confidentiality, and offchain storage or hashing is not automatic compliance.

Expanded dated research, with sources and limits: [LEGAL.md](./LEGAL.md). It is a research reference, not legal advice; its EU and US branches are illustrative, and no jurisdiction is selected.

### Licensing

Progress reporting, documentation and reusable outputs are intended to be public.

For newly authored funded components, I propose **Apache-2.0**, subject to dependency compatibility, actual rights and programme agreement. Its express patent grant and clearer contribution terms suit infrastructure other teams will embed.

Existing IP, NDA-covered or proprietary sources are not automatically licensed, reused or published; a source and rights check precedes publication, and third-party work is not claimed as owned. This section is a licence proposal, not an actual licence file or licensing grant.

Actual network terms, CLA, dependency rights and the conflicting licence versions must be resolved before dependent publication or reliance, distinguishing original code, dependencies, the onchain copy and UI/service attribution. That requires the licensor and counsel, not the funder alone. Handoff materials would contain no keys or personal data.

## 10. Continuity, review and submission readiness

Each phase ends with review by the funder's designated human reviewers of agreed outputs, evidence and expenditure, and the next phase plan. **Funder approval is expressly required both for continuation and for release of the next tranche.** Dispositions: continue; one consolidated revision round within remaining phase budget and time; or pause/stop. No next tranche is automatic, no silence implies approval, and material scope or timing changes need written agreement. M4 is final delivery acceptance plus a separate funder decision approving any reserve use in months 13–24 — not renewal.

The programme prioritises reusable applications, libraries and developer tooling, and its formal route is a project proposal using the official template, submitted as a pull request, followed by email to grants@tendermint.com; questions by email are also invited. This is not confirmation of mailbox deliverability, current funding availability, or eligibility of marketing spend, advances or year-two carryforward. Formal template mapping is required before submission; the document does not claim template conformance.

Remaining before formal submission: technical estimates and acceptance detail for milestone dates; confirmation of whether the second and third reference cases are included in the submitted scope, with any included extension requiring an estimate, milestone allocation and funding; validation of cash quotes; confirmation of programme eligibility; licensing and IP position; and settlement of the optional audit (funding route, quote, provider and timing).

**This draft supports a programme-fit discussion. It is not an approved grant, committed schedule or authorization to launch financial products.**
