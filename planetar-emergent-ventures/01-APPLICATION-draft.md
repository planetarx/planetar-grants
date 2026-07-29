# Emergent Ventures — application (draft — SUPERSEDED)

> ⚠️ **Superseded 2026-07-23 by [`EV-FORM-KIT.md`](EV-FORM-KIT.md)** — the live form was verified and
> is more structured than this draft assumed (required ≤295-char tweet, ≤1500-word proposal in a
> prescribed story→consensus-view→idea structure, no CV/website fields, optional budget). The form
> kit is the paste-ready version; this file is kept as history. **Submit from the form kit.**

---

**Name:** Steven Ness
**Email:** sness@sness.net
**Location:** Victoria, BC, Canada
**CV / LinkedIn:** https://sness.net

**Project title:** planetar — open infrastructure that finds ships that don't want to
be found

**Amount requested:** US$50,000 *(decided 2026-07-04)*

---

## Project description (draft — trim to form limits)

Ships that want to disappear just switch off their AIS transponder. That one gesture defeats most maritime monitoring on Earth — it's how illegal fishing fleets, sanctions evaders, and smugglers operate in plain sight. The sensors that could still see them (satellite radar, cameras, hydrophones) exist, but the systems that fuse those feeds are closed, priced for navies, and unauditable.

I'm building the open-source alternative, solo. planetar is live today at planetar.ca: a real-time fusion platform with its own sub-microsecond message bus (measured, not estimated), a typed provenance-carrying envelope, and working ingest pipelines for AIS, Sentinel-1 satellite radar, coastal cameras, and hydrophone acoustics, fused into an entity graph and a live analyst UI — running over two real operating areas. All of it is public, open source, and built by one person in months, not by a contractor in years.

The next step is the interesting one, and it's what this grant funds. While a vessel still broadcasts AIS, its radar signature, visual appearance, and acoustic signature co-occur with a known identity — which means the ocean is generating free labeled training data, continuously. I'm training a **self-supervised cross-modal re-identification model** on that co-occurrence, so that when a vessel goes dark, the system can match its radar/camera/acoustic signature back to the identity it learned — tracking the same physical ship across sensors without any transponder. Nobody offers this openly; the closed versions are classified or cost millions.

The grant buys the two things a solo founder can't bootstrap: GPU compute for model training, and months of focused runway to ship the model into the live system and publish an honest evaluation. The result is public-good infrastructure: any coastal state, fisheries agency, or conservation group gets an auditable dark-vessel monitoring stack they can run themselves — and the same architecture serves search-and-rescue and naval domain awareness. It's deliberately dual-use and deliberately open.

Why me: I built the entire existing stack alone — bus (C), envelope, four sensor pipelines, entity-resolution graph, UI. I'm an applicant-named inventor on US Patent 10,936,582 (entity-resolution architecture, 1 of 19 inventors), with a PhD in Computer Science (University of Victoria, 2013); my published research — hydrophone event-detection on Ocean Networks Canada data (IEEE PacRim 2011), large-scale orca-call ML on the OrcaLab archive (Interspeech 2021) — is the direct ancestor of planetar's acoustic pipeline. A Government of Canada defence-R&D proposal on this fusion research is currently under evaluation; this grant is independent of it and keeps the open-source core moving regardless of that outcome.

## How the money will be used (if asked)

*(split decided 2026-07-04)*

- Founder runway (focused months on the model + evaluation + release): **US$25,000**
- GPU training compute for the cross-modal re-ID model: **US$15,000**
- Satellite data access + hosting for the live demo: **US$10,000**

## Links (if asked)

- Live system: https://planetar.ca
- Repos: https://github.com/planetarx (platform) · https://github.com/sness23/zmesg (envelope)
- CV / everything else: https://sness.net
