# 369 Wallet — Native Mobile + AI Agent Wallet for Gno.land

- **GitHub**: [@leopard627](https://github.com/leopard627)
- **Email**: ali@alpsoft.io
- **Links**:
  - 369 Wallet website: https://www.369wallet.xyz
  - 369 Wallet on X: https://x.com/369Wallet
  - Google Play (live): https://play.google.com/store/apps/details?id=com.alpsoft.threesixninewallet
  - iOS TestFlight (live): public TestFlight invite available on request
  - APK direct: https://www.369wallet.xyz/downloads/369wallet.apk
  - Founder LinkedIn: https://www.linkedin.com/in/jihun-kim-556a32110/
  - Founder X: https://x.com/JihunWeb3

## Project Summary

**369 Wallet** is a production, App Store + Google Play distributed
mobile wallet that already supports 15 chains across EVM, Bitcoin,
Solana, XRP, Tron, Cosmos, Aptos, and Litecoin — and ships a built-in
**AI Agent** that signs every recommended on-chain action with an
**ERC-8004 trustless-agent** proof. To date this is the only consumer
wallet that turns "AI proposes a transaction" into a cryptographically
auditable on-chain record.

We propose to add **first-class Gno.land support to 369 Wallet**:

1. Native Gno address derivation, signing, send/receive, and tx history
   on the **Gno Beta Mainnet** plus testnet.
2. **GnoConnect** TxLink handling so any GnoConnect-aware dApp can
   trigger transactions through 369 Wallet from a mobile browser or QR.
3. A first-of-its-kind **AI Agent toolset for Gno** — `getGnoBalance`,
   `sendGno`, `queryRealm`, `callRealm`, `listGnoTxs`, `listValidators`
   — letting users perform Gno actions through chat ("send 10 GNOT to
   gno1abc…", "what's my balance on gno.land", "call hello() on
   r/demo/boards"), each one anchored on-chain via the same ERC-8004
   audit log we ship today.
4. An open-source **`@369wallet/gno-mobile-sdk`** — TypeScript wallet
   primitives (key derivation, signing, RPC, GnoConnect link parser,
   tx builder) packaged so any other React Native / Expo / mobile-web
   project can adopt Gno without re-implementing the stack.

### Why this matters now

The official documentation today lists **exactly one** third-party
Gno.land wallet — **Adena**, which is browser-extension only. No
native iOS/Android Gno wallet is available in either app store. The
mobile-first user — overwhelmingly the global majority — currently has
no way to hold or interact with Gno realms from their phone unless
they jump through a wrapped browser flow on a desktop.

369 Wallet is already on both stores with a production CI/CD pipeline
(EAS Build, EAS Update OTAs, Play Console + App Store Connect
automation). Adding Gno here means Gno reaches a real mobile audience
**on day one of merge**, not after a multi-quarter ramp.

The AI Agent layer is the second, larger lever: it turns Gno's
"transparent, auditable code" philosophy into a **transparent,
auditable AI** experience. Every realm call made on the user's behalf
is cryptographically signed by our registered agent (ERC-8004
identity) and anchored on-chain — the user (and anyone) can verify
exactly which model session caused which transaction. This is the
showcase application of trustless AI agents on a smart contract
platform, and Gno's deterministic Go VM is the right substrate for it.

## Goals and deliverables

### Phase 1 — Native Gno chain primitives (Month 1)

- [ ] **Key derivation**: secp256k1 over BIP-39 / BIP-44, derive
      `gno1…` bech32 addresses; integrate into 369's existing
      `mnemonic-store` (single-seed, multi-chain pattern proven across
      15 chains).
- [ ] **RPC client**: thin TypeScript wrapper over `tm2-js-client` for
      RN runtime (Hermes), routing through 369's iMac API as an
      optional cache/proxy layer for read calls (same pattern we use
      for Alchemy / Litecoinspace / etc.).
- [ ] **Read paths**: balance, account sequence, tx history (RPC
      `tx_search`), validator set listing.
- [ ] **Local-tx merge**: integrate Gno entries into 369's unified
      Activity tab so a user sees Gno alongside ETH/SOL/BTC in one
      timeline.
- [ ] **Token catalog entry**: add GNOT to the wallet's built-in
      catalog with logo and metadata.

**Deliverable:** running on internal TestFlight + Play Internal
Testing track, observably reading Gno Beta Mainnet.

### Phase 2 — Send / receive + on-device signing (Month 2)

- [ ] **Transaction builder**: implement the Gno SDK tx envelope
      (Amino-style) in pure TypeScript so no native bridging is
      needed.
- [ ] **Signing**: use 369's existing `usePasscodeRequest` gate —
      every Gno send requires passcode/biometric, no exceptions,
      consistent with Trust/MetaMask/Phantom bar.
- [ ] **Send UI**: amount input, recipient address book, fee preview,
      review-and-confirm sheet matching our existing per-chain
      patterns.
- [ ] **Receive UI**: QR + address copy + share, same primitives as
      other chains.
- [ ] **Broadcast + status tracking**: pending → confirmed transitions
      with explorer linkout to Gnoscan.
- [ ] **Offline safety**: tx can be signed without network (same as
      the rest of the wallet); broadcast deferred. Documented in our
      `feedback_offline_mode_must_work` invariant.

**Deliverable:** end-to-end send/receive on Beta Mainnet from a real
mobile device, demoed publicly.

### Phase 3 — GnoConnect dApp connector (Month 3)

- [ ] **TxLink parser**: handle `gnoconnect:` URL scheme on iOS/Android
      (custom URL scheme + universal links), parse function call +
      args + chain/RPC metadata.
- [ ] **QR scanner**: in-wallet QR scanner for GnoConnect TxLinks,
      same UX pattern as WalletConnect URI scan.
- [ ] **Approval sheet**: domain check (`gnoconnect:txdomains`),
      function name + args display, fee preview, passcode confirm.
- [ ] **GnoConnect metadata fetcher**: HTML `<meta>` + HTTP header
      sniffing for `gnoconnect:rpc` / `chainid` / `txdomains` so the
      wallet auto-trusts only the dApp's declared origin.
- [ ] **Session log**: store GnoConnect interactions in our existing
      Settings → WalletConnect-equivalent surface so users can audit
      what dApps touched their wallet.

**Deliverable:** scan a TxLink from any GnoConnect-compliant dApp on
desktop → 369 Wallet on phone → signed + broadcast.

### Phase 4 — AI Agent tools for Gno (Month 4)

This is the unique, hard-to-replicate piece. 369 Wallet today exposes
14 AI tools (sendArc, bridgeQuote, bridgeExecute, listApprovals,
revokeApproval, listPendingBridges, resumeBridge, listWcSessions,
disconnectWcSession, listAgentActivity, etc.), each one anchored on
Arc Testnet via ERC-8004 ValidationRegistry. We extend the same
pattern to Gno:

- [ ] `getGnoBalance(address)` — read-only.
- [ ] `getGnoTxHistory(address, limit)` — read-only.
- [ ] `sendGno(to, amount, memo?)` — propose-only; on-device passcode
      gates execution. Per-tx POC cap configurable.
- [ ] `queryRealm(path, fn, args)` — call an exported pure / read-only
      function (`vm/qeval`); no signature.
- [ ] `callRealm(path, fn, args, send?)` — propose-only mutating call
      to a realm; same passcode gate; tx anchored.
- [ ] `listGnoValidators()` — read-only.
- [ ] **Audit anchor**: every successful action triggers the existing
      `anchorAgentAction` fire-and-forget helper — the AI Agent's
      EIP-712 recommendation hash + Gno action tx hash land in the
      ValidationRegistry, viewable on the existing Settings → Agent
      Activity timeline we shipped this week.
- [ ] **Agent system-prompt rules**: a Gno-scoped rule block in the
      assistant's system prompt (consistent with our existing 21
      operational rules) — covers safe defaults, address format
      validation, "ask before mutating", explicit per-realm function
      whitelisting for the POC.

**Deliverable:** chat-driven Gno actions, with a live demo at the end
of the month showing "send 5 GNOT to gno1abc… and post 'hello' to
r/demo/boards" executing as two consented, anchored transactions.

### Phase 5 — Open-source mobile SDK + i18n + polish (Months 5-6)

- [ ] **`@369wallet/gno-mobile-sdk`**: extract the Phase 1-3 modules
      (key derivation, signing, RPC, GnoConnect handler, tx builder)
      into a standalone TypeScript package published to npm and
      mirrored on GitHub under a permissive license (Apache-2.0).
      Includes Expo / RN compatibility shims, browser shims, and
      Hermes-compatible crypto.
- [ ] **i18n parity**: 5 locales (en/ko/ja/zh/es) for every Gno UI
      string. 369's i18n bot already enforces parity; no extra cost.
- [ ] **Documentation**: integration guide, sample apps (a minimal
      Expo demo and a vanilla TypeScript browser demo), troubleshooting
      notes.
- [ ] **Public release**: App Store + Google Play production track,
      versioned release, announcement on @369Wallet + LinkedIn + the
      gno.land funding-program report.

**Deliverable:** anyone building a mobile or browser wallet/dApp can
`npm install @369wallet/gno-mobile-sdk` and add Gno support in a
weekend.

## Impact on gno.land's developer ecosystem

1. **Distribution.** Gno gets onto the world's two largest app stores
   (App Store + Play Store) inside one quarter via a wallet that is
   already there. No new infrastructure, no new auth, no per-platform
   ramp-up.

2. **A mobile reference implementation.** The Adena team has shipped
   the gold standard for browser. We ship the gold standard for
   mobile + AI. Every other team that wants to add Gno to a phone app
   can fork or `npm install` our SDK — we close the "no native mobile
   wallet" gap permanently.

3. **The AI-agent showcase.** The Gno blog has multiple pieces about
   transparent, auditable code. We give Gno's narrative the matching
   *transparent, auditable AI* story: every AI-driven Gno action is
   cryptographically signed and posted to chain via ERC-8004. This is
   the strongest demo a team can take to a conference or to
   regulators in 2026.

4. **Reusable contributions.** Every primitive we build (key
   derivation, signing, tx builder, GnoConnect handler, AI-tool
   scaffolding) is packaged for reuse. The Gno community gets a
   permissively-licensed mobile SDK that didn't exist before.

## Timeline and milestones

| Month | Milestone                                            | Status update channel |
| ----- | ---------------------------------------------------- | --------------------- |
| 1     | Chain primitives + read paths on Beta Mainnet        | weekly PR + tweet     |
| 2     | Send / receive end-to-end on real device             | demo video            |
| 3     | GnoConnect TxLink handling + scanner                 | live testnet demo     |
| 4     | AI Agent tools + ERC-8004 audit anchoring            | recorded chat demo    |
| 5     | `@369wallet/gno-mobile-sdk` published                | npm + GitHub release  |
| 6     | Public iOS + Android release; case study writeup     | blog post + thread    |

Progress is tracked in public on the
[369wallet-releases](https://github.com/leopard627/369wallet-releases)
repo and announced from [@369Wallet](https://x.com/369Wallet).
Quarterly written status update will be submitted to the gno.land
funding-program report.

## Contributions or related work for gno.land

This is our first dedicated Gno.land contribution. During the
preparation of this proposal we completed structural research on the
Gno chain architecture (tm2), the GnoConnect TxLink standard, the
`tm2-js-client` / `gno-js-client` libraries, and the existing
third-party wallet landscape — confirming both the gap (no native
mobile wallet, no AI-agent integration) and the technical feasibility
of the milestones below.

## Why are you and your team well-suited for this project?

**Track record on the exact shape of this problem.** 369 Wallet is
already a production, multi-store mobile wallet supporting 15 chains
— each one required exactly the same scope as Gno (key derivation,
RPC, tx envelope, signing, send/receive UI, AI tool wiring, i18n,
release). We have run the playbook 15 times in the past 18 months.
Adding the 16th chain is muscle memory, not a R&D project.

**AI agent is not a toy at 369.** We ship the only consumer wallet
with an **ERC-8004 trustless-agent integration**. Open-source
contracts are deployed at:
- AgentIdentityRegistry: `0xAceB520444ddeDec663277FC866ab77E8085918e`
- ValidationRegistry: `0x148336926e6F21A2EC63B47BA31dD0B08E538b91`
- Repo: https://github.com/369wallet/369-agnet-8004

Every AI-driven send / bridge / swap / revoke / mint already lands as
a verifiable on-chain record. Extending the same registry to Gno
takes weeks, not quarters, because the hard work (the EIP-712
signing pipeline, the validation submission, the local activity
store, the audit UI) is shipped.

**Operational maturity.** v1.0.29 currently in production. 29 release
cycles, Crashlytics-clean, 5-locale i18n parity, OTA pipeline with
runtime/binary version preflight, EAS Build + EAS Submit + Play
Console API + App Store Connect API all wired. None of this needs
re-invention to add Gno; it is overhead-free distribution.

**Founder, Jihun Kim (Alpsoft, South Korea).** Builder of 369 Wallet
end-to-end. Previously shipped **TikPay** ([https://tikpay.live](https://tikpay.live))
— a production zkLogin implementation on Sui that proved out the
"social-login → on-chain action" path now being proposed for GnoKit.
Background: TypeScript, Rust, Solidity, Python; Web3 + mobile +
back-end full stack. 232 public repos on GitHub, 1.3k stars.

## Referrals or examples of past work

- **369 Wallet (live):**
  - Google Play: https://play.google.com/store/apps/details?id=com.alpsoft.threesixninewallet
  - Website: https://www.369wallet.xyz
  - X: https://x.com/369Wallet
- **369 Agent (ERC-8004 implementation, open source):**
  - https://github.com/369wallet/369-agnet-8004
- **TikPay (zkLogin on Sui):**
  - https://tikpay.live
- **Founder GitHub:** https://github.com/leopard627
- **Founder LinkedIn:** https://www.linkedin.com/in/jihun-kim-556a32110/
- **Founder X:** https://x.com/JihunWeb3

## Budget

Open to scoping with the review committee. As a reference: we are
proposing a six-month, single-team build with three core deliverables
(native mobile chain support, GnoConnect dApp connector, AI agent
toolset) plus an open-source SDK. Comparable scope grants in the
program's history have ranged USD 60K–120K; we are happy to fit any
shape that the committee finds appropriate. We can also break the
scope into smaller, separately-funded phases (chain primitives →
GnoConnect → AI agent → SDK) if that suits the committee's process.
