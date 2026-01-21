# Gnomo DEX - Gno.land Grant Proposal

## Applicant Information

- **Project Name:** Gnomo DEX
- **Applicant Name:** Jim Wood
- **Contact Email:** tazmaan@gmail.com
- **GitHub:** https://github.com/tazmaan-defi/gnomo
- **Discord:** tazmaan

---

## Project Summary

**Gnomo DEX** is a fully on-chain decentralized exchange (DEX) built natively on Gno.land, featuring both a traditional **V2 AMM (Constant Product)** and an advanced **Concentrated Liquidity Market Maker (CLMM)** inspired by Uniswap v3.

This is one of the first production-ready DEXs on Gno.land, demonstrating that complex DeFi primitives can be built entirely in Gno. The project includes:

- **V2 AMM Contract:** Classic x*y=k constant product pools with configurable fee tiers
- **CLMM Contract:** Concentrated liquidity with tick-based positions, sqrt-price math, and fee collection
- **Full-Featured Frontend:** React/Next.js interface with wallet integration (Adena), real-time quotes, price charts, and position management
- **Multi-Pool Routing:** Automatic best-rate discovery across V2 and CLMM pools

### Why This Matters for Gno.land

1. **Proves DeFi Viability:** Demonstrates that sophisticated financial primitives work on Gno
2. **Liquidity Infrastructure:** Essential building block for any blockchain ecosystem
3. **Reference Implementation:** Well-documented code that other developers can learn from
4. **User Onboarding:** DEXs drive user adoption and transaction volume

---

## Goals & Deliverables

### Phase 1: Core DEX (Completed)
- [x] V2 AMM smart contract with liquidity management
- [x] CLMM smart contract with concentrated liquidity positions
- [x] Proper sqrt-based CLMM math (Uniswap v3 style)
- [x] Frontend with Adena wallet integration
- [x] Multi-pool quote aggregation and routing
- [x] Price charts and volume tracking
- [x] Deployed to Gno staging testnet

### Phase 2: Production Readiness (In Progress)
- [ ] Security audit and bug fixes
- [ ] Remove test functions (MintTestTokens) for mainnet
- [ ] Gas optimization
- [ ] Comprehensive test suite
- [ ] Documentation and developer guides

### Phase 3: Advanced Features (Planned)
- [ ] Limit orders
- [ ] Multi-hop routing (A→B→C swaps)
- [ ] Liquidity mining / incentive programs
- [ ] Analytics dashboard
- [ ] Mobile-responsive UI improvements

### Phase 4: Ecosystem Integration (Planned)
- [ ] GRC-20 token standard integration
- [ ] Price oracle for other Gno dApps
- [ ] SDK/library for other developers to integrate swaps
- [ ] Governance token and DAO structure

### Phase 5: Cross-Chain (Future - Pending IBC)
- [ ] IBC integration when available on gno.land
- [ ] Skip Go API integration for cross-chain swaps and bridging
- [ ] Multi-chain liquidity aggregation

---

## Impact on the Developer Ecosystem

### For Gno.land Developers
- **Reference Code:** Production-quality Gno smart contracts demonstrating:
  - Safe integer math patterns
  - Complex state management (positions, ticks, liquidity)
  - Multi-contract architecture
  - Banker/coin integration patterns
- **Reusable Libraries:** Price oracle functionality, sqrt math, safe math utilities
- **Integration Point:** Other dApps can integrate swap functionality

### For Gno.land Users
- **Essential Infrastructure:** Every blockchain needs a DEX for token liquidity
- **Familiar UX:** Interface patterns users know from Uniswap/other DEXs
- **Low Barrier:** Easy onboarding for DeFi users from other chains

### For Gno.land Ecosystem
- **TVL Growth:** DEXs attract liquidity and capital to the ecosystem
- **Transaction Volume:** Swaps generate network activity and fees
- **Proof Point:** Shows investors and developers that Gno is DeFi-ready

---

## Timeline & Milestones

| Milestone | Deliverable | Timeline |
|-----------|-------------|----------|
| M1 | Core V2 AMM + CLMM contracts deployed to testnet | **Completed** |
| M2 | Frontend with full swap/liquidity UI | **Completed** |
| M3 | Security fixes, sqrt-math corrections, audit prep | **Completed** |
| M4 | Mainnet deployment (remove test functions) | 2 weeks |
| M5 | Documentation + developer guides | 3 weeks |
| M6 | Multi-hop routing implementation | 6 weeks |
| M7 | Limit orders + advanced features | 10 weeks |
| M8 | SDK release for ecosystem integration | 12 weeks |

