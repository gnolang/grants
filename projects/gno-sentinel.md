# Gno Sentinel

- GitHub handle: **SuperSmile0426**
- Email: **professional.akiranakao@gmail.com**
- Links:
  - Project repository: https://github.com/SuperSmile0426/gno-sentinel
  - GitHub profile: https://github.com/SuperSmile0426

## Project summary

Gno Sentinel is an open-source security tool for Gno.land realms.

The first part of the project is a package-aware static analyzer for `.gno` source code. It flags Gno-specific security patterns for review and produces human-readable and JSON findings that can be used locally or in CI.

The next part is automatic monitoring of newly published packages. Sentinel will use existing Gno.land indexing infrastructure to detect package publications, pass package metadata to a separate source-resolution step, run the analyzer, and keep a history of findings.

The Gno grants README lists real-time contract monitoring and auditing as an example project. Gno Sentinel is focused on that area.

A working v0.2 prototype already exists. The current implementation includes:

- package-aware AST analysis across multiple `.gno` files;
- CLI and JSON output;
- severity-based CI failure thresholds;
- vulnerable/fixed regression fixtures;
- source excerpts in findings;
- caller-supplied Gno version and network metadata;
- four initial Gno-specific rules;
- an ingestion interface for later tx-indexer integration;
- pinned validation against selected upstream Gno realms.

Current rules:

- `GNO-PAY-001` — flags `OriginSend()` paths where Sentinel cannot identify a recognized direct-user payment guard;
- `GNO-AUTH-001` — flags `OriginCaller()` use in authorization comparisons for security review;
- `GNO-STATE-001` — flags exported pointer/getter patterns that may expose mutable state, including cross-file cases; type/capability-aware classification is still planned;
- `GNO-REALM-001` — flags use of `unsafe.PreviousRealm()` inside functions that accept a `realm` parameter.

The current analyzer is heuristic and does not yet perform full CFG/dominance, SSA, or Gno type/capability analysis. A clean scan is not proof that a realm is secure. Sentinel is intended to catch known Gno-specific patterns early and make those checks reusable across projects.

### Goals and deliverables

#### 1. Gno-native static analyzer

Improve the current analyzer and make the rule framework stable enough for regular developer use.

Deliverables:

- stable CLI and JSON formats;
- package-level analysis across multiple `.gno` files;
- additional Gno parser/type/capability information where useful;
- version-aware rule applicability metadata where verified;
- deterministic finding order;
- file/line evidence and source excerpts;
- CI-compatible exit behavior;
- vulnerable and fixed fixtures for every production rule;
- documentation for each rule.

The first production rule set will focus on Gno-specific issues such as:

- caller identity mistakes;
- payment validation and `OriginSend()`;
- mutable-state pointer exposure;
- `/p/` package capability leaks;
- callbacks executed while a realm holds authority;
- unsafe realm-context APIs;
- interface/type assumptions;
- rendering issues;
- determinism issues;
- gas-risk patterns.

A rule will only be included as a production rule when it has a clear security rationale and reproducible vulnerable/fixed examples. Where a rule depends on Gno semantics that vary by version, the applicability range will only be marked after verification.

#### 2. Automatic package monitoring

Connect Sentinel to existing Gno.land indexing infrastructure rather than building a separate chain indexer.

The current tx-indexer exposes indexed transactions, including `MsgAddPackage`, and supports real-time block subscriptions. Sentinel will use those capabilities for package-publication detection. Package source retrieval will remain a separate Sentinel component.

Deliverables:

- tx-indexer integration for indexed chain data;
- detection of new package publications such as `MsgAddPackage`;
- separate package/source resolution;
- automatic analysis after source is resolved;
- package and finding history;
- deduplication of already analyzed package versions;
- block, transaction, network, and package metadata.

Planned flow:

```text
Gno.land
    ↓
tx-indexer
    ↓
publication detector
    ↓
source resolver
    ↓
Gno Sentinel analyzer
    ↓
finding history
```

#### 3. API and notifications

Provide machine-readable access to results.

Deliverables:

- API for realm/package findings;
- package security history;
- JSON finding schema;
- webhook notifications;
- CI examples;
- integration documentation.

Example endpoints:

```text
GET /realm/{path}/findings
GET /realm/{path}/history
GET /rules
```

#### 4. Security dashboard

Build a small interface for inspecting analyzed packages.

Deliverables:

- feed of newly analyzed packages;
- findings by severity and rule;
- package history;
- links to source and transaction context;
- rule descriptions and remediation guidance;
- filters by network, rule, severity, and package.

This is intended to complement existing explorers, not replace them.

#### 5. Open-source rule framework

Make it straightforward for contributors to add new checks.

Each production rule will include:

- stable rule ID;
- title and severity;
- confidence;
- affected Gno version range where verified;
- technical description;
- security invariant;
- vulnerable fixture;
- fixed fixture;
- tests;
- remediation guidance;
- references to relevant Gno documentation or code.

