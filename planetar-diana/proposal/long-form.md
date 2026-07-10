# Long-Form Proposal — content (transfer into DIANA's official 4-page template)

> ⚠️ **Content, not the submission.** DIANA requires its **official Long-Form template** (≤4 pages,
> font/format enforced; non-compliant = rejected). Download from the portal, paste this content in,
> and **cut to fit 4 pages** — this draft runs long on purpose so there's material to select from.
> Headings below map 1:1 to DIANA's **scoring criteria** (see [../CHALLENGE.md](../CHALLENGE.md)).
> Thesis SSOT: [../THESIS.md](../THESIS.md). Every claim traces to a repo path, a measurement, or a
> citation — keep it that way.
>
> Challenge: **Multidomain Sensing & Advanced Data Processing for Intelligence and Surveillance**.

---

## Summary

**planetar** is an open-source, provenance-native platform that fuses multi-domain sensors into a
single live operating picture and **re-identifies the same entity across those sensors** — including
vessels that switch off their AIS transponder to "go dark" (demonstrated end-to-end across SAR and
EO). It already runs on **real and live feeds** across four sensor domains, on a benchmarked
nanosecond message bus, with an analyst shell.
We seek the DIANA accelerator to advance the fusion + re-identification engine from **TRL 4 to
TRL 5/6** and validate it in a NATO-relevant environment, hardening it for contested,
multi-classification ISR. Because the backbone is open, it becomes shared interoperability
infrastructure across NATO sensor estates rather than another single-vendor silo.

## Technical — Alignment to the challenge

The challenge asks for sensor and data fusion across **platforms, formats, and security
classifications**, with **AI/analytics** producing **actionable, causality-based intelligence and
predictive insights**. planetar maps to each, with working code today:

- **Across platforms** — satellite (`planetar-sat`, real Sentinel-1 SAR via Copernicus, CFAR
  detection), satellite/terrestrial AIS (`planetar-ais`), ground electro-optical
  (`planetar-eo`, live harbour/coastal cameras, YOLO), and subsea acoustic (`planetar-acoustic`,
  live hydrophone via Ocean Networks Canada / OrcaSound, cochlear-model front end). All publish to
  one bus.
- **Across formats** — every sensor output is normalized into a compact, self-describing **`zmesg`
  envelope** (UUIDv7 ids, nanosecond timestamps, topic, correlation/causation ids), so
  heterogeneous feeds become one typed stream.
- **Across classifications** — the envelope + bus design carries per-message provenance and
  routing metadata; classification-aware partitioning / multi-level routing is the natural
  in-program extension (see Feasibility).
- **AI / analytics** — an entity-graph service (`planetar-ontology`) resolves observations into
  canonical entities and applies a **kinematic dark-vessel re-identification** rule to re-acquire
  tracks across sensors and across AIS gaps.
- **Causality-based & auditable** — because every observation and every merge carries lineage
  (UUIDv7 + correlation/causation links), each fused entity can answer *which observations, from
  which sensors, in what order* produced it. That lineage is the substrate for the challenge's
  "causality-based intelligence."
- **Predictive** — kinematic extrapolation forecasts where/when a vessel that dropped AIS should
  re-emerge, turning a gap into a cue.

## Technical — Novelty / innovation

The novel core is **provenance-native fusion**: fusion and re-identification performed on a
substrate where lineage and causality are first-class, not bolted on. Two consequences competitors
(closed, single-vendor C2 suites) do not offer together:

1. **Auditable fusion** — every conclusion is explainable down to source observations, which is
   what "causality-based" ISR and human-in-the-loop trust require.
2. **Open interoperability** — a permissively-licensed bus + envelope means *any* NATO sensor or
   analytic can join the stream without a vendor gate; the platform becomes shared infrastructure.

The entity-resolution approach is grounded in the applicant's prior art: **named inventor on US
Patent 10,936,582** (entity resolution across distributed systems; Salesforce-assigned, one of 19
named inventors). The nanosecond bus is a measured capability, not an aspiration:
**p50 ≈ 80–140 ns, p99 ≈ 400–900 ns** shared-memory message latency (1M-message benchmark; full
report in `planetar/docs/benchmark-2026-04-27.md`).

## Technical — Feasibility

The hard parts are already built and integrated; the in-program work is bounded engineering plus
validation, not invention.

- **Already integrated & verified** (TRL 4): AIS → bus → bridge → analyst shell, on two live
  theatres (Victoria, BC and the Strait of Hormuz), with dark-vessel AIS-drop behaviour on a live
  map (`planetar/HANDOFF-DEMO.md`, verified 2026-05-19); SAR → bus → shell channel; the entity
  graph verified live against the running bus (`planetar-ontology`, 30 tests); and
  **cross-sensor re-identification (SAR + EO) of a dark vessel demonstrated end-to-end** through the
  entity graph, surfaced in the analyst shell's entity-graph and map views
  (`planetar-ontology/tools/demo-reid.ts`; verified 2026-06, runbook in `planetar-diana/DEMO.md`).
- **In-program plan (TRL 4 → 5/6)** — building on the now-demonstrated cross-sensor re-ID:
  1. Classification-aware routing / multi-level-security partitioning so fusion spans security
     classifications.
  2. Learned multi-sensor association + probabilistic track prediction, beyond today's kinematic
     re-ID rule.
  3. Onboard additional platforms (autonomous/UAS, RF) via new detector adapters.
  4. Validate in a **NATO-relevant, contested environment** at a DIANA test centre (degraded comms,
     adversarial conditions); capture metrics.
