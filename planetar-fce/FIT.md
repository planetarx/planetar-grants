# Fit + go/no-go — Reliable AI sensor fusion (Fusion Compliance Engine)

- **Recommendation:** **LEAN BID — Component 1a (TRL 1–3, ≤$250K, ≤6 mo).** This is the
  **first IDEaS challenge whose *Essential* outcomes are pure software/AI** — the exact
  bar that sank the two prior no-bids ([`../planetar-true-north`](../planetar-true-north/DECISION-no-bid.md),
  [`../planetar-innovation`](../planetar-innovation/DECISION-no-bid.md), both killed by
  hardware Essentials). Decision owner: **Steven Ness.** Not yet committed — gated on the
  three checks in "Before committing."
- **Date:** 2026-06-22.
- **Deadline:** 2026-07-14 14:00 EDT (~3 weeks; confirm on CanadaBuys Guide).

---

## The one thing to understand: this challenge inverts the CH13 re-center

CH13's 2026-05-30 re-center made the **learned fusion model** the thesis and **demoted the
provenance substrate** (per-message `correlation_id`/`causation_id`/`source`, append-only
**CRC32 WAL**, per-edge provenance in the entity graph) to "enabling infrastructure."

**This challenge wants that demoted substrate as the hero.** The FCE *is* a
provenance/audit/policy-enforcement layer between ingestion and fusion. The learned fusion
model becomes background here; the **bus + envelope + WAL + entity-graph provenance**
become the scored core. We already built most of the primitive form.

> **Strategic consequence:** do **not** copy-paste the CH13 learned-fusion narrative. The
> scored thesis here is **compliance-by-design / sovereign Canadian audit + lineage**, with
> fusion assumed. Novelty (the PRC-2 equivalent) must be about the *enforcement engine*,
> not the embedding model.

---

## Essential-outcome → planetar-asset map (the must-pass gate)

| FCE Essential outcome | planetar asset today | Gap to close in a 1a |
|---|---|---|
| **EO1** Modular component enforcing policy during ≥2-sensor fusion | `planetar-broker` sits exactly between ingestion and fusion; AIS/SAR/EO/acoustic already publish onto it | The *enforcement/tagging logic* is net-new — but it's a bus middleware, not a rebuild |
| **EO2** Machine-readable policy; ≥2 modalities, Network-security domain, ≥Protected B | `planetar-market` ships **W3C ODRL machine-readable licenses** + provenance manifests — directly repurposable as the policy language | Map ODRL → classification/release-authority vocabulary; add Protected B / domain tags to the `zmesg` envelope |
| **EO3** Programmatic checks during ingestion/fusion, no human approval | Bus is already the automated chokepoint every message crosses | Add a synchronous policy-check hook on publish/subscribe |
| **EO4** Provenance records: source ID, classification, timestamp, domain | `zmesg` envelope **already carries** UUIDv7, ns timestamps, topic, `source`, correlation/causation | Add `classification` + `domain` fields (small, additive) |
| **EO5** Audit logs: rules applied + actions (permit/restrict/downgrade/segregate) + dispositions | **CRC32 append-only WAL** already records every message immutably | Add the enforcement-action + disposition record type to the WAL |
| **EO6** Exportable data-lineage from ingestion → fusion output | causation chain + WAL = replayable lineage; `planetar-ontology` tracks provenance **per-edge** | Add an export/accreditation format |

**Read:** every Essential maps to an **existing primitive** + a **small additive change**.
No Essential requires hardware we don't have, data DND won't give, or capability outside
software. That is the structural difference from the two no-bids.

### Desired outcomes — where we're already strong
- **Real-time at tactical speed:** the `zbroker0` benchmark (p50 80–140 ns / p99 400–900 ns
  SHM) is *directly* the "no added latency" selling point. The FCE's whole risk is latency;
  we can show a measured ns-scale chokepoint.
- **Adaptable policy without restart:** ODRL policies are data, not code → hot-reload story.
- **SWaP / edge:** the dependency-light single-file **C** broker (~1.5k LOC) is a genuine edge artifact
  (the Tactical-Edge/Dismounted example asks for exactly a ruggedized-laptop deployment).
- **Explainability + override:** the `planetar-ui` shell already clicks from a detection
  back through its causation chain to raw inputs — that's "human-readable compliance
  decisions" for free.

---

## Why this is the strongest IDEaS fit yet (vs. the two no-bids)

