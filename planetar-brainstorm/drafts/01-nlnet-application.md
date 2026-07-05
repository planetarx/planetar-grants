# NLnet application (draft) — target fund: **Restack**

> **⏸️ ON HOLD 2026-07-03 — do not submit for 2026-08-01.** Verified on `nlnet.nl/propose`
> (2026-07-02): the only selectable calls are **NGI TALER** and **NGI Fediversity** — no
> Restack, and no general Open Call (so the fallback in the apply-note below is currently
> impossible). NLnet's regular call reopens **after summer 2026**; Restack's rolling calls
> haven't started. Keep this draft ready, **check https://nlnet.nl/propose/ monthly**, and
> submit to the first Restack / regular call that appears. Status detail:
> [`../02-oss-funders.md`](../02-oss-funders.md).

> **Retargeted 2026-06-03.** The **NGI Zero Commons Fund closed permanently** — its 13th
> and final call was 2026-06-01; the NGI0 budget is fully allocated. NGI Zero **Core** is
> also closed. The fit-appropriate successor is **Restack** — NLnet's new Horizon Europe
> "Open Internet Stack" cascade-funding programme: *"a healthy Open Internet Stack… open,
> resilient, trustworthy digital infrastructure… middleware without vendor lock-in… local-first
> infrastructure."* €5k–50k, **individuals and organisations of any type eligible**, rolling
> open calls **every 2 months, June 2026 → 2030**, scale-up available for proven projects.
> **Next deadline: 2026-08-01 12:00 CEST.** This is a near-perfect fit for the permissively
> licensed bus + envelope as reusable open infrastructure — *not* the defence platform.
>
> **Apply:** https://nlnet.nl/propose/ — set **Call Selection = Restack** if listed by the
> Aug-1 window; if Restack isn't yet selectable, choose **Open Call** and name Restack in the
> abstract, or email NLnet to confirm routing. `[TODO]` = fill before submitting.
>
> **Scope of this grant = the open, permissively-licensed bus (`planetar-broker`, now
> Apache-2.0) + envelope (`zmesg`, Apache-2.0)** as reusable digital-commons infrastructure,
> plus a civilian maritime-safety reference application. Keep defence framing **out**.

---

## Form fields (in the order the NLnet form asks them)

