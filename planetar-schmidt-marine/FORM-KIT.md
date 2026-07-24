# Schmidt Marine — initial-proposal form kit (matched to the LIVE form, 2026-07-24)

> Form: https://airtable.com/appAz0pWLtt9SwFl1/paghIRHWLBhEQPDw6/form · **closes 2026-07-31 12:00 PM PST**
> (a midday cutoff). Verified live 2026-07-24. **Civilian face only (D3)** — no defence language.
> Short intake, **no uploads/attachments**, ~200-word advisory caps (not enforced). Paste top-to-bottom.

## Founder decisions — CONFIRMED 2026-07-24

- **SMTP Focus Area:** **Sustaining Fisheries** (pick this radio).
- **Requested Amount (year-1 band):** **$150,000–$200,000**. **Total Project Budget:** **$350,000**.
  *(Reshapes D6's "$200K/18mo" — the form asks for 1 year of funding with annual renewals, not an
  18-month total.)*
- **Work Title:** **Founder & CEO**.
- **TRL:** **3** (rating the funded work — the re-ID model at proof-of-concept — not the platform
  substrate; within Schmidt's TRL 2–6 band).

## Project Overview

**Project Title:**
planetar — open-source, real-time sensor fusion to find the fishing vessels that don't want to be seen

**Short Project Description (1–2 sentences, HARD CAP 250 chars — 236 below):**
Open-source platform fusing AIS, radar, cameras and hydrophones into one live picture of who's on the water — including "dark" vessels that fish illegally with their transponders off. It funds a model to re-identify them across sensors.

**SMTP Focus Area (radio, pick one):** Sustaining Fisheries

**Technology Type (multi-select, pick all):** Artificial Intelligence (AI) & Machine Learning · Sensors & Acoustics · Observing Systems

## Primary Contact Information

- **First Name:** Steven · **Last Name:** Ness
- **Work Title:** Founder & CEO
- **Email Address:** sness@sness.net
- **Website:** https://planetar.ca
- **Organization:** Zax Analytics
- **Organization Location:** Canada
- **Organization Type (radio, optional):** For-profit

## Project Description

**Problem** (advisory <200 words):
Illegal, unreported and unregulated (IUU) fishing thrives in a simple blind spot: enforcement sees the ocean one sensor at a time. AIS transponders — the beacons that announce a vessel's identity and position — can be switched off at will, and vessels fishing in closed or protected areas routinely go dark. Satellite radar passes are intermittent, coastal cameras don't reach open water, and hydrophones hear only what is nearby. The tools that fuse these feeds into a single picture exist, but they are closed, expensive, and vendor-locked — built for navies and priced out of reach. The organizations with the actual mandate to act — fisheries enforcement agencies, marine protected areas, coastal states, and conservation groups — are exactly the ones that cannot afford them. So a vessel that wants to disappear usually can, and illegal fishing continues in plain sight.

**Solution** (advisory <200 words):
planetar is an open-source, real-time fusion platform that ingests AIS, Sentinel-1 satellite radar, coastal cameras, and hydrophone acoustics, correlates them, and re-identifies vessels across sensors — so a vessel that goes dark on AIS can still be tracked as the same physical object in radar, imagery, and sound. A working prototype is live today at planetar.ca, fusing real feeds over two operating areas, on a public, auditable data fabric that carries provenance on every observation. This grant funds the core research: a self-supervised cross-modal re-identification model. While a vessel still broadcasts AIS, its radar, visual, and acoustic signatures co-occur with a known identity — free training pairs, no manual labeling. We train on that co-occurrence, then match a dark vessel's signature back to the identity it learned. Everything ships open source — a permissively-licensed interoperability core and an AGPL platform — so any fisheries agency or conservation group can deploy and audit the full stack themselves, rather than buying a closed black box.

**Impact** (advisory <200 words):
IUU fishing is one of the largest drivers of overfishing and a direct threat to ocean health, food security, and coastal livelihoods — and it depends on not being seen. By making dark vessels visible with open, affordable tools, planetar puts real monitoring capability in the hands of the organizations that need it most: fisheries agencies, marine protected areas, coastal states, and conservation groups, especially smaller operators priced out of closed systems. Two things make the impact durable. First, it is open source: one shared, auditable stack that any group can run and improve, instead of per-country procurement of proprietary black boxes — the economics that keep monitoring out of reach today. Second, every detection carries provenance and an evidence chain, so results are contestable and usable — monitoring you can trust rather than an opaque score. The same open architecture extends naturally to marine-mammal protection, pollution monitoring, and search-and-rescue. The goal is public-good ocean-observing infrastructure that strengthens the whole marine-conservation ecosystem, not a single closed product.

**Project Location (multi-select):** Canada · Global *(demo is the Salish Sea; the problem is global)*

**TRL (dropdown):** 3 *(rating the funded work — the self-supervised cross-modal re-ID model, at analytical/experimental proof-of-concept. It advances on top of a working platform substrate that is itself further along; within Schmidt's TRL 2–6 band)*

**Total Project Budget:** $350,000 *(the full ~2-year research program: model development, integration into the live stack, published evaluation, and deployment documentation)*

**Requested Amount (year-1 band):** $150,000–$200,000

**Team Description:**
Steven Ness — founder and CEO of Zax Analytics (Victoria, BC, Canada) — is building planetar solo. He holds a PhD in Computer Science (University of Victoria) and has published peer-reviewed ocean-bioacoustics research using Ocean Networks Canada hydrophone data (IEEE PacRim 2011) and on large-scale killer-whale call identification (Interspeech 2021); planetar's acoustic pipeline descends directly from that work. He is an applicant-named inventor on US Patent 10,936,582 (entity-resolution architecture; one of nineteen inventors) — the discipline behind planetar's cross-sensor vessel re-identification. He has built the entire existing prototype himself — the real-time message bus, the typed data envelope, four sensor pipelines (AIS, satellite radar, cameras, hydrophones), the entity-resolution graph, and the analyst interface — live at planetar.ca.

## Notes

- **No conflicts/relationships field** exists on the initial form, so the **C2 disclosure** (spouse
  at Open Ocean Robotics) has no home here — disclose proactively **if** a full-proposal stage or a
  later field asks. Don't force it into an unrelated field.
- **Referral** (optional dropdown) is a Schmidt-staff-name picker — leave blank unless a staff member
  requested this application.
- If **Ocean Observing** is chosen instead of Sustaining Fisheries, no text changes — only the radio.
- Other/pending funding: the Government of Canada CH14 proposal is under evaluation. There is no
  "other funding" field on the initial form; disclose honestly only if a later stage asks, and
  never lead with the defence framing (D3).
