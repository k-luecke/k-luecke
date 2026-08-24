## Kyle Luecke

I build verification and data-integrity infrastructure — systems whose job is to
prove something is true, and to stay honest when the source disappears. Most of
my work sits where cryptography, public-record data, and the pipelines that keep
both auditable meet.

Rust, Python, TypeScript/Node, SystemVerilog. Comfortable from a C-FFI
cryptographic primitive up to the CI that runs it on a schedule.

---

### Selected work

**[FinCEN-BOI](https://github.com/k-luecke/FinCEN-BOI)** · Python · public-record preservation

A provenance-first archival system for the Corporate Transparency Act's
beneficial-ownership record set, built around the August 2026 rule that ended
collection of U.S.-person BOI and deleted what had been gathered.

- Content-addressed object store (SHA-256) with an append-only retrieval ledger,
  so the archive can prove *these exact bytes* were served from *that*
  government URL at *that* timestamp.
- The change ledger is a pure function of the append-only manifest and can be
  rebuilt from scratch — which makes `ADDED / MODIFIED / REMOVED` falsifiable
  rather than asserted.
- Host-aligned chunked crawls across parallel CI jobs, so per-host rate limits
  stay true under parallelism.
- A challenge-aware recovery layer that detects bot interstitials, refuses to
  count them as captured records, and routes to other *lawful* public
  representations — explicitly no CAPTCHA solving, proxy rotation, or
  rate-limit circumvention.

**[bls-verifier](https://github.com/k-luecke/bls-verifier)** · Rust · cryptographic primitive

Ethereum sync-committee signature verification as a single C-FFI function,
compiled to either a native cdylib or a `wasm32` module.

- Deliberately narrow: one primitive that verifies one thing, with its
  failure-mode taxonomy and return codes documented as a runbook.
- Four-crate workspace separating the primitive from its integration runner, CLI
  wrapper, and production harness (beacon failover, period-keyed committee
  cache, signing-root computation).
- The docs lead with what the primitive *does not* do, and why it must not be
  wired directly into production.

**[811Dog](https://github.com/k-luecke/811Dog)** · Python · TypeScript · data pipeline

A monitoring pipeline for Tennessee 811 excavation tickets: Playwright scrapes
the public portal, pdfplumber parses the linked PDFs, tickets are scored against
configurable relevance rules, history lands in SQLite, and a static dashboard
plus expiry reminders are published from scheduled CI.

- Export-first scraping: the portal's CSV export carries enough to classify most
  tickets without opening a detail page, turning tens of thousands of requests
  per run into hundreds.
- Scoring is explainable — every ticket carries the rules that fired and at what
  weight, so a surprising classification is traceable rather than arguable.
- No target is hard-coded. Which counties, contractors, and work types matter
  all live in config; the engine has no built-in notion of any company.
- 335 tests, running offline against captured fixtures.

**[Selkov + Goldilocks RTL](https://github.com/k-luecke/medals)** · SystemVerilog · hardware verification

Two SystemVerilog cores — a Q8.24 fixed-point Selkov integrator and a
divider-free Goldilocks-field reducer — simulated with Icarus, cocotb, and Yosys.

- Every core is checked **differentially against an independent implementation**:
  the fixed-point RTL against a float integration of the same ODEs, and the fast
  modular reduction against the `%` operator bit-for-bit. No golden traces, so
  the tests still mean something when parameters change.
- `` `default_nettype none `` makes an implicit wire a compile error; arithmetic
  saturates and raises a sticky fault flag, because a wrapped accumulator that
  keeps running is indistinguishable from a correct one downstream.
- Documents what it is *not*: not a prover, not an FPGA timing result.

**[zkfwdbld](https://github.com/k-luecke/zkfwdbld)** · Rust · verifiable findings

A prototype trust layer attaching evidence, derivation trace, and a proof
artifact to automated security findings, so a triage engineer can act on a
scanner alert without treating it as a black box. Rust proving core doing witness
generation and R1CS verification over the Goldilocks field. The README marks
exactly where the real prover path ends and the demo path begins.

**[paxiom](https://github.com/k-luecke/paxiom)** · Node · Solidity · cross-chain verification

Cross-chain state verification: fetch archived Ethereum proofs, Merkle-verify
them against the block's `stateRoot`, and serve the result through x402-gated
services that sign every response over a canonical-JSON hash. Includes an
unflattering security audit of my own code, and a "what is and isn't built"
table separating working components from stubs and design intent.

**[TermBrow](https://github.com/k-luecke/TermBrow)** · Python · terminal browser

A terminal browser that strips ads and page furniture and curates a reading feed
— science, policy, and long-form. Runs at
[termbrow.org](http://www.termbrow.org/).

---

### Also here

- **[paxiom-static](https://github.com/k-luecke/paxiom-static)** — architecture
  and documentation site.
- **[smartdream](https://github.com/k-luecke/smartdream)** — an exploratory
  symbolic-agent framework. Built for fun; labeled as such.
- **[driftbound-site](https://github.com/k-luecke/driftbound-site)** — static
  site, custom apex domain, Pages deploy.

---

### How I work

The through-line is that I write down what a system **cannot** do as carefully
as what it can. Proof boundaries, failure-mode taxonomies, out-of-scope markers,
and "do not wire this into production yet" warnings are in these READMEs on
purpose — a verification system that oversells its guarantees is worse than
none.

🔗 [paxiom.org](https://paxiom.org)
