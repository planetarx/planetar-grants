# Ocean Startup Challenge — application prep (draft)

> ⏰ **Opens 2026-06-05 · closes 2026-07-26 23:59 · selection 2026-07-27 → 08-25.**
> Up to **$25K** in awards to up to **15 early-stage Canadian blue-tech startups**, **TRL ≤6**.
> Low effort, strong civilian-maritime fit, Victoria-based. *Verified live 2026-06-03.*
> The web form has **no save-and-continue** — draft every answer offline (here), then paste.
> Review the bilingual info package first. Apply: https://www.oceanstartupproject.ca/startup-challenge

---

## ⚠️ Eligibility — read before anything else

Confirmed criteria for the 2026–27 cohort:

| Criterion | Rule | planetar |
|---|---|---|
| Stage | Pre-revenue (pilot revenue OK) | ✓ |
| Prior investment | ≤ $250,000 | ✓ (bootstrapped) |
| TRL | **6 or lower** | ✓ TRL 1–3, lots of headroom |
| Company age | **≤ 5 years old** | ⚠️ **Zax Analytics is ~10 yrs → fails** |
| Team size | < 10 full-time employees | ✓ (solo) |
| Ownership | **Founders must be majority owners** | ⚠️ **Zax is in spouse's name → fails** |
| Location | Apply from anywhere; **winners register a Canadian entity** | ✓ |

**Consequence — do NOT apply as Zax Analytics.** The 10-year age and the spouse-ownership
both disqualify it here. Instead:

> **Apply as an individual (Steven Ness).** The rules let applicants apply from anywhere and
> only require *winners* to register a Canadian entity. **If selected, incorporate a NEW
> Canadian company with you as majority owner** (fresh = ≤5 yrs, pre-revenue, you control it).
> This keeps Ocean Startup eligible **and** leaves Zax Analytics free for the IRAP/SR&ED track,
> where its age + accountant are the asset. Same individual-vs-Zax split as the NLnet/Restack app.

*(This is the mirror image of C1: Zax's maturity helps the mature-corp programs and hurts the
early-stage ones. Run the two tracks on two different vehicles.)*

## Positioning (civilian-first)

planetar as **open situational-awareness infrastructure for the blue economy** — fuse
AIS + satellite radar + cameras + hydrophones in real time to detect and re-identify
vessels, including "dark" vessels that switch off AIS. Lead with the **civilian** uses
(maps onto the challenge's own "maritime safety / vessel efficiency" focus areas):

- **Illegal, unreported & unregulated (IUU) fishing** — detect vessels operating dark in
  protected/closed areas.
- **Search-and-rescue** — faster fused tracking of small/non-cooperative targets.
- **Pollution & marine-mammal protection** — bilge-dump and whale-strike risk monitoring;
  the acoustic detector descends directly from ONC/OrcaLab whale-call work.

## Draft answers (adapt to the real fields)

**One-line pitch.** Open, real-time multi-sensor fusion that gives ocean operators one
live picture of who's on the water — including vessels trying not to be seen.

**Problem.** A single sensor is easy to evade; AIS can be switched off, radar misses small
craft, cameras don't see at night. Existing fusion tools are closed, costly, and
vendor-locked. Coastal nations, ports, and conservation bodies lack an affordable, open,
auditable way to see the whole picture in real time.

**Solution.** planetar fuses AIS, Sentinel-1 SAR, electro-optical, and hydrophone acoustic
streams over a low-latency message bus into an entity graph that re-identifies the same
vessel across sensors, surfaced in an analyst shell. Open-source; runs on commodity
hardware and public/low-cost data.

**Why now / traction (auditable).** Working today on live data out of Victoria: live AIS
ingest, Sentinel-1 SAR detection (validated on a 433-megapixel scene), webcam EO detection,
hydrophone acoustic classification, and an entity-graph service with a working dark-vessel
re-identification rule. ~13k LOC across the open repos, open-sourced 2026-05-15; the bus
(`planetar-broker`) and envelope (`zmesg`) are permissively licensed (Apache-2.0).

**Team.** Steven Ness, PhD (UVic), **CEO of Zax Analytics** — published ML on **Ocean
Networks Canada hydrophone data**; built the Orchive (30-year orca-acoustic archive); named
inventor on US Patent 10,936,582 (entity resolution). *Applying as an individual; will
incorporate a new Canadian entity on selection (see eligibility note).*

**Blue-economy impact.** Affordable open MDA for fisheries enforcement, SAR, port
security, and marine-conservation bodies — especially smaller coastal operators priced
out of closed systems.

**Use of the $25K.** A focused TRL-raising validation sprint:
1. **Live-data validation campaign** in the Victoria approaches / Salish Sea — quantify
   dark-vessel detection + cross-sensor re-id performance on real AIS + Sentinel-1 + ONC
   hydrophone traffic (precision/recall, latency), published as an open benchmark.
2. **Packaged, reproducible demo deployment** (containerized) a design partner can run on
   commodity hardware.
3. **One design-partner pilot** — discovery + a scoped trial with a port authority, DFO
   fisheries, or a marine-conservation NGO.
4. **Compute + data costs** for the validation runs.

## Checklist & notes

- [x] Confirmed dates/amount/TRL/eligibility (live 2026-06-03). Re-confirm exact **form
      fields** when the portal opens 06-05 (no save-and-continue — draft offline).
- [x] Eligibility resolved: **apply as individual; new entity on win** (Zax is too old /
      spouse-owned — see eligibility note).
- [ ] **Disclose the OOR relationship if asked** (spouse works at Open Ocean Robotics, a
      blue-economy firm — C2 in [`../DECISIONS.md`](../DECISIONS.md)). Keep it clean.
- [ ] Re-verify the traction numbers before pasting (LOC, test count, 433-Mpx, 95% ONC) —
      pull current figures from the repos / CH13 spine.
- [ ] Reuse the hero demo video + one-pager ([`00-one-pager.md`](00-one-pager.md)).
- [ ] Lead civilian; do **not** lead with defence framing here.
- [ ] Mention the open-source angle — blue-tech programs favour sovereign, non-vendor-locked tools.

## Why this one is worth the small effort

Fast, cheap, local fit, and a **logo + cohort network** (Ocean Startup is a top-ranked
blue-economy accelerator) that strengthens later Ocean Supercluster and ONC conversations.
A $25K cheque is small, but the validation and network compound — and with a ~7-week window
(06-05 → 07-26) it's the most imminent concrete opportunity on the calendar.
