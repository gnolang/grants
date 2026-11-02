# Legal, Regulatory and Licensing Research — Companion to PROPOSAL.md

**Status:** Draft 3 — research reference, with a product selection note. Not legal advice, not a legal opinion or certification, not a counsel engagement, and not permission to launch any product or activity.
**Research date:** 2 November 2026 (UTC), with a targeted recheck of the licensing and SEC sources at approximately 20:27 (UTC); earlier retrieval times are retained per source.
**Companion to:** [PROPOSAL.md](./PROPOSAL.md) (Draft 8). This document does not restate the budget, milestones or acceptance criteria; those remain governed by the proposal.

## 1. Purpose, scope and limits

This annex records the legal, regulatory and licensing research behind the general-purpose tokenization and asset platform described in the proposal. It exists so that findings are retained rather than re-derived, and so that the proposal can cite them without carrying a long legal appendix.

Limits that apply to everything below:

- No jurisdiction has been selected. The European Union and United States branches are **illustrative researched branches**, not an assumption about where any activity will occur. Other jurisdictions have not been surveyed.
- No live asset is classified or cleared. The product selection of synthetic reference cases is recorded in Section 1; it is an editorial update, not a researched legal finding.
- No regime, licence, exemption, sandbox admission or filing is claimed to apply.
- Nothing here states that a token or record does or does not confer enforceable rights in any particular case; legal effect depends on the arrangement and applicable law.
- Sources differ in legal weight: published terms, legislation summaries, regulatory guidelines, SEC staff views, press releases and nonbinding model principles are identified separately; applicability and legal effect require jurisdiction-specific review.
- Only the sources listed in Section 12 were reviewed. Gaps are recorded rather than filled.

Findings, proposed implications, and unresolved choices are kept separate throughout. Research findings do not themselves adopt decisions; the selected reference cases and the incorporated planning conditions are identified below, and other suggestions remain provisional. The legal brief, privacy timing and licensing qualifications reflected in the proposal are planning conditions, not a legal opinion, clearance or adopted implementation architecture.

**Selection status (product update; not a researched legal finding).** The user has selected a synthetic reference package in this order: (1) a single whole B2B trade receivable, (2) a prepaid service entitlement, and (3) an identified warehoused-goods claim. Only the first is an M1 anchor; the second and third are staged extensions whose scope, timing and funding are unestimated. The first live offer, jurisdiction, operator roles and counterparties remain unselected, and no asset is classified or cleared for live use.

## 2. Summary of key findings

1. **Tokenized financial instruments remain financial instruments.** EU guidance is substance-over-form and technology-neutral; a whitelist, a "utility" label or an NFT label does not by itself remove a financial-instrument classification.
2. **A token does not automatically establish or prove title.** International model principles treat control and ownership as distinct, and link digital-asset effects to domestic law.
3. **The operator's role matters as much as the asset.** Software author, issuer, arranger, custodian, venue and payment provider carry different duties; the same code can sit inside very different regulated activities.
4. **Gno network terms and licensing show a source, version and scope discrepancy.** Terms, CLA, `gno.land/license`, the repository `LICENSE.md` and the README badge do not line up on version or scope. The binding target requires clarification by the licensor with counsel rather than an assumption that one source silently governs.
5. **Publication is permanent in practical terms.** Gno documentation states source cannot be deleted; removing current realm data does not erase chain history. `private=true` is not confidentiality.
6. **Submission is not execution.** Documented configuration supports code being submitted and stored without being active; execution success is a separate event. Documented RPC interfaces do not support event subscriptions, though target behaviour was not runtime tested.
7. **Connectivity needs route-specific verification.** An operator-described bridge for GNOT/BUBBLE to Solana carries limited assurance; no general EVM, IBC, USDC or fiat route was verified, and this research did not establish that none exist.
8. **Privacy applies earlier than a live launch.** Wallet metadata, presence and networking data can be personal data even when asset fixtures are fictional.

## 3. Gno technical features with legal implications

