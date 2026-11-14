## Kyle Luecke

**[Driftbound Labs](https://driftboundlabs.com)**

I build verification, provenance, and measurement systems for situations where a conclusion must remain defensible when conditions, sources, or incentives drift.

Rust, Python, TypeScript/Node, SystemVerilog. Comfortable from a C-FFI cryptographic primitive up to the CI and settlement plumbing that runs it in production.

Lab site: [driftboundlabs.com](https://driftboundlabs.com) · portfolio: [termbrow.org](https://termbrow.org) · Paxiom: [paxiom.org](https://paxiom.org)

---

### Featured work

**[Paxiom Receipts (`paxiom-static`)](https://github.com/k-luecke/paxiom-static)** · TypeScript/Node · Python · proof-bound execution receipts

Proof-of-delivery specification (`paxiom.receipt.v0`), zero-dependency SDKs, MCP servers, and live Base Mainnet x402 verification service at [`api.paxiom.org`](https://api.paxiom.org) / [`paxiom.org`](https://paxiom.org).

- Published at `v0.1.3` across npm ([`@paxiom/receipts`](https://www.npmjs.com/package/@paxiom/receipts)), PyPI ([`paxiom-receipts`](https://pypi.org/project/paxiom-receipts/)), and the Official MCP Registry (`io.github.k-luecke/paxiom-receipts`), verified byte-for-byte via cross-language RFC 8785 & Ed25519 test vectors.
- Free deterministic offline verification (`POST /v1/receipt/verify`), plus paid Base Mainnet x402 USDC `Transfer`-log settlement attestation (`POST /v1/receipt/verify-live`, `$0.002` USDC) and SSRF-hardened seller preflight scanning (`POST /v1/x402/preflight`, `$0.01` USDC).
- Offline checks report unverified settlement assertions honestly as `claimed_not_checked` rather than implying on-chain finality.

**[Monad(1) V7 (`monad-1-arc-agi-3`)](https://github.com/k-luecke/monad-1-arc-agi-3)** · Python · deterministic neuro-symbolic synthesis

Intent-Native Operating System (`INOS v0.7`) and Fuzzy Merkle Forest architecture for interactive discrete reasoning on ARC-AGI-3.

- Verified `100.0%` (`25/25` games, `167/167` levels) official `OperationMode.COMPETITION` scorecard (`6b457c81-1b14-407c-9f8a-d1e119fc72f9`).
- Falsification-gated synthesis and bounded counterfactual state search with deterministic execution traces.

**[811Dog](https://github.com/k-luecke/811Dog)** · Python · TypeScript · operational pipeline

A monitoring pipeline for Tennessee 811 excavation tickets: Playwright scrapes the public portal, pdfplumber parses linked PDFs, tickets are scored against configurable relevance rules, history lands in SQLite, and a static dashboard plus expiry reminders publish from CI when an active campaign is configured.

- Export-first scraping: most tickets classify without opening a detail page.
- Scoring is explainable — every ticket carries which rules fired and at what weight.
- No target is hard-coded; counties, contractors, and work types live in config (scheduled CI paused outside active campaigns).
- 335 tests, offline against captured fixtures.

**[FinCEN-BOI](https://github.com/k-luecke/FinCEN-BOI)** · Python · provenance-first preservation

Public-record preservation around the Corporate Transparency Act beneficial-ownership environment after the August 2026 rule that stopped collecting U.S.-person BOI and deleted what had been gathered.

- Content-addressed object store (SHA-256) with an append-only retrieval ledger.
- Distinguishes publicly accessible government evidence from the confidential CTA-filed BOI database (never treated as available).
- Ownership reconstruction uses only separately public sources, with every edge source-addressable.
- Challenge-aware recovery routes to other lawful public representations — no CAPTCHA solving or access bypass.

**[Time Integrity](https://github.com/k-luecke/time-integrity)** · preregistered measurement package

Preregistered measurement of Schumann-band coherence and inter-site propagation lag between LIGO Hanford and Livingston magnetometers over one six-hour O3 interval.

- **P1** physical coherence: verified.
- **D2b** physical lag stability: failed (between-window scatter exceeds the frozen threshold).
- Analysis package complete with checksums and reproduction instructions; large binaries external with recorded hashes.
- Not a positioning system, timing service, or GNSS replacement.

**[Driftbound Labs (`driftbound-labs`)](https://github.com/k-luecke/driftbound-labs)** · Python · research platform

Reproducible experiments in adaptive assurance, agent populations, nonlinear control, and physical sensing under changing conditions.

- Core experiment primitives, baselines, and the Three Little Pigs benchmark CLI are implemented.
- Three Little Pigs is an implemented benchmark / research platform — **not** a deployed intelligent system.
- Site: [driftboundlabs.com](https://driftboundlabs.com)

---

### Supporting

- **[research-method](https://github.com/k-luecke/research-method)** — executable eleven-stage research protocol, preregistration templates, and artifact hash verification CLI.
- **[paxiom](https://github.com/k-luecke/paxiom)** — historical Ethereum Merkle-Patricia state proof & x402 substrate prototype (159 tests, explicit self-audit).
- **[bls-verifier](https://github.com/k-luecke/bls-verifier)** — narrow Ethereum sync-committee BLS12-381 primitive (native / wasm) with explicit production boundaries.
- **[zkfwdbld](https://github.com/k-luecke/zkfwdbld)** — prototype trust layer attaching evidence and proof artifacts to automated security findings; README marks where the real prover path ends.
- **[medals](https://github.com/k-luecke/medals)** — SystemVerilog Selkov + Goldilocks field arithmetic cores verified with Icarus Verilog, cocotb, and Yosys.
- **[Geo](https://github.com/k-luecke/Geo)** — open research notebook and closure ledgers for the broader Schumann / geophysical experiment lineage.
- **[TermBrow](https://github.com/k-luecke/TermBrow)** / **[term-brow-static](https://github.com/k-luecke/term-brow-static)** — terminal browser and reading-first portfolio site at [termbrow.org](https://termbrow.org).

---

### How I work

I write down what a system **cannot** do as carefully as what it can. Proof boundaries, failed criteria, out-of-scope markers, and "not built yet" tables stay in the READMEs on purpose — a verification system that oversells its guarantees is worse than none.

🔗 [driftboundlabs.com](https://driftboundlabs.com) · [paxiom.org](https://paxiom.org) · [termbrow.org](https://termbrow.org) · [ORCID 0009-0008-0202-7852](https://orcid.org/0009-0008-0202-7852)
