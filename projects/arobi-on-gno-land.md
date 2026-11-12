# Arobi on gno.land: pay in GNOT, anchor evidence on gno.land

- GitHub handle: PossumXI
- Email: gaetano@aura-genesis.org
- Links: https://aura-genesis.org · https://github.com/PossumXI

## Project summary

Arobi Technology Alliance, Inc. builds assurance for AI work: software that checks identity, permission and rules
before an important action runs, and keeps evidence of what happened. This project brings Arobi's products and their
users to gno.land in two ways:

1. **Pay in GNOT.** A gno.land realm where a person will pay GNOT for a named Arobi service; Arobi's services will
   check the payment and grant the service. Whisper, Arobi's private messenger, will be the first service to accept GNOT.
2. **Anchor evidence on gno.land.** A realm that will record 32-byte digests of Arobi evidence records with the block
   height, so anyone can later check that a record existed by that height on gno.land.

Nothing will be bridged, and no token wrapped or minted anywhere else. Payments stay on gno.land; only the proof of a
payment or of an anchor is used outside it.

### Goals and deliverables

The deliverables are Arobi's own work and are not released under an open-source licence. The realms will be deployed
on gno.land, where, like every realm, their source can be read on chain, and they will be public services that anyone
with a gno.land wallet can call.

| # | Deliverable | What it is |
| --- | --- | --- |
| D1 | Pay-for-service realm | Arobi's service offers, each with a price in ugnot. A payment of exactly the price records a receipt and emits an event, and the payment goes to Arobi's wallet in the same call, so the realm never holds a balance. |
| D2 | Anchoring realm | Records a 32-byte digest with the caller and the height and emits an event. A small fee and a per-caller rate limit keep it from being spammed. |
| D3 | GNOT payments in an Arobi product | Whisper accepts GNOT for a paid feature: first on a gno.land test network, then on mainnet. |
| D4 | Evidence anchoring from Arobi products | Arobi evidence records are anchored on gno.land on a regular schedule: first on a test network, then on mainnet. |
| D5 | User documentation | Public pages on aura-genesis.org and the realms' gnoweb pages: how to pay for an Arobi service with GNOT from a gno.land wallet, and how to look up an anchor. |
| D6 | Public progress reports | A short report at the end of each milestone, with the realm addresses and on-chain counts of payments and anchors. |

### Impact on gno.land's developer ecosystem

- **Real payments in GNOT.** Arobi's users get a reason to hold and use GNOT, starting with Whisper. Every payment is
  a transaction on gno.land.
- **Regular on-chain activity.** Evidence anchoring from Arobi's products adds steady, fee-paying transactions.
- **A worked example of an off-chain service charging in GNOT.** The realms' behaviour is visible on chain and
  documented on gnoweb, so builders can see a commercial service accept GNOT without holding anyone's funds in a
  realm.
- **New users.** Arobi's products put a gno.land wallet in front of people who have never used one, with step-by-step
  instructions.

### Timeline and milestones

Sixteen weeks from the start date. Progress is tracked in public on this pull request: an update at the end of each
milestone, with the realm addresses and on-chain counts.

| Milestone | Weeks | Done when |
| --- | --- | --- |
| M1 Realms on a test network | 1–4 | D1 and D2 deployed on a gno.land test network with their gnoweb pages; reviewers can pay an offer and anchor a digest. |
| M2 Whisper accepts GNOT on the test network | 5–8 | D3 working end to end on the test network. |
| M3 Anchoring and documentation | 9–12 | D4 running on the test network; D5 published. |
| M4 Review and mainnet | 13–16 | An external security review of both realms, with its findings fixed; both realms, D3 and D4 on mainnet; a D6 report for every milestone. |

Requested amount: **USD 50,000**, in four payments of USD 12,500, one at the end of each milestone. Payment in GNOT to
the address below, at the rate of the payment date, is welcome, or in another form the program prefers.

Payment address on gno.land: `g1cr24h5ljhm740vkejtetmlepcxyu4kyl9l5wdd` (Arobi Technology Alliance, Inc.)

## Contributions or related work for gno.land (if applicable)

None upstream yet; this would be our first. We have written both realms and tested them with gno v1.7.0 on a local
network.

## Why are you and your team well-suited for this project?

Arobi Technology Alliance, Inc. builds assurance for AI work. Evidence that can be checked later, by someone who does
not have to trust us, is the centre of what we do.

- Gaetano Comparcola, founder and CEO, superintelligence researcher, leads the project.
- Arobi carries out private research on verifiable evidence and anchoring. It is not part of this proposal and is not
  disclosed here.
- We ship software people use: a cloud workspace, a desktop app, a terminal coding agent, a Linux desktop and a
  private messenger. The work in this proposal goes into those products.
- Every release we ship is verified before it goes out. The realms get the same treatment, plus the external review
  in M4.

## Referrals or examples of past work

- https://aura-genesis.org: Arobi's products and research pages.
- The founder's essays on governing autonomous systems and on memory for AI assistants, linked from the Research page.
- Further references on request.
