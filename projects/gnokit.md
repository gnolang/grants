# GnoKit - Web3 Developer Platform for Gno.land (Like Enoki for Sui)

- **GitHub**: [@leopard627](https://github.com/leopard627)
- **Email**: ali@alpsoft.io
- **Links**:
  - X (Twitter): https://x.com/JihunWeb3
  - LinkedIn: https://www.linkedin.com/in/jihun-kim-556a32110/
  - TikPay (zkLogin Implementation): https://tikpay.live

## Project Summary

**GnoKit** is a comprehensive Web3 developer platform for Gno.land—similar to what **Enoki** is for Sui. It provides everything developers need to build mainstream-ready applications: social login authentication, sponsored transactions, and plug-and-play SDKs.

### What is Enoki?

Enoki (by Mysten Labs) revolutionized Sui development by offering:
- **zkLogin**: Social login wallet creation
- **Sponsored Transactions**: Gas fee abstraction for users
- **Developer APIs**: Simple integration for any application

**Result**: Hundreds of thousands of users onboarded, 17% → 42% conversion rate improvement.

### GnoKit: Enoki for Gno.land

We propose to build the equivalent infrastructure for Gno.land:

| Feature | Enoki (Sui) | GnoKit (Gno.land) |
|---------|-------------|-------------------|
| Social Login | zkLogin | GnoLogin (ZKP-based OAuth) |
| Gas Abstraction | Sponsored Txs | Sponsored Transactions |
| Developer SDK | Enoki SDK | GnoKit SDK |
| Dashboard | Enoki Portal | GnoKit Dashboard |

**The Problem:**

1. **For Users**: Web3 onboarding is painful—seed phrases, gas fees, complex wallets
2. **For Developers**: Building user-friendly dApps requires months of infrastructure work
3. **For Gno.land**: Without developer tools, ecosystem growth is limited

**Our Solution:**

GnoKit provides a complete developer platform:
- **GnoLogin**: Users sign in with Google, Apple, Discord, Twitch, Microsoft, Meta, LinkedIn, and more—wallet created in 30 seconds
- **Sponsored Transactions**: Users never see gas fees; developers pay on their behalf
- **Plug-and-Play SDK**: Add 3 lines of code to integrate GnoKit
- **Developer Dashboard**: Manage apps, monitor usage, configure settings

### Why Gno.land Needs This

1. **Ecosystem Catalyst**: Every dApp benefits from GnoKit—games, DeFi, social, NFTs
2. **Developer Magnet**: Developers choose platforms with better tooling
3. **User Acquisition**: Mainstream users can join without crypto knowledge
4. **Competitive Parity**: Sui has Enoki; Gno.land needs GnoKit

### Our Expertise

We've built with Enoki/zkLogin on Sui through TikPay:
- Production zkLogin integration with multiple OAuth providers
- Sponsored transaction implementation
- Biometric authentication (Face ID/fingerprint)
- Non-custodial key management
- Real user adoption and feedback

### Goals and Deliverables

#### Phase 1: Research & Architecture (Months 1-3)
- [ ] Analyze Gno.land's cryptographic primitives and transaction model
- [ ] Design ZKP circuits compatible with Gno.land
- [ ] Architect OAuth integration flow for 10+ providers (Google, Apple, Discord, Twitch, Microsoft, Meta, LinkedIn, X/Twitter, Kakao, LINE)
- [ ] Design sponsored transaction mechanism for Gno.land
- [ ] Define security model and threat analysis
- [ ] Publish technical specification document

#### Phase 2: Core Platform Development (Months 4-8)
- [ ] Implement ZK circuits for JWT verification (GnoLogin)
- [ ] Build ephemeral key pair generation system
- [ ] Develop salt management and key derivation
- [ ] Create ZKP proving service infrastructure
- [ ] Implement on-chain verifier contracts in Gnolang
- [ ] Build sponsored transaction relay service
- [ ] Implement gas fee abstraction layer

#### Phase 3: SDK & Developer Tools (Months 9-12)
- [ ] Build GnoKit JavaScript/TypeScript SDK
- [ ] Create React hooks and components library (`@gnokit/react`)
- [ ] Develop mobile SDK (iOS/Android)
- [ ] Build GnoKit Developer Dashboard
- [ ] Create app management and analytics portal
- [ ] Deploy on Gno.land testnet

#### Phase 4: Security & Launch (Months 13-15)
- [ ] Third-party cryptographic audit
- [ ] Security audit of smart contracts
- [ ] Bug bounty program
- [ ] Mainnet deployment
- [ ] Developer documentation and tutorials
- [ ] Developer onboarding program

### Final Deliverables

1. **GnoLogin (Social Authentication)**
   - ZK circuits for OAuth JWT verification
   - On-chain verifier contracts (Gnolang)
   - ZKP proving service infrastructure
   - Support for 10+ OAuth providers: Google, Apple, Discord, Twitch, Microsoft, Meta, LinkedIn, X/Twitter, Kakao, LINE

2. **Sponsored Transactions**
   - Gas fee abstraction for end users
   - Relay service for transaction submission
   - Developer-controlled sponsorship policies
   - Usage tracking and billing

3. **GnoKit SDK**
   - JavaScript/TypeScript SDK (`@gnokit/core`)
   - React component library (`@gnokit/react`)
   - Mobile SDKs (iOS/Android)
   - Simple 3-line integration

4. **Developer Dashboard**
   - App registration and API key management
   - Usage analytics and monitoring
   - Sponsorship budget management
   - User management tools

5. **Documentation & Support**
   - Comprehensive API reference
   - Integration tutorials
   - Example applications
   - Developer community support

### Impact on Gno.land's Developer Ecosystem

1. **Removes #1 Barrier to Adoption**
   - Users can join Gno.land dApps with accounts they already have
   - No gas fees for end users (sponsored transactions)
   - Conversion rates can improve from ~17% to 42%+ (based on Sui/Enoki data)

2. **Developer Experience Revolution**
   - 3-line SDK integration vs months of infrastructure work
   - Focus on product, not wallet integration
   - Managed infrastructure reduces operational burden

3. **Every dApp Benefits**
   - GnoKit is horizontal infrastructure—all Gno.land applications can use it
   - Games, DeFi, social apps, NFT platforms all get easier onboarding
   - Network effects: more GnoKit apps = more Gno.land users

4. **Competitive Positioning**
   - Sui has Enoki → Gno.land has GnoKit
   - Attracts developers who prioritize user experience
   - Positions Gno.land as developer-friendly chain

5. **Open Source Contribution**
   - All code will be open-sourced under permissive license
   - Community can extend to support additional OAuth providers
   - Reference implementation for Web3 developer platforms

### Timeline and Milestones

| Phase | Duration | Key Milestones | Budget Allocation |
|-------|----------|----------------|-------------------|
| Phase 1 | Months 1-3 | Technical spec, architecture finalized | $150,000 (15%) |
| Phase 2 | Months 4-8 | GnoLogin + Sponsored Txs on testnet | $400,000 (40%) |
| Phase 3 | Months 9-12 | SDK + Dashboard complete, beta launch | $250,000 (25%) |
| Phase 4 | Months 13-15 | Audits complete, mainnet launch | $200,000 (20%) |

**Total Requested Budget: $1,000,000 USD**

### Budget Breakdown

- Core Platform (GnoLogin + Sponsored Txs): 40% ($400,000)
- SDK & Developer Tools: 25% ($250,000)
- Security Audits (Crypto + Smart Contract): 20% ($200,000)
- Infrastructure & Operations: 10% ($100,000)
- Documentation & Developer Relations: 5% ($50,000)

## Contributions or Related Work for Gno.land

This will be our first direct contribution to Gno.land. Our relevant experience includes:

- **TikPay**: Production zkLogin implementation on Sui
  - Multi-provider OAuth integration (Google, Apple, etc.)
  - Biometric authentication flow
  - Non-custodial wallet management
  - Live at https://tikpay.live

- **PRX Market**: DeFi application with complex smart contract architecture
  - Demonstrates ability to build production blockchain applications
  - Experience with oracle integration and time-sensitive operations

## Why Are You and Your Team Well-Suited for This Project?

### Company: Alpsoft Inc. (South Korea)

| Role | Background |
|------|------------|
| CEO/Founder (Jihun Kim) | Former Senior Backend Developer at **Coinone** (Top 3 Korean Crypto Exchange). Deep experience in authentication systems, security infrastructure, and high-throughput backend systems |
| Senior Developer | Full-stack blockchain development, cryptography implementation |
| Senior Developer | Smart contract security, ZK circuit development |

### Why We're Qualified

1. **Production zkLogin Experience**: We've already shipped zkLogin through TikPay—we understand the challenges and edge cases

2. **Exchange-Grade Security Background**: Coinone experience means we understand authentication security at scale

3. **Full-Stack Capability**: We can deliver the complete stack—from ZK circuits to user-facing SDKs

4. **Track Record**:
   - PRX Market: $9.88M+ volume, 689+ rounds
   - TikPay: Live zkLogin implementation
   - 2025 Base Token Korea Hackathon Finalist

### Technical Expertise

- **Cryptography**: Zero-knowledge proofs, JWT/OAuth protocols
- **Smart Contracts**: Move (Sui), Solidity, expanding to Gnolang
- **Frontend**: Next.js, React, TypeScript
- **Backend**: Node.js, Go, TypeScript
- **Infrastructure**: AWS, distributed systems

## Referrals or Examples of Past Work

### TikPay - zkLogin Implementation (Live)
- **Website**: https://tikpay.live
- **Blockchain**: Sui
- **Status**: Production zkLogin integration

**What We Built:**
- Complete zkLogin flow with multiple OAuth providers
- Biometric authentication (Face ID/fingerprint)
- Ephemeral key management
- Non-custodial wallet architecture
- 30-second onboarding flow

**Key Learnings Applied to GnoLogin:**
- Multi-provider OAuth quirks and edge cases
- ZKP proving service optimization
- Salt management best practices
- Mobile-first authentication UX

---

### PRX Market - DeFi Application (Live on Testnet)
- **Website**: https://prxmarket.xyz
- **Blockchain**: Sui Testnet

**Metrics:**
| Metric | Value |
|--------|-------|
| Total Trading Volume | $9.88M+ USDC |
| Treasury Balance (TVL) | $294K USDC |
| Market Rounds Completed | 689+ |

---

### Why This Project Matters

Developer platforms like Enoki are becoming essential infrastructure for modern blockchains. Sui's ecosystem exploded after Enoki launched—hundreds of thousands of users onboarded through social login, and developer adoption accelerated.

Gno.land has innovative smart contract technology. Now it needs equally innovative developer tooling. **GnoKit will be that tooling.**

We have:
- Production experience with Enoki/zkLogin (TikPay)
- Deep understanding of developer needs
- Track record of shipping blockchain products

Let's make Gno.land the most developer-friendly blockchain.

---

**Contact**: ali@alpsoft.io | [@JihunWeb3](https://x.com/JihunWeb3)