**Network status (documented, not runtime-verified).** The Gno README and network documentation state mainnet `gnoland-1` went live on 12 September 2026 with no faucet, and that native balances begin locked under Constitution §126; the current unlock state was not checked. Onyx `onyx-1` (test) is documented as launched 28 September 2026 with a faucet, open transfers and a mainnet-line upgrade rehearsal — not production equivalence. The exact deployed version was not pinned: the mainnet deployments path returned robots denial and was not bypassed.

*Implication:* availability of a network is not availability of application assets, and locked native balances are not evidence that application-level transfers are blocked.

**Submission versus activation versus execution.** Configuration documentation describes `vm:p:code_submission_policy=inert` as supporting submitted and stored code that is not yet active; the actual target activation policy was not verified. Deployment, activation and successful execution are distinct.

*Implication:* "deployed" is not "live", and "accepted" is not "executed".

**Storage and fees.** Documentation states source cannot be deleted, that removing current realm data is not erasure of chain history, and that storage requires a GNOT deposit with refund conditions. Gas documentation notes that included failed transactions still pay fees, with variable native gas and storage deposits.

*Implication:* retention and cost representations must not imply deletion or confidentiality. The $250 allowance in the proposal is unvalidated and is not a quote.

**Confidentiality.** `private=true` affects imports and re-uploads, not confidentiality; code and deployment transactions are public.

*Implication:* no confidentiality claim attaches to onchain components.

**RPC and event observation.** Go and JavaScript clients and query/submit paths are documented, with HTTP and WebSocket transport. The documented RPC interfaces do not support event subscriptions; target behaviour was not runtime tested. HTTP 200 or `CheckTx` acceptance is not final execution.

*Implication:* execution observation requires a reconciliation design; this is a technical matter and not adopted architecture here. It is not legal settlement finality.

**Wallets and clients.** Adena, a browser extension, and GnoConnect are documented; mobile and desktop support were not verified as integrated.

*Implication:* wallet key control is not evidence of title to an underlying asset.

**Security guidance.** The security guide documents `gno.land/p/nt/grc20/v0` as a canonical fungible reference candidate. The proposal treats it as a candidate subject to pinning, not as a standard chosen for all asset types. The guide also discusses realm authority, canonical Teller checks, encapsulation and realm callback risks. Community packages are not official stable APIs and some are quarantined and not importable.

*Implication:* separate deployments do not by themselves establish isolation; dependencies and rights must be pinned.

**Bridge.** `bridge.gno.world` is an operator-described GNOT/BUBBLE bridge to Solana using lock/mint/burn, return 2-of-3 attestors, limits, guardian pauses, initially single-key governance, and expressly no external audit. These are operator assertions; implementation, reserves and production capability were not verified. `bridge.onbloc.xyz` was robots-refused and no alternate route was used.

*Implication:* no production general bridge, stablecoin route, fiat on-ramp, custody or oracle is assumed. Bridge construction is not part of the grant.

## 4. Intellectual property, licensing and the CLA

The reviewed sources show a source, version and scope discrepancy rather than four automatically competing current terms:

