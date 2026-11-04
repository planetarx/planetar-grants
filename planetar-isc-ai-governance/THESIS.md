# Thesis — governance as replayable evidence lineage (SSOT)

> Single source of truth for every narrative in this bid. If a draft drifts from this, fix the
> draft. Decided 2026-11-02 (lane: sprint to TRL 5 — [`PLAN.md`](PLAN.md)). **Draft until the
> 2026-12-15 TRL gate passes.**

## One sentence

> **A Canadian-built AI-governance assessor that turns each GC requirement (DADM, AIA, Policy on
> Service and Digital, AI Strategy) into a versioned, machine-checkable control, assesses every
> registered AI system against it from dated evidence, and records every finding, reviewer
> decision and requirement change in an immutable, replayable journal — so any compliance result
> can be reproduced, audited, and automatically re-opened when a requirement changes.**

## What is distinct (and what it is not)

- **Not the CH14 thesis.** CH14 (`../planetar-fce/THESIS.md`, under evaluation) is *runtime
  policy enforcement on sensor data at a bus chokepoint* (classification markings, release
  authority). This bid is *governance assessment of AI systems at the registry level*. Do not
  reuse FCE language ("chokepoint", "tag/permit/downgrade/segregate", "tactical edge").
  Shared substrate, different science.
- **Not maritime, not defence.** Face (D3): civilian GC enterprise IT. The maritime stack appears
  only as *one real AI system under governance* (the `planetar-fusion` learned SAR detector),
  never as the pitch.

## The science (what makes it more than GRC forms)

1. **Requirements-as-code with lineage.** Each requirement is a versioned control with an
   explicit evidence query; a requirement change is an event, and the set of affected systems is
   computed, not hand-triaged (Essential 1).
2. **Evidence-grounded findings with calibrated confidence.** Each finding = requirement +
   evidence pointer + result (met / partial / not met / N/A / unable to determine) + a
   confidence that is *measured* against reviewer-labelled ground truth, not asserted (E4).
3. **Replayable audit.** Findings, artifacts, reviewer actions and requirement versions are
   journalled append-only (the planetar CRC32 WAL lineage); any past assessment can be replayed
   bit-for-bit from the journal (E4, E5).
4. **Open standards for exchange.** Controls and assessment results exchanged in an open,
   published format (candidate: NIST OSCAL — *verify fit before claiming*), ODRL for data
   residency/retention/access policy (E2, E3).

## Built vs. to build (honesty spine)

**BUILT (verify each against the repo before citing):** typed envelope with UUIDv7 / ns
timestamps / causation ids (`zmesg`); append-only CRC32 WAL (`planetar-broker`); entity graph
with per-edge provenance and trace index (`planetar-ontology`, `GET /trace/:id`); ODRL policy +
catalog API (`planetar-market`); governed-ports policy enforcement point (`planetar-platform`);
an analyst UI with message trace (`planetar-ui`).

**TO BUILD in the sprint (the TRL 2 → 5 work):** the requirement/control model for DADM, AIA,
PSD, AI Strategy; AI Register ingest; the assessment engine and findings; reviewer workflow;
change-propagation; output/data-quality monitoring of one live model; open-format export.

**Claim TRL 5 only if** the gate in `PLAN.md` passes with evidence. Otherwise this becomes a
build-for-next-call (MINERVA lane-B pattern), and no TRL-5 language leaves this repo.