---

## Budget Request

| Item | Cost | Notes |
|------|------|-------|
| Smart Contract Development (Completed) | $12,000 | V2 AMM + CLMM with Uniswap v3-style sqrt-math |
| Frontend Development (Completed) | $7,000 | React/Next.js UI with Adena wallet integration |
| Phase 2: Production Readiness | $5,000 | Testing, mainnet prep, documentation |
| Phase 3: Advanced Features | $7,000 | Multi-hop routing, limit orders, analytics |
| Infrastructure & Hosting | $1,500 | RPC access, Vercel hosting (12 months) |
| Ongoing Maintenance | $2,500 | Bug fixes, updates (6 months post-launch) |
| **Total** | **$35,000** | |

*Budget reflects developer time for completed and planned work.*

---

## Team Background & Qualifications

### Team Members
- **Jim Wood** - Lead Developer - Full-stack blockchain developer with extensive DeFi experience

### Relevant Experience

**Vitruveo Exchange (vitruveo.exchange)**
- Built and deployed a full DEX on the Vitruveo blockchain
- Implemented smart routing, bridge integrations, and revenue sharing mechanisms
- Ran complete infrastructure: validator node, RPC node, and subgraph indexer
- Project remains live and operational

**Core Team Experience at Multiple DEXs**
- **Arbidex** - Core team member
- **Baseswap** - Core team member
- **Swapmode** - Core team member
- **Omni Exchange** - Core team member

Responsibilities across these projects included:
- User support and community management
- Bug testing and QA
- Development of operational scripts for project management and finances
- Cross-functional collaboration with development teams

### Technical Skills
- Smart contract development (Solidity, Gno)
- Frontend development (React, Next.js, TypeScript)
- DeFi mathematics (AMM curves, concentrated liquidity, sqrt-price math)
- Infrastructure operations (validator nodes, RPC nodes, subgraphs)
- Full-stack dApp development

### Why We Can Execute
- Already built and deployed working V2 and CLMM contracts on Gno.land
- Demonstrated ability to implement complex DeFi math correctly (Uniswap v3 style CLMM)
- Proven track record building and operating production DEXs
- Experience running blockchain infrastructure
- Active engagement with Gno.land community and tooling

---

## Technical Architecture

### Smart Contracts (Gno)

```
r/gnomo/           # V2 AMM
├── gnomo.gno      # Pool management, swaps, liquidity
└── Types: Pool, LP balances

r/clmm/            # Concentrated Liquidity
├── clmm.gno       # Positions, ticks, sqrt-math swaps
└── Types: CLMMPool, Position, TickInfo
```

### Key Technical Achievements
- **Integer sqrt implementation** for precise CLMM math without floating point
- **Tick-based liquidity tracking** with proper cross-tick handling
- **Safe math throughout** preventing overflow/underflow
- **Gas-efficient design** minimizing on-chain computation

### Frontend Stack
- Next.js 14 / React
- Adena wallet SDK integration
- Real-time RPC queries
- LocalStorage price/volume history

---

## Links & Resources

- **Live Demo:** https://gnomo-eosin.vercel.app/
- **GitHub Repository:** https://github.com/tazmaan-defi/gnomo
- **Contract (V2):** `gno.land/r/gnomo/dex3`
- **Contract (CLMM):** `gno.land/r/gnomo/clmm4`

---

## Previous Work / References

### Live Projects
- **Vitruveo Exchange:** https://vitruveo.exchange - Full-featured DEX with smart routing, bridges, and revenue sharing

### DeFi Protocol Experience
- Core team contributor to Arbidex, Baseswap, Swapmode, and Omni Exchange
- Hands-on experience with AMM design, liquidity management, and protocol operations

### Infrastructure Operations
- Operated validator node, RPC node, and subgraph for Vitruveo blockchain
- Production experience with blockchain infrastructure at scale

---

## Contact

For questions about this proposal, please reach out:
- GitHub: https://github.com/tazmaan-defi
- Discord: tazmaan
- Email: tazmaan@gmail.com

---

*Submitted to the [Gno.land Grants Program](https://github.com/gnolang/grants)*