- **Network Terms** (`TERMS.md`, §1–§8, complete retrieval at pinned commit `251b706675d7701e33345620167b8fd3711bb671`; targeted sections reviewed): ownership retained; perpetual broad rights over content and result-state for network operations, mirrors and forks; public permanent data with no confidentiality or deletion assurance; representations of adequate rights and sanctions/export compliance; §5 states published-for-execution code and copyrightable work is under "GNO Network GPLv6+ strong attribution", with a required applicable CLA hash; §6 disclaims guarantees. **§8 states an express precedence**: these Network Interaction Terms control for on-chain submissions and the licence grants in the Terms, while the Interface Terms of Service control for use of the interfaces. No terms or CLA acceptance or signing occurred during this research; the applicant's prior acceptance history and the actual target hash are not established.
- **CLA** (`CLA.md`, complete retrieval at the same pinned commit; targeted sections reviewed): §3 copyright grant for the Contribution; §4 separate input and result-state permissions within the rights held; §5 patent grant for owned or controlled claims necessarily infringed by the code portion, alone or combined with the Network — not a patent grant over all data. Employer and third-party permission representations; canonical onchain CLA hash. The actually accepted hash was not checked.
- **Repository licence** (`LICENSE.md`, pinned commit, 38,571 characters retrieved complete; targeted sections reviewed, not a full end-to-end legal review): opening states v6+, the introduction refers to an attached v4, and the definition refers to "this License" as v6; strong attribution extends to UIs and services using covered work. This internal mismatch is directly verified in the pinned file.
- **Site licence** (`gno.land/license`, complete page retrieved, 39,772 characters, re-fetched 2026-11-02T20:27:16Z; header, footer and version statements reviewed during the targeted recheck, not a fresh end-to-end legal review): the UI header shows "Network Info / Chain ID gnoland-1 / RPC Address https://rpc.gno.land"; the body states v4, dated 7 May 2024, with different scope and duration; the footer (©2026) states that code and copyrightable works published through Gno.land are under GNO Network GPLv6 or later with Strong Attribution, and links the Network Terms and CLA. No "betanet" reference appeared in this retrieval. The older-dated body therefore sits alongside a currently mainnet-labelled page and a v6 footer; this is not runtime proof, and no conclusion is drawn that v4 binds mainnet. The absence of a betanet reference here does not prove none existed historically.
- The README badge (v5) is repository metadata, as previously observed, and not operative authority.

The material point is that the target version, scope, attribution obligations and CLA hash are unresolved and must be clarified by the actual licensor with counsel before reliance or publication. The §8 precedence statement addresses conflicts between the Network Terms and the interface terms; it does not by itself resolve dependency compatibility, CLA questions or enforceability.

Layered analysis is required rather than a single licence decision:

| Layer | What it is | Open question |
|---|---|---|
| Independent original offchain source | Code we author outside the Gno repository | Apache-2.0 remains an option, not a settled restriction |
| Dependencies and derivatives | Third-party packages, combined or modified works | Compatibility and rights per dependency |
| Onchain published copy | Work published for execution on the network | Which version, attribution and CLA apply |
| Frontends and services | UIs and services using covered work | Attribution scope for UIs and services |

NDA-covered or proprietary source material is excluded absent actual rights. No dual-licensing workaround is proposed, and the funder alone cannot decide binding third-party terms.

The proposal's current §9 conditional Apache-2.0 proposal for newly authored funded components is unchanged. This research neither establishes that Apache-2.0 is compatible with the target onchain terms nor that it is incompatible; independent offchain source under Apache-2.0 is one option for counsel and licensor review, not a finding that it must be restricted, and not an adopted licence change.

## 5. Rights, issuance, transfer, custody and operator activity

The following matrix separates questions that are often conflated. It does not classify any candidate asset.

| Question | What it turns on | Evidence status |
|---|---|---|
| What right is represented? | Contract terms, instrument documentation, statutory rights | Not established for any family |
| Who is the obligor? | Issuer, fund, debtor, service provider | Not established |
| Does the record confer or evidence the right? | Domestic law, arrangement, authoritative record | UNIDROIT model principles: control ≠ ownership |
| Can it be transferred, and to whom? | Assignment rules, restrictions, notices, consents | Jurisdiction-dependent |
| What happens on insolvency? | Custody structure, segregation, priority | Separate analysis; no global rule |
| Who operates the activity? | Author, issuer, arranger, custodian, venue, payment provider | Roles not assigned |

UNIDROIT's 2023 model principles are nonbinding absent implementation. They treat the effects of a linked asset as a matter of domestic and other applicable law, distinguish control from ownership, and address custody and insolvency separately. They do not create a global SPV requirement or a securities exemption.

## 6. Illustrative EU branch (not a selected regime)

- **MiCA** applies to crypto-assets not already covered by existing financial-services legislation. It is not a universal licensing route for real-world assets. ESMA's final guidelines (19 March 2025) apply substance over form and technology neutrality; tokenized financial instruments remain financial instruments; whitelisting alone does not remove a securities classification; pooled investment and fund rights matter; utility and NFT labels do not provide universal exclusion.
- **DLT Pilot Regime** (applicable since 23 March 2023) is a permission regime for DLT market infrastructures — trading and settlement systems — requiring relevant authorisations and pilot permission for authorised firms, operators, CSDs or entrants. It is not an automatic startup waiver, and thresholds and eligibility were not assessed.