**Call Selection:** Restack *(fallback: Open Call — see note above)*
**Your Name:** Steven Ness
**Email:** sness@sness.net
**Phone:** `[TODO: founder phone]`
**Organisation:** *(recommend leaving blank → apply as an **individual**.* This keeps the
open-infrastructure grant cleanly **ring-fenced** from Zax Analytics, which separately pursues
Canadian R&D funding for the *platform* layer — avoids any appearance of double-funding the same
work. If you'd rather name the company, use `Zax Analytics` — your call.)
**Country:** Canada

**Proposal Name:** planetar — an open real-time fusion bus & self-describing message
envelope for multi-source data

**Website / repository:** `github.com/planetarx/planetar-broker` ·
`github.com/sness23/zmesg` · https://planetar.ca (live demo) · https://sness.net

**Requested amount:** €50,000

---

### Abstract — explain the whole project and its expected outcome(s) *(be short and to the point)*

planetar is open infrastructure for fusing many real-time data sources into one live,
auditable picture. Two components are the foundation and the focus of this grant, both
**permissively licensed (Apache-2.0)** so anyone can build on them:

- **`zmesg`** — a compact, self-describing binary message envelope (~260 LOC header). Every
  message carries a UUIDv7 id, nanosecond timestamp, topic, source, and
  **correlation/causation links**, so provenance ("which inputs produced this output, and
  when") travels with the data and can be parsed zero-copy.
- **`planetar-broker`** — a small (~1,000 LOC, single-file C) low-latency message bus
  (shared-memory + TCP/UDP) with a CRC-checked write-ahead log for durability and replay.

Today these power a working maritime-safety demo (fusing ship AIS, satellite radar, cameras,
and underwater acoustics to spot vessels that hide by switching off their transponders —
relevant to illegal fishing, search-and-rescue, and pollution response). **This grant hardens
the two foundation components into general-purpose, well-documented, reusable infrastructure**
that any project needing low-latency, provenance-carrying data fusion can adopt — sensor
networks, scientific instruments, IoT, observability.

**Outcomes:** (1) a stable, documented **envelope specification** with a conformance test
suite; (2) a hardened, portable reference **broker** with language bindings; (3) a **web
bridge** so browser apps can consume the bus; (4) a public, reproducible maritime-safety
reference application built entirely on the open components.

### Have you been involved with relevant projects or organisations before?

Yes. The applicant (Steven Ness, PhD, University of Victoria) has ~20 years building
data-intensive open systems: published **bioacoustic ML on Ocean Networks Canada hydrophone
data** (IEEE PacRim 2011); built **the Orchive**, a semi-automatic annotation platform over a
20,000-hour, 30-year orca-call archive (ORCA-SLANG, Interspeech 2021); and is a **named
inventor on US Patent 10,936,582** (entity resolution across distributed systems). The
planetar components are the applicant's own work, open-sourced in 2026 (`zmesg` in March,
`planetar-broker` on 2026-05-15); a prior entity-resolution proof-of-concept (`doibio`, ~20k
LOC) informs the design. All cited repositories are public.

### Requested amount (€) — and budget breakdown

**€50,000.** NLnet pays per completed task/deliverable (milestone-based MoU), so the budget is
a task list, each independently deliverable:

| Task | Deliverable | € |
|---|---|---|
| Envelope spec + conformance suite | Versioned `zmesg` spec; test suite third-party implementations can run | 12,000 |
| Broker hardening | Portability, backpressure, fuzzing, WAL recovery/fault-injection tests | 14,000 |
| Language bindings | Python + JS/TS + one of Rust/Go, with examples | 10,000 |
| Web/WebSocket bridge + docs | Browser bridge that preserves provenance; tutorials | 8,000 |
| Security & accessibility audit follow-through | Remediation using NLnet's offered audit services | 6,000 |

*(First-grant alternative: a tighter ~€30k scope (spec + conformance + hardening + bridge) is
often easier to win, then use Restack's **scale-up** track for the bindings/audit. Decide
before submitting.)*

### Other funding sources (past and present)

The broader planetar **platform** (sensor detectors, fusion models, entity graph, operator
shell) pursues **separate** Canadian R&D funding (e.g. NRC IRAP / SR&ED via Zax Analytics).
**This grant is ring-fenced to the permissively-licensed open infrastructure** (envelope + bus
+ bindings + bridge) and its open reference application — distinct work from anything the
Canadian funding would cover, so there is no double-funding.

### Compare with existing or historical efforts — what's new/different?

General-purpose buses exist — Kafka (durable log, ms latency), NATS/ZeroMQ/Redis Streams
(low-latency transport), Aeron (ultra-low-latency, but a transport, not a typed provenance
model). planetar is **not** trying to out-scale Kafka. What's different:

- **Provenance is in the envelope, not bolted on.** Correlation/causation ids make every
  derived message traceable to its inputs — a first-class lineage graph at the wire level,
  which fusion/observability pipelines normally rebuild by hand.
- **Low-latency shared-memory path co-designed with a self-describing, zero-copy typed
  envelope** — most stacks give you one or the other. (The architectural predecessor,
  `zbroker0`, measured a shared-memory median latency of ~80–140 ns over a one-million-message
  benchmark; `planetar-broker`'s TCP path measures ~34 µs median, and its shared-memory path
  is being re-benchmarked on the current codebase.)
- **Zero/near-zero dependencies and small** (broker ~1,000 LOC C; envelope ~260 LOC header) —
  auditable and embeddable, unlike heavyweight brokers.
- **Permissive license + conformance suite** aimed at making the envelope an *open
  interoperability standard*, not a single product — exactly Restack's "middleware without
  vendor lock-in."

### Significant technical challenges you expect to solve

- A **portable** sub-microsecond shared-memory path (SHM handshake via SCM_RIGHTS today) that
  degrades gracefully across OSes and to TCP/UDP without changing the envelope.
- A stable, **versioned envelope spec** with backward/forward compatibility and a conformance
  suite that third-party implementations can test against.
- **Backpressure, durability, and recovery** under load (WAL replay, CRC validation, bounded
  memory) proven by fuzzing and fault-injection.
- A **zero-copy web bridge** that exposes the bus to browsers without losing provenance.

### Ecosystem & engagement

- **Open-data / ocean community:** live AIS, Sentinel-1, and ONC/OrcaSound hydrophone feeds as
  worked examples; engage maritime-safety and ocean-science users.
- **OSS messaging / standards community:** publish the envelope spec openly; pursue an
  **IETF-style draft** for the envelope (an open interoperability standard).
- **Public build in the open:** documentation, tutorials, conformance suite, and a YouTube
  build-log series; `FUNDING.yml` + Open Collective for ongoing community support.
- **Reuse beyond maritime:** position the bus+envelope for any low-latency,
  provenance-sensitive fusion (sensor networks, scientific instruments, observability).

### Attachments (optional, ≤50 MB; PDF/HTML/ODF/txt)

Optional but strong: the architecture diagram and the formal benchmark report (latency,
methodology). Keep any attachment **civilian-framed** — no defence material.

### ⚠️ Generative AI disclosure (the form now requires this)

NLnet's form asks whether generative AI was used to prepare the application and, if so, for the
**model, dates, prompts, and unedited output**. This draft **was prepared with AI assistance
(Anthropic Claude, 2026-06-03)**. Answer this question **honestly** — disclose the assistance
and be ready to attach the relevant prompts/output. Do **not** leave it blank or answer "no."

---

### Pre-submit checklist
- [x] `planetar-broker` relicensed **Apache-2.0** (done 2026-06-03, commit `bda6cb4`) — the
      "permissively licensed" claim is now true.
- [x] Repo URLs corrected to `github.com/sness23/...` (were wrongly `planetarx/`).
- [x] Latency claim corrected — predecessor (`zbroker0`) ns figure attributed honestly;
      planetar-broker's own measured number is the ~34 µs TCP path.
- [x] LOC corrected to auditable committed values (broker ~1,000; envelope 260).
- [ ] Fill `[TODO]`s: founder phone.
- [ ] Decide applicant entity: **individual (recommended)** vs Zax Analytics.
- [ ] Decide ask: **€50k** vs tighter **~€30k** first grant (then scale-up).
- [ ] Complete the **generative-AI disclosure** honestly.
- [ ] Confirm **Restack** is selectable in Call Selection by the Aug-1 window (else Open Call +
      email NLnet to confirm routing).
- [ ] Trim each field to NLnet's "short and to the point" norm before pasting into the form.
- [ ] Keep defence framing **out** — this is the civilian open-infrastructure face.
