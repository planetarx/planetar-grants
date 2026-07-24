# Schmidt Marine — initial proposal (draft — SUPERSEDED)

> ⚠️ **Superseded 2026-07-24 by [`FORM-KIT.md`](FORM-KIT.md)** — the live Airtable form was verified.
> It's a short intake (Problem/Solution/Impact ≤200 words each, focus-area radio, TRL, banded
> year-1 ask, team) with no uploads. The form kit is the paste-ready version; this file is kept as
> the fuller source narrative. **Submit from the form kit.**

---

**Applicant:** Zax Analytics (Canadian corporation, Victoria BC; Steven Ness, CEO,
performing the R&D) — *decided 2026-07-04.* Disclose ownership + OOR facts per C2.

## Project title

**planetar — open, real-time multi-sensor fusion to find the vessels that don't want
to be seen**

## One-liner

Open-source infrastructure that fuses AIS, satellite radar, cameras, and hydrophones
into one live picture of who is on the water — including "dark" vessels that switch
off their transponders.

## Summary (~200 words)

Illegal, unreported and unregulated (IUU) fishing thrives in a simple blind spot:
enforcement sees the ocean one sensor at a time. AIS transponders can be switched off,
satellite radar passes are intermittent, cameras don't cover open water, and the tools
that fuse these feeds are closed, expensive, and vendor-locked — out of reach of most
coastal states, fisheries agencies, and conservation groups.

planetar is an open-source answer: a real-time fusion platform that ingests AIS,
Sentinel-1 synthetic-aperture radar, electro-optical camera feeds, and hydrophone
acoustics, correlates them, and re-identifies vessels across sensors — so a vessel that
goes dark on AIS can still be tracked as the same physical object in radar, imagery,
and sound. The working prototype is live today at planetar.ca, fusing real feeds over
two operating areas. The core research this grant funds: a **learned cross-modal
re-identification model, trained without manual labels** by exploiting the co-occurrence
of signals while vessels still broadcast AIS — then applied when they don't.

Everything ships open source (Apache-2.0 core, AGPL platform): a public-good ocean
observatory stack any agency or NGO can run and audit.

## The problem

- AIS is voluntary in practice: vessels fishing illegally in closed or protected areas
  routinely disable transponders ("going dark").
- Single-sensor monitoring is easy to evade and existing multi-sensor fusion is
  proprietary, priced for navies, and unauditable.
- The organizations with the mandate to act — fisheries enforcement, MPAs, coastal
  states, conservation NGOs — are exactly the ones that can't afford closed tooling.

## The technology (what exists today — verifiable)

All public repositories; working prototype live at **planetar.ca**:

- **Real-time fusion bus + typed message envelope** (Apache-2.0) — an auditable,
  low-latency data fabric for sensor streams, with provenance (unique IDs, nanosecond
  timestamps, correlation/causation chains) on every message. Measured conservatively
  at sub-microsecond delivery on a single host.
- **AIS ingest** — live vessel-position feeds, one channel per vessel.
- **Satellite SAR pipeline** — Sentinel-1 fetch → CFAR ship detection → track association.
- **Electro-optical pipeline** — public coastal webcams → vessel detection (YOLO).
- **Acoustic pipeline** — hydrophone audio → auditory-image classification; descends
  from ONC/OrcaLab whale-call work.
- **Entity graph + analyst shell** — identity resolution across feeds; a live operator
  UI showing the fused picture.

## What this grant funds (the research step)

A **self-supervised cross-modal re-identification model**: while a vessel broadcasts
AIS, its radar signature, visual appearance, and acoustic signature co-occur with a
known identity — free training pairs, no manual labeling. Train on that co-occurrence;
then, when a vessel goes dark, match its SAR/EO/acoustic signature back to the learned
identity. Deliverables over 18 months:

1. Curated cross-modal training corpus from the two live operating areas (open data).
2. Trained re-ID model + honest, published evaluation (precision/recall on held-out
   dark-vessel events); uncertainty reported, human-in-the-loop by design.
3. The model integrated into the live open-source stack + a public demo.
4. Documentation so a fisheries agency or NGO can deploy the full stack themselves.

## Why open source matters here

Monitoring tools used for enforcement should be **auditable** — evidence chains,
provenance on every detection, no black boxes. Open source also changes the economics:
one shared stack instead of per-country procurement of closed systems. The
interoperability core is permissively licensed (Apache-2.0) precisely so others can
build on it; the platform is AGPL so improvements stay public.

## Team

Steven Ness — solo founder, Victoria BC, Canada. PhD in Computer Science (University
of Victoria, 2013). Published hydrophone event-detection on **Ocean Networks Canada /
NEPTUNE Canada** data (Sattar et al., IEEE PacRim 2011) and large-scale bioacoustic ML
on the OrcaLab archive (the Orchive; ORCA-SLANG, Interspeech 2021) — planetar's
acoustic pipeline descends directly from this work. Applicant-named inventor on US
Patent 10,936,582 (entity-resolution architecture, 1 of 19 inventors). Built the entire
existing prototype solo. h-index 15, ~1,300 citations. CV/links: https://sness.net

## Traction

- Live system: planetar.ca (two operating areas, real feeds).
- Public open-source repositories (bus, envelope, four sensor pipelines, entity graph, UI).
- A Government of Canada R&D funding proposal for the fusion research is under
  evaluation. *(Include only if the form asks about other/pending funding — disclose
  honestly, don't lead with it.)*

## Budget & ask

**US$200,000 over 18 months** *(decided 2026-07-04)*. Rough shape: founder salary (the
team), GPU compute for model training, satellite-data + hosting costs, small
contingency. Hydrophone data via the planned Ocean Networks Canada relationship would
be in-kind, not budgeted. Mid-range of SMTP's stated US$100K–400K.
`[TODO: exact line items before submission]`

## Disclosures

- Spouse is employed at Open Ocean Robotics (ocean-tech sector, Victoria BC). No
  involvement in planetar. **(C2 — disclose proactively wherever the form asks about
  relationships or conflicts.)**