- **Why feasible solo + with DIANA support:** the platform is ~12k LOC across focused repos with
  zero/low runtime dependencies; the architecture (envelope → bus → detectors → entity graph →
  shell) is already proven end-to-end, including cross-sensor re-identification. `[TODO: confirm
  in-program milestone calendar against the accelerator phase durations once the portal publishes
  them.]`

## Technical — Validity (evidence)

Every capability claim is auditable against a public repo, a measurement, or a citation:

| Claim | Evidence |
|---|---|
| Nanosecond bus | `planetar-broker` (~1.4k LOC C11, WAL, tests); benchmark `planetar/docs/benchmark-2026-04-27.md` |
| Four live/real sensor domains | `planetar-ais`, `planetar-sat` (real Sentinel-1), `planetar-eo` (live cams), `planetar-acoustic` (live hydrophone) |
| Cross-sensor re-ID | `planetar-ontology` (30 tests; dark-vessel kinematic rule; live-verified) |
| Cross-sensor re-ID **demonstrated** | SAR + EO re-acquire one dark vessel end-to-end; field-level provenance fused (AIS+EO); `planetar-ontology/tools/demo-reid.ts`, verified 2026-06 (`planetar-diana/DEMO.md`) |
| Normalized provenance envelope | `zmesg` (UUIDv7 + ns ts + correlation/causation) |
| Integrated end-to-end | `planetar/HANDOFF-DEMO.md` (verified two-theatre live demo) |
| Entity-resolution prior art | US Patent 10,936,582 (applicant named inventor) |
| Applicant track record | Bioacoustic ML on Ocean Networks Canada / NEPTUNE data (Sattar et al., IEEE PacRim 2011); Orchive / ORCA-SLANG (Interspeech 2021) |

**Honest TRL statement:** the platform substrate is at **TRL 4** (components integrated and
validated in a laboratory environment); several components reach **TRL 5** (validated on live,
real-world feeds), and cross-sensor dark-vessel re-ID is now **demonstrated end-to-end**. The
remaining TRL 4 → 5/6 work — what this program funds — is validation in a **NATO-relevant, contested
environment**, multi-classification routing, and learned multi-sensor association.

## Defence & security — Relevance & impact

- **Relevance:** maritime domain awareness and contested ISR depend on fusing exactly the sources
  planetar already ingests, and on re-acquiring actors who deliberately go dark — the central
  problem behind illegal fishing, smuggling, sanctions evasion, and grey-zone maritime activity.
- **Impact on NATO capability:** an **open** fusion backbone lets allied sensors and analytics
  interoperate without vendor lock-in, and the provenance layer gives commanders auditable,
  explainable intelligence for human-in-the-loop decisions. The same substrate generalizes beyond
  maritime to any multi-sensor ISR picture (land, air, space sensors emit the same envelopes).
- **Alliance fit:** built in Canada (NATO member); designed as shared infrastructure, not a
  national silo.

## Commercial & adoption — Viability & approach

- **Model:** open-core. **Permissively-licensed bus + envelope** (maximize interoperability and
  reuse) + **AGPL-3.0 platform** (detectors, fusion, entity graph, shell) with **commercial
  licenses** available — funding the open core through dual-licensing and integration/support
  services.
- **Adoption path:** civilian-first traction (maritime safety, fisheries, pollution monitoring,
  research partners such as Ocean Networks Canada) builds a referenceable, auditable capability;
  defence adoption follows the *same* codebase through DIANA's end-user and test-centre network.
- **Why dual-use is real, not a label:** the live demo's civilian use cases (SAR, whale-strike,
  illegal-fishing) and the defence use case (MDA / ISR) run on identical code; only the operating
  area and the consuming analyst change.
- `[TODO: insert any traction metrics — repo stars, pilot conversations, ONC/research-partner
  letters — before submission.]`

## General — Resources, dependencies & DIANA suitability

- **Team:** Steven Ness, PhD (Computer Science, University of Victoria), **Director & CEO of the
  applicant company, Zax Analytics** — large-scale bioacoustic ML, entity-resolution prior art
  (US Patent 10,936,582), and the author of the planetar stack. `[TODO: add any collaborators.]`
- **Dependencies:** open data/services already in use (Copernicus/Sentinel-1, aisstream.io, public
  webcams, Ocean Networks Canada / OrcaSound). No hardware dependency — the deliverable is
  software/AI, which fits the challenge and de-risks delivery.
- **What DIANA adds that money alone cannot:** access to **NATO-relevant test environments and
  military end-users** to validate the fusion + re-ID engine in a contested, multi-classification
  setting — the precise step from TRL 4 to 5/6 — plus the credibility to seed allied adoption of an
  open backbone.
- **Eligibility:** Applicant is **Zax Analytics**, a **British Columbia–registered company**
  (Canada, a NATO member nation), majority Canadian-owned and -controlled; lead/authorized
  representative **Steven Ness, Director & CEO** — satisfies DIANA's company + majority-NATO-national
  requirement.
- **DIANA suitability:** dual-use, open, interoperable, software-defined, and at the right maturity
  band (TRL 4+) — and the in-program plan produces a demonstrable capability within an accelerator
  cycle.