No candidate family has been classified under either branch.

## 7. Illustrative US branch (not a selected regime)

- The SEC's 28 January 2026 staff statement on tokenized securities is a staff view without the force of law (its footnote 2 says it is not a rule, Commission approval, or legal force). It distinguishes issuer-sponsored records from third-party custodial entitlements and synthetic exposure, noting different holder rights and intermediary insolvency exposure; securities obligations do not disappear with format. State-law validity of issuance and transfer is assumed, not certified.
- The 17 September 2026 press release describes a conditional, temporary innovation exemption for permissioned AMM pools trading tokenized NMS stock, with limits, notices, same-rights conditions, auditable and public smart contracts deployed on a public, permissionless distributed ledger, and halts. That clause concerns auditability and public deployment, not a completed independent audit requirement. The underlying order was not read. It is not general startup eligibility or a right to rely, and the reported five-year expiry is not a deregulation promise.

## 8. Privacy, data protection, AML and promotions

- **EDPB blockchain guidelines, final version 2, adopted 7 July 2026** (all 27 pages extracted): wallet metadata, payloads, state and logs can be personal data; roles, lawful basis, minimisation, retention, rights, international transfers and DPIA obligations apply where relevant. Encryption is not automatic anonymity; salted or keyed hashes are not automatic anonymisation. Offchain documents with minimal onchain commitments reduce exposure but are not blanket compliance.
- **Timing:** real wallet metadata, M1 presence and discovery, and M2 networking can involve personal data even when asset fixtures are fictional. Privacy controls are needed before the first actual collection, not only at M3.
- **Travel Rule (EBA guidelines):** information requirements apply to in-scope PSPs, CASPs and intermediaries for transfers of funds and certain crypto-assets. Scope depends on activity and nexus; it does not automatically apply to every developer or campaign.
- **Promotion and consent** are separate questions from AML or asset classification.
- **Gaps:** FATF guidance returned HTTP 403 and OFAC search extraction failed; these are recorded as unverified, not as support for any conclusion. Local tax, consumer, commercial, marketing and cross-border rules were not examined country by country.

## 9. Candidate asset dependency table (selected reference cases)

The three cases below are selected as product reference cases in the order shown: (1) a single trade receivable, (2) a prepaid service entitlement, and (3) an identified warehoused-goods claim. The Treasury-linked fund interest remains an unselected comparative example. No case is ranked or characterised as easiest, cheapest, most complete or best, and selection is not legal classification or clearance.

| Candidate | Core legal/operational dependencies | Synthetic feasibility |
|---|---|---|
| 1. Single trade receivable | Assignment, debtor notice, partial payment, default, disputes, priority, double assignment, enforcement | Possible with fictional fixtures |
| 2. Service or digital entitlement | Who owes fulfilment; redemption, refunds, expiry; consumer terms | Possible without a real issuer contract |
| 3. Physical goods claim | Identity, title, custody, storage, insurance, release, delivery | Possible; custody semantics remain |
| — Treasury-linked fund interest (unselected comparison) | Fund interest rather than direct Treasury ownership; eligibility, valuation, subscription, redemption; manager, custody, distribution | Possible; a synthetic fund needs no real regulated issuer |

For real activity, the applicable dependencies must be assessed and resolved before the action that relies on them. They are not prerequisites for writing fictional tests.

## 10. Decision checklist and timing

Resolve when the dependent action arises; not all at once, and not as a blanket condition on fictional M1 work:

1. Operating entity and the locations of issuer, provider and customers.
2. Actual roles: software author, issuer, arranger, market, custodian, payment provider.
3. Underlying rights and the authoritative record.
4. Transfer, enforcement and insolvency treatment.
5. Settlement rail and provider terms.
6. Data map, lawful basis, retention and international transfers.
7. Concrete AML, sanctions and promotion obligations.
8. Publication licence, CLA hash and dependency rights.
9. Unpriced legal, custody, payment and support costs.