| Test that killed prior bids | True North (/012) | ISC TS13 | **FCE (this)** |
|---|---|---|---|
| Essential outcomes are software/AI, not hardware | ❌ hardware (laser, airframe) | ❌ hardware (TRL 7 platforms) | ✅ **all software** (policy, provenance, audit) |
| Honest TRL lane exists for a solo software bid | only 1a, weak | ❌ needs TRL 7–9 | ✅ **1a (TRL 1–3) is the natural lane** |
| Maritime / ISR / fusion domain | partial | partial | ✅ **MDA named as an example** |
| Reuses existing planetar substrate | thin | thin | ✅ **bus/envelope/WAL/graph are the core** |
| Sovereign-Canadian-IP framing rewarded | yes | yes | ✅ explicit "sovereign Canadian FCE" ask |

Plus heavy **reuse from `CP6-132484`**: GBA+ analysis, portfolio/credentials, the
provenance-substrate architecture text, the benchmark report, compute estimate, glossary,
and the patent framing (named-inventor background) all transfer with light edits.

---

## Risks / honest cautions

1. **Thesis pivot, not copy-paste.** Our novelty IP is the *fusion model*; this challenge
   scores the *compliance engine*. We must author a genuinely new novelty story (the FCE
   approach), or we look like we're retrofitting a maritime demo onto a compliance ask.
2. **Classification/Protected-B realism.** EO2 names Network security + Protected B. We
   can *design* to these and demo on synthetic markings at TRL 1–3, but we must not
   overclaim handling real classified data (we won't have it — DND provides none).
3. **3-week clock, solo, right after CH13.** Same constraint that shaped the no-bids —
   but here the substrate exists, so the 1a is a *concept-definition + design + small
   prototype* of an FCE on the existing bus, which is achievable solo in the window.
4. **Component choice.** 1a (TRL 1–3) is the honest lane: the *FCE itself* is concept-stage
   even though the substrate is ~TRL 3. Do **not** reach for 1b/2 — the engine isn't TRL 4+.
5. **Don't split focus across both siblings.** Challenge 2 (urban) also fits the modality
   detectors, but it pulls toward urban/drone and away from the provenance-compliance core
   that makes Challenge 1 a standout. See below.

## Challenge 2 (urban data) — secondary, lighter fit

Real but weaker. `planetar-eo` (cameras) + `planetar-acoustic` + RF + the bus map well to
the **Urban Counter-UAS** example (fuse traffic-cam + acoustic + passive RF to track
drones), and the Essentials are software. But: (a) it's an **urban/drone domain pivot** off
maritime; (b) the differentiator is "repurpose existing civic feeds," which is integration
breadth, not our provenance/audit moat; (c) privacy-of-civilian-data compliance is a new
burden. **Verdict: bid Challenge 1; treat Challenge 2 as a fallback only if Ch1's
Solicitation Guide disqualifies us.** If pursued, it gets its own `planetar-urban/` folder.

---

## Before committing — gate status (updated 2026-06-22)

The pre-conditions are now **mostly cleared** (CH14 PDF + CanadaBuys notice read):

1. ✅ **Solicitation + deadline:** `W7714-248676/014` (CH14), closes **2026-07-14 14:00 EDT**.
2. ✅ **Criteria/Components:** CH14 reuses CH13's CFP6 framework wholesale — MC-1/MC-2 +
   PRC-1…7 (10/20/20/20/5/15 + budget), 70-pt threshold, 3,000-char caps, **1a/1b/2 ladder
   with 1a (TRL 1–3) the honest lane**. The CH14 PDF adds no challenge-specific scoring. We
   already own the governing doc (Amendment 2) from `/013`.
3. ⏳ **Multiple-bid rules** — verify in the in-hand Amendment 2 (only matters if we also want
   the urban sibling; not blocking a CH14-only bid).
4. ⏳ **No later amendment** than Amendment 2 changes caps/criteria — quick check.

**The gate is effectively green.** The two ⏳ items are confirmations against a doc already in
hand, not new unknowns. This is the **highest-fit IDEaS opportunity to date and the cheapest
to draft** — the substrate exists, the evaluation framework is one we've already passed once,
and ~80% of the CH13 supporting artifacts transfer. The only real authoring work is the
**new FCE novelty/feasibility narrative** (the thesis pivot in §1) and the additive envelope
fields (classification/domain) + WAL enforcement-record type.

**Recommendation stands: BID Component 1a.** Suggested next step → scaffold a `planetar-fce/`
proposal workspace mirroring `planetar/` (reuse the CH13 spine; swap the thesis to
compliance-by-design).

## Sources

- Challenge text + facts: [`CHALLENGE.md`](CHALLENGE.md)
- Prior no-bid rationale (the software-Essentials bar): [`../planetar-true-north/DECISION-no-bid.md`](../planetar-true-north/DECISION-no-bid.md), [`../planetar-innovation/DECISION-no-bid.md`](../planetar-innovation/DECISION-no-bid.md)
- planetar substrate + CH13 reuse: `../../planetar/docs/submission-record.md`, `../../planetar/docs/recenter-learned-fusion.md`, `../../planetar-market` (ODRL policy)
