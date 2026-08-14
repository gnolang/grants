# gnomemepad — Fair Bonding-Curve Launchpad for Gno.land

- **GitHub handle:** [sunny-0x42](https://github.com/sunny-0x42)
- **Email:** quoctoress0401@gmail.com  
- **Team:** **Ekudo Research**
- **Links**
  - **Live demo (Sapphire testnet):** https://gnomemepad-sapphire.netlify.app  
  - **GitHub (public monorepo):** https://github.com/sunny-0x42/gnomemepad  
  - **Backend API (private):** https://github.com/sunny-0x42/gnomemepad-backend  
  - **X / Twitter:** *To be added*  
  - **Primary on-chain package (Sapphire):**  
    `gno.land/r/g1mv0052e7r6s09f5t9xsqf00nj3tqsgt9dg52jr/gnomemepad/padv22`  
  - **Related modules (same deployer namespace):** hubv2, bond, meta, profile, pointsv2  
  - **Ecosystem:** [Gnoswap](https://gnoswap.io/) · [Adena](https://adena.app/) · [docs.gno.land](https://docs.gno.land)

**Open-source posture:**  
The **public** repository hosts on-chain Gno packages, deploy trees, scripts, docs, and (as committed) the web UI. The **chain-read API / Netlify functions backend** is maintained in a **private** repo (`gnomemepad-backend`) and is gitignored from the public monorepo. **On-chain Gno packages remain fully transparent** by Gno.land design. Under this grant, Ekudo Research commits to **openly publishing realm sources, pure packages, the economic specification, and builder documentation**.

**Grant request:** **USD $5,000** over **3 months**, milestone-based.

---

## Project summary

**gnomemepad** is a **permissionless fair-launch (memepad)** built natively in **Gnolang** on Gno.land. It is **live on Sapphire testnet** with a full product UI for create, trade, discovery, portfolio, creator fees, points, and leaderboard.

It implements a complete launch lifecycle on Gno:

1. **Create** — fair bonding-curve launch (no creator pre-mint)  
2. **Trade** — curve buy/sell with **WUGNOT** collateral (1:1 with GNOT; push-pay: wrap/fund pad → Buy, avoiding fragile multi-step Approve/`TransferFrom` UX)  
3. **Graduate** — when net raise reaches the threshold  
4. **List** — seed liquidity on **Gnoswap** (concentrated-liquidity pool; CreatePool fee via **GNS escrow** at create/list)  
5. **Discover & operate** — markets, token page (chart/trades), portfolio, creator hub, rewards/points, leaderboard, profile/meta

We position gnomemepad as both a **consumer dApp** and a **reference stack**: fee split (creator / protocol / remainder), prepaid WUGNOT credits (`ClaimWugnot` after overpay), multi-module hub (pad + bond + points), and a documented path from **bonding curve → Gnoswap**. The grant is not to invent the product from zero—it is to **harden, specify, open the on-chain kit, and document** so the Gno developer community can reuse the patterns.

**Current status:** End-to-end product on Sapphire (create → trade → graduate/list → post-list Gnoswap UX), iterative pad versions (`padv*`), Netlify-hosted UI + serverless chain API against Sapphire RPC.

---

### Goals and deliverables

#### Primary goals

1. Harden the Sapphire pad stack for **economic correctness** (especially free vs reserved WUGNOT inventory) and reliable **user claim** of overpay credit.  
2. Publish **on-chain sources + written specification + builder docs** as a public good for Gno developers.  
3. Expand **automated tests** for curve math, fees, last-fill/raise caps, and claim/list edges.  
4. Deliver a **mainnet / beta-mainnet readiness memo** aligned with network timeline (deploy when appropriate, not forced).  
5. Maintain a **stable public demo** on Sapphire for the full grant period.

#### Concrete deliverables (3-month scope)

| ID | Deliverable | Description |
|----|-------------|-------------|
| **D1** | Public on-chain package surface | Clear package paths, version notes, and published realm / pure-package sources (dedicated public tree or repo if the monorepo UI stays private). |
| **D2** | Technical specification | Tokenomics (supply, fee BPS, graduation), WUGNOT push-pay + prepaid credits, creator/protocol claims, GNS list escrow, graduate → Gnoswap list. |
| **D3** | Builder guide | Deploy a pad, Adena multi-msg Buy, list checklist, common panics, preflight (`FreeWugnot`, last-fill). |
| **D4** | Test expansion | Additional Gno tests for Buy/Sell caps, fee split, `ClaimWugnot` / `ClaimCreatorFees`, list-fee accounting. |
| **D5** | Inventory & claim UX | Address free-float shortfalls; reliable claim of overpay credit; API/UI preflight messages that match chain behavior. |
| **D6** | Mainnet readiness memo | Parameter freeze checklist, Init/protocol ops, residual risks—no mandatory mainnet ship if the network is not ready. |
| **D7** | Monthly public updates | Short written progress + live demo kept online. |

---

### Impact on gno.land’s developer ecosystem

1. **Reference consumer DeFi dApp** — A complete product path (realms + wallet multi-msg + external DEX), not only toy examples. Useful for builders coming from EVM/Solana launchpad models.  
2. **Reusable payment and listing patterns** — WUGNOT push-pay, prepaid credits, GNS CreatePool escrow, multi-version pad factory: applicable beyond memecoins (capped sales, fee vaults, raise-style apps).  
3. **Complementary to Gnoswap** — Graduated launches seed CL pools and drive swap demand; we do not replace concentrated liquidity—we standardize the **path into it**.  
4. **Transparent on-chain logic** — Gno’s model (readable realm code) means other teams can inspect live Sapphire packages and adapt them.  
5. **Testnet stress and feedback** — Create/trade intensity exercises RPC, gas, GRC20/WUGNOT, and wallet multi-msg—signal for core and wallet teams.  
6. **Documentation** — End-to-end case study filling the gap between official language docs and “how to ship a real dApp.”

---

### Timeline and milestones

**Duration:** 3 months  
**Total budget:** **USD $5,000**

| Month | Focus | Milestones | Tranche |
|-------|--------|------------|---------|
| **Month 1** | Spec + open on-chain packaging + test baseline | D1 underway, D2 draft published, D4 baseline tests for math/Buy edges; public update #1 | **$1,500** on kickoff / M1 acceptance |
| **Month 2** | Hardening + claims + builder guide | D3 v1, D5 free/reserved + `ClaimWugnot` verified; public update #2 | **$2,000** on M2 acceptance |
| **Month 3** | Docs freeze + readiness memo | D6 memo, D1/D3 polished, demo stable; final report | **$1,500** on final delivery |

**End-of-grant success criteria**

- Live Sapphire demo remains functional  
- Spec + builder guide published  
- On-chain sources/docs publicly navigable  
- Overpay credit and creator fee claim paths documented and working  
- Mainnet readiness memo delivered  

**Indicative budget use**

| Category | Share of $5,000 |
|----------|-----------------|
| Gno realm engineering & tests | ~45% |
| Spec, builder docs, OSS packaging of on-chain kit | ~30% |
| Claim / inventory preflight (API + minimal UI) | ~15% |
| Demo ops & reporting | ~10% |

---

## Contributions or related work for gno.land

We emphasize **demonstrated execution on Gno.land** over a long list of core-repository PRs.

**Completed / ongoing**

- Designed and deployed a **multi-module application** on **Sapphire**: pad factory & bonding curve, hub, bond, meta, profile, points.  
- Integrated **Adena** multi-message transactions and **Gnoswap** list/trade flows in a real product.  
- Iterated pad versions (`padv*`) based on testnet realities (payment UX, list-fee inventory, free vs reserved WUGNOT).  
- Operated a **public testnet frontend** (https://gnomemepad-sapphire.netlify.app) against Sapphire RPC for continuous validation.  
- Implemented user-facing flows that map to on-chain rights: **creator fee claim**, **prepaid WUGNOT claim (`ClaimWugnot`)** after overpay / last-fill.

**What we are not claiming**

- We are **not** long-time GnoVM / core monorepo maintainers.  
- We do **not** list Game of Realms “notable contributions” or core PRs we have not authored.

**Commitments during the grant**

- Publish **on-chain + pure-package** sources and the economic **specification** for community reuse.  
- File clear upstream issues when we hit platform, wallet, or Gnoswap edge cases.  
- Maintain public monthly progress notes.  
- Optionally contribute **docs/examples** once patterns are stable; register a **Game of Realms** contributor profile to track work transparently.

The strongest evidence of contribution is the **live Sapphire deployment and readable on-chain packages**, not a padded CV.

---

## Why are you and your team well-suited for this project?

**Ekudo Research** is a small, product-oriented team focused on **shipping usable applications on Gno.land**, not theory-only proposals.

Our lead engineer (**GitHub [sunny-0x42](https://github.com/sunny-0x42)**) designed and operates **gnomemepad** on Sapphire: Gnolang realm design, wallet multi-msg UX (Adena), Gnoswap graduation/listing, and the supporting chain-read API. We have already crossed the hardest barrier for a grant proposal—**a working full-stack dApp on the network**—so funding goes to **hardening, documentation, and open packaging of the on-chain kit**, not a greenfield experiment.

We are realistic about scope and budget:

- **$5,000 / 3 months** is intentionally lean, with testable milestones.  
- We keep the **production UI proprietary** while delivering ecosystem value through **open realms, pure packages, and builder docs**—the layer other developers actually fork and audit.  
- We accept mainnet timing constraints and will not force a reckless mainnet deploy; readiness is a documented deliverable.

**Contact:** Ekudo Research · quoctoress0401@gmail.com · GitHub @sunny-0x42  

---

## Referrals or examples of past work

| Item | Detail |
|------|--------|
| **Primary proof of work** | **gnomemepad on Sapphire** — https://gnomemepad-sapphire.netlify.app |
| **Code host** | https://github.com/sunny-0x42/gnomemepad |
| **On-chain** | `padv22` and related modules under deployer `g1mv0052e7r6s09f5t9xsqf00nj3tqsgt9dg52jr` on Sapphire |
| **Product surfaces** | Markets, Create, Token (curve + Gnoswap), Portfolio, Creator hub (fee claim), Rewards/points, Leaderboard, Guide |
| **X** | *To be added before or shortly after submission* |
| **Other past work** | Ekudo Research’s public track record for this application is centered on gnomemepad as an end-to-end Gno product. Additional prior projects can be shared on request during committee review. |

**One-line pitch for reviewers**

> We shipped a fair-launch pad on Gno Sapphire that graduates into Gnoswap; this grant funds open-sourcing the on-chain kit, hardening inventory and claims, and publishing builder documentation—for $5k over 3 months.

---

## Appendix A — Technical architecture (brief)

| Layer | Components |
|-------|------------|
| **On-chain** | `padv*` curve/factory, bond, hubv2, meta, profile, pointsv2; WUGNOT collateral; fee split; Gnoswap list hooks; `ClaimWugnot` / `ClaimCreatorFees` / protocol fee claim-push |
| **API** | Serverless/Node: markets, market detail, activity, portfolio, creator, leaderboard, pad WUGNOT preflight, Gnoswap FX & swap history |
| **Client** | React SPA + Adena multi-msg |
| **External** | Sapphire RPC, Gnoswap, Adena |

## Appendix B — Differentiation vs Gnoswap

gnomemepad is the **fair-curve raise and discovery** layer. **Gnoswap** remains the post-list trading venue. Our success increases Gnoswap pool count and volume; we do not replace concentrated liquidity.

## Appendix C — Open risks (honest)

- Free vs reserved WUGNOT accounting needs careful hardening before any mainnet freeze.  
- Charts may depend on external Gnoswap history APIs.  
- Mainnet deploy timing depends on network readiness, not only our code.  
- Closed UI means ecosystem reuse depends on **excellent on-chain packaging and documentation** (D1–D3).

## Appendix D — How we will track progress

- Public milestones / issues on https://github.com/sunny-0x42/gnomemepad (and the grants PR thread)  
- Monthly short written update  
- Live demo: https://gnomemepad-sapphire.netlify.app  
- Contact: **quoctoress0401@gmail.com**

---

## Submission checklist

1. Fork https://github.com/gnolang/grants  
2. Copy this file to `projects/gnomemepad.md`  
3. Add X/Twitter link when available  
4. Open a Pull Request  
5. Email **grants@tendermint.com** with the PR link and a short introduction  

---

*Proposal draft for the [Gno.land Grants Program](https://github.com/gnolang/grants) (template: `projects/TEMPLATE.md`).*  
*Team: **Ekudo Research** · Email: **quoctoress0401@gmail.com** · GitHub: **[@sunny-0x42](https://github.com/sunny-0x42)***