Funder approval is not a licence, sandbox admission or legal permission. An external code audit is not legal clearance.

## 11. Implications: incorporated conditions and remaining proposals

The legal brief, privacy timing and licensing qualifications below are now reflected in PROPOSAL Draft 8 as planning conditions. That incorporation is not a legal opinion, clearance or adopted architecture. Other suggestions remain provisional.

- §2/§3 continue to describe the contribution without asserting verified runtime capability; platform constraints remain background evidence. *Not separately incorporated.*
- §9 distinguishes licence layers and discloses unresolved target terms and compatibility; the conditional Apache-2.0 proposal is unchanged, and independent-offchain Apache is one option for counsel and licensor review. *Incorporated.*
- §9 of the proposal includes a licensing clarification step before dependent publication. *Incorporated.*
- Privacy language moves earlier, covering presence and networking metadata. *Incorporated.*
- No budget, milestone or scope change is implied by this document.

## 12. Sources

All retrieved 2 November 2026 unless noted. These are the sources used in this companion. "Full" means the extracted text was read end to end; "capped" or "excerpt" means the read was truncated and the limit is stated.

Sources 1–3 use commit-pinned permalinks at `251b706675d7701e33345620167b8fd3711bb671`. The original mutable `master` lookups are noted with their earlier times; the pin is a research-source revision, not retroactive proof that the earlier retrieval used the same commit, and not proof of the deployed network revision or of the onchain CLA hash.

