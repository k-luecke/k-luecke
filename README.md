## Kyle Luecke

**[Driftbound Labs](https://driftboundlabs.com)**

I build verification, provenance, and measurement systems for situations where a conclusion must remain defensible when conditions, sources, or incentives drift.

Rust, OCaml, C, Python, TypeScript/Node, SystemVerilog. Comfortable from a C-FFI cryptographic primitive up to the CI and settlement plumbing that runs it in production.

Lab site: [driftboundlabs.com](https://driftboundlabs.com) · papers: [driftboundlabs.com/papers.html](https://driftboundlabs.com/papers.html) · portfolio: [termbrow.org](https://termbrow.org) · Paxiom: [paxiom.org](https://paxiom.org)

---

### Featured work

**[Paxiom Receipts (`paxiom-static`)](https://github.com/k-luecke/paxiom-static)** · TypeScript/Node · Python · proof-bound execution receipts

Proof-of-delivery specification (`paxiom.receipt.v0`), zero-dependency SDKs, MCP servers, and live Base Mainnet x402 verification service at [`api.paxiom.org`](https://api.paxiom.org) / [`paxiom.org`](https://paxiom.org).

- Published at `v0.1.3` across npm ([`@paxiom/receipts`](https://www.npmjs.com/package/@paxiom/receipts)), PyPI ([`paxiom-receipts`](https://pypi.org/project/paxiom-receipts/)), and the Official MCP Registry (`io.github.k-luecke/paxiom-receipts`), verified byte-for-byte via cross-language RFC 8785 & Ed25519 test vectors.
- Free deterministic offline verification (`POST /v1/receipt/verify`), plus paid Base Mainnet x402 USDC `Transfer`-log settlement attestation (`POST /v1/receipt/verify-live`, `$0.002` USDC) and SSRF-hardened seller preflight scanning (`POST /v1/x402/preflight`, `$0.01` USDC).
- Offline checks report unverified settlement assertions plainly as `claimed_not_checked` rather than implying on-chain finality.

**[IntentNativeOS](https://github.com/k-luecke/IntentNativeOS)** · Rust (`no_std` UEFI) · OCaml 5 · C · experimental capability OS (`v0.3.0-alpha`)

Experimental x86-64 operating system pairing a bare-metal UEFI Rust microkernel (`W^X` paging, per-process `CR3` Ring 0/3 isolation, crash-tested WAL filesystem, VirtIO TCP/UDP, DNSSEC, 1280×800 GOP compositor) and 17 native Ring 3 desktop applications with an OCaml 5 + C typed intent control plane (zero Python or cloud runtime dependencies).

- **55/55** unit, property, adversarial-boundary, and Sentinel qualification suites passing (`dune runtest`), plus cold-build verification of `BOOTX64.EFI` and all 17 Ring 3 `.inapp` packages.
- Production Beta status remains explicitly withheld behind bare-metal USB HID FIDO2 token passthrough (`BLK-01`) and external cryptographic/kernel audit (`BLK-02`); experimental `research/tonic` and `research/scp` lanes are quarantined `OFF` by default.

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

---

### Preprints & reproducible research packages

Full PDFs, SHA-256 digests, OpenTimestamps proofs, and BibTeX records are indexed at **[driftboundlabs.com/papers.html](https://driftboundlabs.com/papers.html)**:

- **[time-integrity](https://github.com/k-luecke/time-integrity)** (`v2.0.0`) — *Exterior Clock-Integrity Auditing via Canonical Coherence of the Schumann Resonance Field*. Preregistered 6-hour LIGO H1–L1 O3 vault measurement (`P1` canonical coherence `0.3291`, `z = 24.54`; `P2` `49.9×` vault gain; `D1` `76.6 µs` Carter CRLB; **`D2b` lag stability not supported** at `4.95 ms` scatter vs. `0.796 ms` threshold). Companion WWLLN notebook at **[Geo](https://github.com/k-luecke/Geo)**.
- **[scp-typed-boundaries](https://github.com/k-luecke/scp-typed-boundaries)** (`v1.0.0` · `5/5` Bitcoin `.ots` proofs) — *Typed Boundaries for Small-Model Web Agents*. Tracks the BrowserGym/MiniWoB++ reference agent across `0.5B–3B` at `3.1×–3.8×` fewer tokens with **zero invalid actions executed** (`0/300` vs. `152/300` unassisted), reporting plainly that the deterministic gate filters rather than repairs.
- **[tonic-gating](https://github.com/k-luecke/tonic-gating)** (`v1.0.0` · `12/12` Bitcoin `.ots` proofs) — *Phase Selects; It Does Not Amplify*. Twelve preregistered stages testing oscillatory expert selection (`T_hold = 26.8` / `65.0` tokens, cosine demodulation, single-pass attribution `r_φ = 0.869`) alongside null ensemble amplification, lookup dominance under continuous evidence, and `T10` closed as `not informatively tested`.
- **[network-native-computation](https://github.com/k-luecke/network-native-computation)** (`v1.0.0`) — *Network-Native Computation*. Formal four-term accounting law, Bounded-Probe Structural Ambiguity proof (Theorem 1 & Lemma 1), and 8 reproducible micro-experiments across DNS `DNAME`, CAS Merkle trees, stock Git `v2.55.0`, IPFS Bitswap/DHT, AO checkpoint witnesses, and failed prospective routing (`Exp08`).
- **[The Physical Layer of the AI Infrastructure Buildout](https://driftboundlabs.com/papers/AI_Infrastructure_Buildout_Whitepaper.pdf)** (Institutional Research Whitepaper) — Point-in-time sovereign docket, permit, and 811 telemetry audit across 31 North American data center and semiconductor fab builds (`2,184 MW` announced, `51.6%` execution-ready, `211-day` median lead time across `9/9` resolved delays, `112.0-week` Kaplan–Meier substation energization median).
- **[fnwd-v04-retraction](https://github.com/k-luecke/fnwd-v04-retraction)** (`v0.4.0`) — *Autonomous Discovery of Idempotent State-Space Retractions and Conditional Commutation Manifolds*. `115`-class quotient Projection Poset over `F_4093`, 6-gate linearizability and factorial ablation suite, 12-operator blind triage (`3/3` valid promoted, `0/9` unsound promoted), and explicit small-tree DSW latency crossover (`+69.6%` at `N = 150`).

---

### Supporting systems & protocols

- **[custos](https://github.com/k-luecke/custos)** — ESP32/ESP32-S3 SX1262 LoRa `ChaCha20-Poly1305` sensor telemetry, 24-bit `PCM1808` I2S Goertzel DSP, and Python TDOA localization / hash-chained incident engine (`v0.1.0`).
- **[secp256k1-kangaroo-lab](https://github.com/k-luecke/secp256k1-kangaroo-lab)** — OpenCL decoupled Pollard's Kangaroo benchmark (Puzzles `#40`–`#44`), modular ECDLP representation tournament, BIP34 regtest verifier, and 16 falsified sub-constant/endomorphism cycles.
- **[rc4-causal-cones](https://github.com/k-luecke/rc4-causal-cones)** — reduced-modulus RC4 ($m \le 16$) Z3/DFS equivalence, lazy address revelation, and causal-cone frontier experiments (`exp1`–`exp16`).
- **[switchboard](https://github.com/k-luecke/switchboard)** — single-file offline-first visual countdown timer and RFC 5545 (`.ics`) calendar import/export utility.
- **[driftbound-labs](https://github.com/k-luecke/driftbound-labs)** — reproducible-experiment research platform and Three Little Pigs benchmark CLI (implemented benchmark, not a deployed intelligent system).
- **[research-method](https://github.com/k-luecke/research-method)** — executable eleven-stage research protocol, preregistration templates, and artifact hash verification CLI.
- **[paxiom](https://github.com/k-luecke/paxiom)** — historical Ethereum Merkle-Patricia state proof & x402 substrate prototype (159 tests, explicit self-audit).
- **[bls-verifier](https://github.com/k-luecke/bls-verifier)** — narrow Ethereum sync-committee BLS12-381 primitive (native / wasm) with explicit production boundaries.
- **[zkfwdbld](https://github.com/k-luecke/zkfwdbld)** — prototype trust layer attaching evidence and proof artifacts to automated security findings; README marks where the real prover path ends.
- **[medals](https://github.com/k-luecke/medals)** — SystemVerilog Selkov + Goldilocks field arithmetic cores verified with Icarus Verilog, cocotb, and Yosys.
- **[TermBrow](https://github.com/k-luecke/TermBrow)** / **[term-brow-static](https://github.com/k-luecke/term-brow-static)** — terminal browser and reading-first portfolio site at [termbrow.org](https://termbrow.org).

---

### How I work

I write down what a system **cannot** do as carefully as what it can. Proof boundaries, failed criteria, out-of-scope markers, and "not built yet" tables stay in the READMEs on purpose — a verification system that oversells its guarantees is worse than none.

🔗 [driftboundlabs.com](https://driftboundlabs.com) · [driftboundlabs.com/papers.html](https://driftboundlabs.com/papers.html) · [paxiom.org](https://paxiom.org) · [termbrow.org](https://termbrow.org) · [ORCID 0009-0008-0202-7852](https://orcid.org/0009-0008-0202-7852)