### Impact on gno.land’s developer ecosystem

Before deployment, developers will be able to run:

```sh
gno-sentinel scan ./my-realm
```

and use the same checks in CI.

After deployment, Sentinel can automatically detect newly published packages, resolve their source, analyze them, and keep a history of findings.

For security researchers, the rule framework provides a way to turn a confirmed Gno-specific vulnerability pattern into a reusable test.

For other ecosystem tools, the JSON/API output can be consumed by explorers, wallets, monitoring services, or developer platforms.

The project will reuse tx-indexer and other existing Gno infrastructure instead of building a separate chain indexer.

### Timeline and milestones

Proposed duration: **12 weeks**.

#### Milestone 1 — Analyzer and rule framework
**Weeks 1–4**

Deliverables:

- stabilize the package-aware analyzer;
- add Gno-native semantic/type/capability information where practical;
- improve rule precision for known heuristic edge cases;
- finalize rule metadata/versioning;
- expand to about 8–10 validated rules;
- add vulnerable/fixed fixtures for each production rule;
- deterministic regression tests;
- CI examples and documentation;
- contributor documentation for adding rules.

Acceptance criteria:

- `gno-sentinel scan <package>` produces deterministic results;
- text and JSON formats are stable;
- every production rule has vulnerable/fixed tests;
- known rule limitations are documented;
- the full suite runs in CI.

#### Milestone 2 — Chain ingestion and automatic scanning
**Weeks 5–8**

Deliverables:

- tx-indexer integration;
- new package-publication detection;
- package/source resolution;
- automatic scanning after source resolution;
- persisted package/finding history;
- block, transaction, network, and package metadata;
- retry/error handling;
- testnet demonstration.

Acceptance criteria:

```text
package publication indexed
→ detected
→ source resolved
→ analyzed
→ findings stored
```

without manual triggering.

#### Milestone 3 — API, notifications, and dashboard
**Weeks 9–12**

Deliverables:

- findings API;
- webhook notifications;
- CI/integration documentation;
- lightweight dashboard;
- package history views;
- public testnet deployment/demo;
- installation and operating documentation;
- final milestone report.

Acceptance criteria:

A developer can:

1. scan a local Gno project;
2. use the scanner in CI;
3. inspect automatically analyzed packages;
4. retrieve findings through an API;
5. subscribe to notifications.

## Contributions or related work for gno.land (if applicable)

I started Gno Sentinel before applying for this grant.

Project repository:

https://github.com/SuperSmile0426/gno-sentinel

The current prototype includes:

- Go CLI;
- package-aware `.gno` source loading;
- AST-based rules;
- cross-file analysis;
- structured findings;
- text and JSON reports;
- source evidence;
- caller-supplied Gno version/network metadata;
- regression fixtures;
- GitHub Actions CI;
- four initial Gno-specific rules;
- pinned validation against selected upstream Gno realm code.

The upstream calibration is used to identify false positives and rule-model limitations before expanding automated monitoring. Current known limitations include incomplete type/capability analysis and the absence of full CFG/dominance and SSA analysis.

I built the prototype after reviewing Gno's security documentation, realm/runtime security model, existing audit-pattern tooling, and tx-indexer architecture.

Sentinel is not intended to be a UI around existing text-pattern checks. The current direction is package-aware analysis with better semantic context, measured rule precision, and version-aware rules where applicability has been verified.

## Why are you and your team well-suited for this project?

I am a software engineer and security researcher working on source-code auditing, vulnerability research, and security tooling.

My security work is centered on reproducible results: identify the security property, build a vulnerable case, build a fixed case, and keep the test as a regression check.

That fits this project because each Sentinel rule needs to be tied to an actual Gno security property instead of relying on generic smart-contract assumptions.

The prototype is already working, so the grant would fund the next development steps rather than the initial idea.

I plan to keep the analyzer, rule definitions, fixtures, and documentation open source.

## Referrals or examples of past work

Gno Sentinel:

https://github.com/SuperSmile0426/gno-sentinel

GitHub profile:

https://github.com/SuperSmile0426

My related work includes smart-contract and blockchain security research, source-code auditing, reproducible vulnerability testing, and security tooling.

## Proposed funding

**Requested funding: USD 48,000 equivalent, milestone-based**

| Milestone | Duration | Funding |
|---|---:|---:|
| Analyzer and expanded security rules | Weeks 1–4 | $14,000 |
| tx-indexer integration and automatic package analysis | Weeks 5–8 | $16,000 |
| API, notifications, dashboard, and public deployment | Weeks 9–12 | $18,000 |
| **Total** | **12 weeks** | **$48,000** |

I am open to adjusting the scope, milestone split, or funding amount based on feedback from the Gno engineering and grants teams.

The requested funding is for the future work described above. The existing prototype was built before this application.