| # | Source | URL | Fetched (UTC) | Read status / version |
|---|---|---|---|---|
| 1 | Gno Network Terms | https://github.com/gnolang/gno/blob/251b706675d7701e33345620167b8fd3711bb671/TERMS.md | 20:27:51 (pinned); original 19:19:04 | Pinned commit; 8,736 chars; complete retrieval, targeted sections reviewed; published terms; no acceptance performed during this research; target hash not established |
| 2 | Gno CLA | https://github.com/gnolang/gno/blob/251b706675d7701e33345620167b8fd3711bb671/CLA.md | 20:27:49 (pinned); original 19:22:04 | Pinned commit; 8,819 chars; complete retrieval, targeted sections reviewed; scope corrected per §3–§5; canonical hash not checked |
| 3 | Repository licence | https://github.com/gnolang/gno/blob/251b706675d7701e33345620167b8fd3711bb671/LICENSE.md | 20:27:49 (pinned); original 19:19:03 | Pinned commit; 38,571 chars complete retrieval, targeted sections reviewed, not a full legal review; v6 opening, v4 intro mismatch verified |
| 4 | Site licence | https://gno.land/license | 20:27:16 (recheck); original 19:20:16 | Complete page retrieved, 39,772 chars; header/footer/version statements reviewed during targeted recheck, not a fresh end-to-end legal review; mainnet-labelled UI, v4 body dated 2024-05-07, v6 footer; no betanet reference in this retrieval |
| 5 | UNIDROIT digital assets work | https://www.unidroit.org/work-in-progress/digital-assets-and-private-law/ | 19:22:04 | Page full |
| 6 | UNIDROIT Principles PDF | https://www.unidroit.org/wp-content/uploads/2024/01/Principles-on-Digital-Assets-and-Private-Law-linked-1.pdf | 19:25:54 | All 143 pages; 2023 model principles, nonbinding |
| 7 | ESMA MiCA page | https://www.esma.europa.eu/esmas-activities/digital-finance-and-innovation/markets-crypto-assets-regulation-mica | 19:18:48 | Full |
| 8 | ESMA CA qualification guidelines | https://www.esma.europa.eu/sites/default/files/2025-03/ESMA75453128700-1323_Guidelines_on_the_conditions_and_criteria_for_the_qualification_of_CAs_as_FIs.pdf | 19:25:43 | All 21 pages; final, 19 Mar 2025 |
| 9 | ESMA DLT Pilot Regime | https://www.esma.europa.eu/esmas-activities/digital-finance-and-innovation/dlt-pilot-regime | 19:22:04 | Full, 3,340 chars |
| 10 | SEC staff statement, tokenized securities | https://www.sec.gov/newsroom/speeches-statements/corp-fin-statement-tokenized-securities-012826-statement-tokenized-securities | 19:18:49 | Capped 20k; main text and footnotes; tail references truncated; staff statement without legal force |
| 11 | SEC press release 2026-90 | https://www.sec.gov/newsroom/press-releases/2026-90-sec-issues-innovation-exemption-facilitate-trading-tokenized-nms-stock-request-comment | 20:26:44 (recheck); original 19:18:49 | Full, 3,993 chars; underlying order not read; auditability clause, not a completed-audit requirement |
| 12 | EDPB blockchain guidelines | https://www.edpb.europa.eu/documents/guideline/guidelines-022025-on-processing-of-personal-data-through-blockchain_en | 19:28:26 | Completed read; final v2 adopted 7 Jul 2026 |
| 13 | EDPB final PDF | https://www.edpb.europa.eu/system/files/2026-07/edpb_guidelines_202502_blockchain_v2_en.pdf | 19:31:51 | All 27 pages |
| 14 | EBA Travel Rule guidelines | https://www.eba.europa.eu/activities/single-rulebook/regulatory-activities/anti-money-laundering-and-countering-financing-terrorism/guidelines-information-requirements-relation-transfers-funds-and-certain-crypto-assets-transfers | 19:32:13 | Full page |
| 15 | FATF virtual-asset guidance | https://www.fatf-gafi.org/en/publications/Fatfrecommendations/Guidance-rba-virtual-assets-2021.html | — | HTTP 403; unverified gap, no bypass |
| 16 | Gno repository README | https://github.com/gnolang/gno | 19:18:46 | Full; badge v5 conflicts with licence docs |
| 17 | Gno networks | https://docs.gno.land/resources/gnoland-networks/ | 19:19:12 | Full, 17,265 chars; mainnet and Onyx dates; unlock not checked |
| 18 | Gno project configuration | https://docs.gno.land/resources/configuring-gno-projects/ | 19:20:18 | Full, 5,745 chars; `private`, inert submission policy |
| 19 | Gno storage deposit | https://docs.gno.land/resources/storage-deposit/ | 19:19:47 | Full, ~4k; no source deletion |
| 20 | Gno gas fees | https://docs.gno.land/resources/gas-fees/ | 19:19:44 | First 9,500 chars; excerpt |
| 21 | Gno security guide | https://docs.gno.land/resources/gno-security-guide/ | 19:20:15 | Full, 30,638 chars; grc20/v0 reference candidate |
| 22 | Gno community packages | https://docs.gno.land/resources/community-packages/ | 19:19:11 | Full; unstable APIs, quarantined packages |
| 23 | Gno RPC clients | https://docs.gno.land/builders/rpc-clients/ | 19:19:08 | Full, 2,052 chars; no event subscriptions |
| 24 | Gno RPC endpoints | https://docs.gno.land/resources/rpc-endpoints/ | 19:19:45 | First 9,500 chars; excerpt |
| 25 | GnoConnect | https://docs.gno.land/resources/gnoconnect/ | 19:19:09 | Full, 2,698 chars |
| 26 | Third-party wallets | https://docs.gno.land/users/third-party-wallets/ | 19:19:10 | Full, 1,830 chars; Adena browser extension |
| 27 | Gno bridge operator page | https://bridge.gno.world/ | 19:19:40 | Full; operator assertions, no external audit stated |
| 28 | Onbloc bridge | https://bridge.onbloc.xyz/ | — | Robots refused; not accessed |
| 29 | Mainnet deployments path | https://github.com/gnolang/gno/tree/chain/mainnet/misc/deployments/mainnet.gno.land | — | Robots denied; not accessed; deployed version unpinned |

Blocked or refused attempts are listed as gaps; they are not sources for any claim in this companion.

---

**Reminder.** This is research evidence with dated limits. It is not advice, and it does not decide any live asset, jurisdiction, licence or operator role described in the proposal. The synthetic reference selection is recorded separately as a product decision.
