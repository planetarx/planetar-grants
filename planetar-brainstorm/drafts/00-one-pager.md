# planetar — one-pager (reusable)

> Reusable project overview for grant applications, sponsor pages, the website "About",
> and partner outreach. Claims here are **auditable** (repo paths / measurements /
> citations) — keep them that way; don't soften into marketing. Civilian-forward framing;
> dual-use noted where honest. `[TODO]` = founder-only fact to fill in.

---

**planetar — open, real-time situational awareness for the ocean.**

## The problem

A vessel that wants to disappear simply switches off its AIS transponder. These
"dark vessels" are behind illegal fishing, smuggling, sanctions evasion, and undetected
pollution — and they're invisible to any single sensor. Seeing them means **fusing many
sensors in real time** (AIS, satellite radar, cameras, underwater acoustics, radio) and
re-identifying the *same* vessel across all of them, fast enough to act. The tools that
can do this today are closed, expensive, and locked to single vendors.

## What planetar is

An **open-source platform** that fuses multi-sensor maritime data into one live picture,
built on five layers:

1. **Envelope** (`zmesg`) — a compact, self-describing message format with built-in
   provenance (every message carries UUIDv7 ids, nanosecond timestamps, and
   correlation/causation links). *Permissively licensed — meant to be a shared standard.*
2. **Bus** (`planetar-broker`) — a nanosecond-scale message bus (shared-memory + TCP/UDP)
   with a write-ahead log. *Permissively licensed.*
3. **Detectors** — per-sensor services that turn raw feeds into typed events: live AIS,
   Sentinel-1 SAR, electro-optical (webcams/YOLO), and hydrophone acoustics.
4. **Entity graph** — identity resolution that merges detections into vessel entities with
   full lineage, including kinematic **dark-vessel re-identification**.
5. **Shell** — a Slack/Palantir-style 4-pane analyst interface over a WebSocket bridge.

## What's actually built today (auditable)

Not a concept — working code, open-sourced 2026-05-15:

- **Nanosecond bus**: p50 ≈ **80–140 ns** shared-memory message latency (measured,
  1M-message benchmark, predecessor `zbroker0`, 2026-04-27); ~34 µs p50 over TCP
  (`planetar-broker`, 2026-05-14). Re-benchmark of `planetar-broker` SHM in progress.
- **Four working detectors** on live/real data: AIS (Victoria BBox, per-vessel channels),
  SAR (Sentinel-1 → CFAR, validated on a 433 Mpx scene), EO (public webcams → YOLO11n),
  acoustic (hydrophone → CAR-FAC cochlear model → classifier).
- **Entity-graph service** with identity resolution, merge, and a dark-vessel kinematic
  re-ID rule (`planetar-ontology`, 30 tests passing, zero runtime dependencies).
- **Analyst shell** (`planetar-ui`, React 19) bridged live to the bus.
- ~12,000+ LOC across 8 repos; all gitleaks-scanned clean.

## Dual-use

The same fusion + re-ID backbone serves **search-and-rescue, fisheries enforcement, and
pollution / whale-strike monitoring** (civilian) and **maritime domain awareness**
(defence). Civilian-first; defence applications pursued through separate channels.

## Who's building it

**Steven Ness, PhD** (Computer Science, University of Victoria, 2013) — `[TODO: confirm
company/role wording per C1]`. Background: published hydrophone event-detection on
**Ocean Networks Canada / NEPTUNE Canada** data (Sattar et al., IEEE PacRim 2011, 95%
accuracy); large-scale bioacoustic ML (the Orchive, ORCA-SLANG / Interspeech 2021);
**named inventor on US Patent 10,936,582** (entity resolution across distributed systems;
Salesforce-assigned, 1 of 19 named inventors). h-index 15, ~1,300 citations.

## Open-source posture

Permissively-licensed **bus + envelope** (interoperability substrate, maximize reuse);
**AGPL-3.0** platform (detectors, fusion, entity graph, shell). Commercial licenses
available for the AGPL components.

## Status & links

- Repos: `github.com/planetarx/*` and `github.com/sness23/zmesg`
- Website: `[TODO]` · YouTube: `[TODO]` · Demo video: `[TODO: dark-vessel demo]`
- Support / sponsor: `[TODO: GitHub Sponsors + Open Collective links]`
- Contact: Steven Ness — `[TODO: email]`

## The ask (tailor per use)

- **Grant funders:** non-dilutive support to harden the open bus + envelope as reusable
  infrastructure and ship the civilian maritime-safety reference application.
- **Sponsors:** recurring support via GitHub Sponsors / Open Collective; scoped tiers.
- **Partners (data / research):** access to live sensor streams (e.g., ONC hydrophone /
  observatory data) and joint validation.
