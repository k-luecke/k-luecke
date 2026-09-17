## Kyle Luecke

**[Drift Bound Labs](https://driftboundlabs.com)**

I build verification, provenance, and measurement systems for situations where a conclusion must remain defensible when conditions, sources, or incentives drift.

Rust, Python, TypeScript/Node, SystemVerilog. Comfortable from a C-FFI cryptographic primitive up to the CI that runs it on a schedule.

Portfolio surface: [termbrow.org](https://termbrow.org) · lab site: [driftboundlabs.com](https://driftboundlabs.com)

---

### Featured work

**[811Dog](https://github.com/k-luecke/811Dog)** · Python · TypeScript · operational pipeline

A monitoring pipeline for Tennessee 811 excavation tickets: Playwright scrapes the public portal, pdfplumber parses linked PDFs, tickets are scored against configurable relevance rules, history lands in SQLite, and a static dashboard plus expiry reminders publish from scheduled CI.

- Export-first scraping: most tickets classify without opening a detail page.
- Scoring is explainable — every ticket carries which rules fired and at what weight.
- No target is hard-coded; counties, contractors, and work types live in config.
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

**[paxiom](https://github.com/k-luecke/paxiom)** · Node · Solidity · cross-chain verification

Working prototype: Merkle-Patricia proof verification against block `stateRoot`, plus an HTTP service tier with signed envelopes and x402 gating.

- MPT substrate and HTTP tier are working and tested.
- ZK proving layer, production contracts posture, and mainnet: **not built**.
- Includes an unflattering self-audit and an explicit "what is and isn't built" table.

**[Drift Bound Labs](https://github.com/k-luecke/driftbound-labs)** · Python · research platform

Reproducible experiments in adaptive assurance, agent populations, nonlinear control, and physical sensing under changing conditions.

- Core experiment primitives, baselines, and the Three Little Pigs benchmark CLI are implemented.
- Three Little Pigs is an implemented benchmark / research platform — **not** a deployed intelligent system.
- Site: [driftboundlabs.com](https://driftboundlabs.com)

---

### Supporting

- **[research-method](https://github.com/k-luecke/research-method)** — executable research protocol and scaffolding.
- **[bls-verifier](https://github.com/k-luecke/bls-verifier)** — narrow Ethereum sync-committee BLS primitive (native / wasm), with explicit production boundaries.
- **[zkfwdbld](https://github.com/k-luecke/zkfwdbld)** — prototype trust layer attaching evidence and proof artifacts to automated findings; README marks where the real prover path ends.
- **[TermBrow](https://github.com/k-luecke/TermBrow)** / **[term-brow-static](https://github.com/k-luecke/term-brow-static)** — terminal browser and reading-first portfolio site at [termbrow.org](https://termbrow.org).
- **[Geo](https://github.com/k-luecke/Geo)** — research notebook for the broader Schumann / geophysical experiment lineage.
- **[medals](https://github.com/k-luecke/medals)** — SystemVerilog Selkov + Goldilocks cores with differential testing against independent implementations.

---

### Also / archive

- **[smartdream](https://github.com/k-luecke/smartdream)** — exploratory symbolic-agent framework. Built for fun; not featured.
- **[paxiom-static](https://github.com/k-luecke/paxiom-static)** — architecture and documentation site for Paxiom.
- **[driftbound-site](https://github.com/k-luecke/driftbound-site)** — Driftbound Labs static site (Pages).

---

### How I work

I write down what a system **cannot** do as carefully as what it can. Proof boundaries, failed criteria, out-of-scope markers, and "not built yet" tables stay in the READMEs on purpose — a verification system that oversells its guarantees is worse than none.

🔗 [driftboundlabs.com](https://driftboundlabs.com) · [termbrow.org](https://termbrow.org) · [paxiom.org](https://paxiom.org)
