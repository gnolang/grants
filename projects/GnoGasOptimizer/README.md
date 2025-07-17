# GnoGas – A Gas Optimizer for gno.land

**Github**: [github.com/amaramci](https://github.com/amaramci)  
**Email**: amarmujezinovic1@gmail.com  
**LinkedIn**: [linkedin.com/in/amar-mujezinovic](https://linkedin.com/in/amar-mujezinovic)  
**X**: [x.com/AmarMujezinov](https://x.com/AmarMujezinov)  
**Telegram**: @amaramci

---

## Project Summary

GnoGas is a tooling and compiler-level enhancement suite aimed at gas diagnostics, optimization, and developer tooling for smart contract development on gno.land.  
Unlike EVM-based platforms, gno.land lacks mature infrastructure for analyzing and optimizing gas consumption across contract execution paths. GnoGas provides the missing layer by introducing:

- Static analysis of Gno smart contracts to estimate gas usage  
- Real-time gas profiling for contract methods  
- Compiler hints and LSP integration to warn developers about inefficient patterns  
- Automated suggestions and refactoring tools for minimizing redundant computation  

The goal is to make gas optimization in Gno transparent, developer-friendly, and actionable, enabling better dApp performance and cost efficiency while laying the groundwork for more sophisticated tooling.

---

## Goals and Deliverables

### 🔧 Static Analyzer and Cost Inference Engine

- **Contract Scanner**: Parse smart contracts to extract call graphs and estimate gas cost per function.  
- **Loop/Recursion Detection**: Warn about unbounded loops or stack depth issues.  
- **Redundant Computation Finder**: Identify repeated expression evaluations and unnecessary state mutations.

### 🔍 Gas Profiler

- **Instrumentation Engine**: Wrap contracts during local runs to log actual gas consumption per call.  
- **Execution Tracer**: Output cost breakdowns (e.g., state reads/writes, loop iterations).  
- **Test Harness Plugin**: Compatible with Makefile test runs, integrates with gno test output.

### ⚠️ Developer Tooling

- **LSP/VS Code Plugin**: Highlights expensive lines, suggests more efficient patterns.  
- **Compiler Hints**: Inject warnings or hints during compilation (e.g., suggest use of view vs mutate patterns).  
- **Autofix Engine**: Basic code rewrites to optimize storage access, constants, and common idioms.

### 📉 Optimization Recipes

- **Code Cookbook**: Expand on the Effective Gno Guide by documenting practical optimization examples and integrating them with automated suggestions.  
- **Pre-deploy Checklist**: Tool that audits a contract and provides optimization suggestions.  
- **Benchmark Runner**: Compare before/after gas costs for different optimization approaches.

### 🧪 Testing & Simulation

- **Simulated Markets**: Use example dApps like GnoLend, Fomo3D, or GnoXchange to test optimizer impact in real-world logic.  
- **Regression Suite**: Ensure optimization does not break expected functionality.

### 📚 Documentation

- **User Docs**: How to use CLI tools, integration with Gnoweb, interpreting cost reports.  
- **Dev Docs**: Internals of analyzer, architecture diagrams, plugin architecture.  
- **Examples**: Side-by-side optimized/unoptimized contract examples.

---

## Impact on gno.land’s Developer Ecosystem

GnoGas addresses one of the key barriers to building performant smart contracts on gno.land: lack of tooling for understanding and controlling gas usage.

By enabling transparent gas analysis, GnoGas improves:

- **Developer experience** (cost-aware development)  
- **User experience** (cheaper dApps)  
- **On-chain performance** (lower gas load on validators)  

The optimizer will also help projects migrating from EVM understand cost trade-offs in Gno and ease the onboarding curve.

In the long run, GnoGas sets the foundation for:

- **Gas-aware compiler optimizations**  
- **Automatic optimization pipelines**  
- **Better fee modeling for ecosystem-wide efficiency**

---

## 🗓 Timeline and Milestones – GnoGas (12-16 Weeks)

### Week 1–4: Static Analyzer & Call Graph Generation

- Build a parser for Gno smart contracts to construct an Abstract Syntax Tree (AST).  
- Analyze the call structure of contracts to identify function relationships.  
- Detect loops, recursion, and potentially unbounded logic.  
- Begin assigning rough gas cost heuristics to storage access patterns, state mutations, and function calls.

### Week 5–6: Gas Profiler & CLI Tooling

- Instrument test environments to track real-time gas consumption using `gno test`.  
- Develop a CLI tool (`gno-gas-report`) to output gas usage per function, sorted by cost.  
- Compare static estimates with runtime measurements to refine heuristics.  
- Display a breakdown of gas cost sources: reads/writes, loops, contract calls.

### Week 7–8: Developer Tooling Integration

- Expose GnoGas as a CLI service or library that can be integrated into existing Gno IDE plugins (such as the current VS Code and IntelliJ extensions powered by the Gno LSP).  
- Provide a public API or CLI command that returns static analysis results and gas estimates.  
- Allow existing editors to display highlights, tooltips, and warnings by consuming GnoGas outputs.  
- Ensure consistency between CLI diagnostics and in-editor feedback without requiring a new plugin.

### Week 9–10: Real-World Integration & Regression Testing

- Apply GnoGas to existing projects (e.g., GnoLend, GnoXchange, Fomo3D).  
- Produce before/after gas reports to demonstrate optimization effectiveness.  
- Build a regression suite to ensure optimizations do not alter business logic.  
- Add mock contracts and scenarios to simulate high-load edge cases.

### Week 11–12: Documentation, Cookbook & Release

- Write user documentation covering:
  - CLI tool usage  
  - Integration with VS Code  
  - How to interpret gas reports and apply fixes  
- Publish a “Gas Optimization Cookbook” featuring common patterns and their refactored versions.  
- Finalize public release of GnoGas:
  - Open-source repository  
  - Grant documentation  
  - Example walkthroughs and marketing blog post

---

## Why We're Well-Suited for This Project

I previously worked on **Liberty Bridge** ([GitHub link](https://github.com/amaramci/LibertyBridge)), a project developed during the Petnica Science Center program, which built a bridge between gno.land and Ethereum using Golang. The project explored inter-chain communication, gas compatibility, and secure state syncing between two fundamentally different architectures.

My teammate on GnoGas is **Boris Cvitak** ([GitHub](https://github.com/djanluka)), with 4+ years of experience using Golang. Together, we spent over a year working at a blockchain R&D company, where we contributed to several smart contract platforms and infrastructure components across multiple chains.

### Our shared experience includes:

- Gno-GasOptimisator: https://github.com/amaramci/gno-GasOptimisator  
- Issue on gno repl: https://github.com/gnolang/gno/issues/4375  
- Building developer tools for ZK Languages: https://www.zksimulator.xyz/  
- Building parser infrastructure  
- Stealth address protocol: https://www.0xcurvy.io/

We’ve collaborated extensively and understand how to split responsibilities efficiently.  
Based on the scope and milestones of GnoGas, we’re confident in our ability to deliver a complete and production-grade tool within 3 months.

---

## Our CVs

- **Amar**: [Amar](https://drive.google.com/file/d/10Oma6MifCP8eVDEDyvZaXPfUtbXpaP5-/view?usp=sharing)  
- **Boris**: [Boris](https://drive.google.com/file/d/1IoklBk9HDHBMK_jC6iH0YCr9FvgvRBF7/view)

