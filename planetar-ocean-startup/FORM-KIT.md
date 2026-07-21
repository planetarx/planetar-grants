# OSC 2026 — form kit (built 2026-07-20 against the LIVE Airtable form)

> ⏰ **Closes 2026-07-26 @ 11:59pm** (timezone unstated — assume **ADT**, i.e. 7:59pm Pacific;
> don't cut it close). Form re-verified OPEN 2026-07-20 (live Airtable, active Submit).
> **No save-and-continue** — everything below must be final before you open the form.
> Field order below = the real form's order. Label line, then the paste value on the next line.
> `[FOUNDER]` = only you can answer; nothing invented.

## ⛔ Three asset blockers (the critical path — text is done, these are not)

1. **Video (3 min max, link required).** Script drafted below (§Video). Record + upload
   (YouTube unlisted / Drive), paste link.
2. **Pitch deck (link required).** ⚠️ The CH14 one-pager is defence-framed — **do not reuse**
   (D3: civilian face here). A civilian deck must be made; slide outline below (§Deck).
3. **Budget file (upload, their template).** Make a copy of the form's linked template and
   fill from §Budget below; export PDF/xlsx.

---

## General Information

Cohort:
2026 Ocean Startup Challenge | Concours Startup Des Océans

Preferred Language:
English / Anglais

Company Name:
Planetar

*(pre-incorporation venture name; matches planetar.ca. The form itself says incorporation is
only required before funding release — consistent with the apply-as-individual plan.)*

Website or Social Media:
https://planetar.ca (live demo) · https://github.com/planetarx (open-source repos)

Is your company/technology based on research conducted at a university?
**Recommend: No** — built independently in 2026; the founder's UVic PhD and Ocean Networks
Canada publications are background expertise, not licensed university IP. `[FOUNDER confirm]`

Has this startup been incorporated?
No

Have you raised equity investment for this solution/company?
No

Have you generated any revenue with this startup?
No

## Team or Founder

Main Applicant Name:
Steven Ness

Main Applicant Pronouns:
`[FOUNDER]` (option: prefer not to answer)

Main Applicant Email:
sness@sness.net

Main Applicant Phone:
`[FOUNDER]` — the standing missing founder input (same as NLnet)

Do you have a co-founder?
No

Do you have additional co-founders?
No

Which province(s) are you located in?
British Columbia

Have you or any of your Co-Founders participated in any other Ocean Startup Project programs?
`[FOUNDER]` — presume No; select honestly

Have you participated in any other startup support programs outside of the Ocean Startup Project?
`[FOUNDER]` — if none: "No."

Have you or your Co-Founder started a company before?
Yes — `[FOUNDER phrasing]`; suggested: "Yes — the founder is CEO of Zax Analytics, an
established Victoria BC software consultancy. This ocean venture is being run as a separate,
new entity (to be incorporated on selection)."

How much total time are you working on this startup?
`[FOUNDER]` — pick the honest band (options: 40+ / 35–40 / 15–35 / <15 h/wk)

How many Full-Time Equivalent (FTE) employees do you currently have?
0

## Problem Understanding and Market Opportunity

Does your startup fall under any of the industries below?
*(options unknown until the form is open — pick the maritime-safety / ocean-observing /
fisheries-adjacent options; select all that apply)*

What are current alternatives in the market addressing this problem?
Most operators still rely on single-sensor tools and manual watchkeeping: an AIS feed on one
screen, a radar picture on another, cameras on a third. Each is easy to evade alone — AIS can
simply be switched off, satellite radar passes miss small craft between revisits, and cameras
fail at night and in weather. Commercial fusion platforms exist at the high end (closed
maritime-intelligence suites sold to navies, insurers and large agencies), but they are
expensive, proprietary and vendor-locked: a port authority, a fisheries enforcement office or
a conservation NGO cannot afford them, cannot audit how they reach their conclusions, and
cannot run them on their own infrastructure. At the open end, Global Fishing Watch has proven
the demand for vessel-behaviour transparency, but it is a global batch-analysis service, not
a real-time local operating picture an operator can point at their own harbour, strait or
marine protected area. The gap between those two poles — affordable, open, real-time,
locally-deployable multi-sensor fusion — is where this venture sits.

How will your solution be better than what is currently on the market?
Three advantages. (1) Open and auditable: the entire stack is open source — a message bus and
typed envelope under a permissive licence, the platform under AGPL — so any harbour master,
enforcement office or NGO can inspect it, run it on commodity hardware, and never be locked
in. Every detection carries provenance (which sensor, when, via which processing steps), so
conclusions are traceable rather than black-box. (2) Real-time cross-sensor re-identification,
including dark vessels: the system fuses live AIS, free Sentinel-1 satellite radar,
electro-optical camera detections and hydrophone acoustics into one entity graph that links
the same vessel across sensors — so a vessel that switches off its AIS does not vanish, it
becomes a correlated radar/camera/acoustic track. (3) Cost structure: public and low-cost data
(Sentinel-1 is free; AIS and webcams are cheap; hydrophone feeds exist through Ocean Networks
Canada), commodity hardware, and a measured low-latency core — the fusion bus is benchmarked
at nanosecond-scale message handling — mean the whole system runs at a price point smaller
coastal operators can actually afford.

## Customer Discovery & Market Interest

Have you conducted customer research with individuals experiencing this problem?
`[FOUNDER]` — answer honestly. If the honest answer is "not yet formally": the $25K plan's
third workstream is exactly this (structured discovery + one scoped design-partner pilot with
a port authority, DFO fisheries, or a marine-conservation NGO). If a text box accompanies a
"Yes", describe only real conversations.

## Proposed Solution

What are you building to address this problem?
Planetar is an open-source, real-time multi-sensor fusion platform for maritime domain
awareness. Live sensor streams — AIS transponder data, Sentinel-1 satellite radar scenes,
electro-optical camera feeds, and hydrophone acoustics — flow over a low-latency message bus
into an entity graph that resolves detections from different sensors into one vessel identity,
with per-edge provenance, and surfaces the fused picture in an analyst console. The core
capability is re-identifying vessels across sensors, including "dark" vessels operating with
AIS off — the central enforcement gap in illegal, unreported and unregulated (IUU) fishing,
and equally relevant to search-and-rescue and pollution monitoring. It is working today on
live data out of Victoria BC: live AIS ingest for the Salish Sea, Sentinel-1 radar vessel
detection validated on a real 433-megapixel scene, webcam-based vessel detection, hydrophone
acoustic classification descended from the founder's published Ocean Networks Canada work,
and a working cross-sensor re-identification rule — roughly 24,000 lines of open-source code
across nine public repositories (measured 2026-07-20), with a live demonstration at
planetar.ca. The $25K would fund a validation sprint: quantify dark-vessel detection and
re-identification performance on real regional traffic, package a reproducible containerized
deployment, and run one design-partner pilot.

Describe your company in one sentence.
Open, real-time multi-sensor fusion that gives ocean operators one live picture of who is on
the water — including vessels trying not to be seen.

Does your solution have any novel inventions or designs that will need to be protected (IP)?
The strategy is open source rather than patents: the message bus and envelope are permissively
licensed (Apache-2.0) and the platform is AGPL — protection comes from copyright, licence
terms and being the reference implementation, which is deliberate for public-good ocean
infrastructure. The founder brings relevant prior art expertise as an applicant-named inventor
on US Patent 10,936,582 (entity resolution; Salesforce-assigned — named-inventor credit, not
an asset of this venture). A trademark on the Planetar name may be registered as the venture
incorporates.

How will you monetize this solution?
Open-core model on a dual-licensed stack: the platform is AGPL, so organizations that want to
embed it in closed products purchase commercial licences, while the open version remains free
for public-interest users. Revenue lines, in order of nearness: (1) paid design-partner pilots
and deployment/integration contracts for ports, enforcement agencies and NGOs; (2) a hosted,
managed instance (subscription) for operators who don't want to run infrastructure; (3)
commercial licensing and support agreements as adoption grows. The near-term $25K validation
sprint feeds line (1) directly by producing the benchmark evidence and the first pilot.

Select below what best describes your solution:
*(dropdown — pick the software/data-platform option)*

What stage are you at with this solution?
*(dropdown — pick working prototype / pre-revenue)*

What technology readiness level are you at?
**TRL 4** — the platform substrate is built and demonstrated with components running on live
feeds (verified against the repos 2026-06-22, `planetar-diana/FIT.md`). Within the ≤6 gate.
*(Consistency note, for the record: the CH14 bid filed the FCE **enforcement engine** — a
different, not-yet-built component — at TRL 2. Different scope, both honest.)*

Provide a link/URL to your current pitch deck:
`[BLOCKER — build civilian deck; outline in §Deck below]`

## Use of Funds — §Budget (fill their template; $25,000 total)

| Line | Amount | Justification |
|---|---|---|
| Live-data validation campaign (founder time: dark-vessel detection + cross-sensor re-id benchmark on Salish Sea traffic; published open) | $12,000 | The evidence that unlocks pilots and follow-on funding |
| Packaged reproducible deployment (containerization, install docs, commodity-hardware profile) | $5,000 | What a design partner actually runs |
| Design-partner pilot (discovery + scoped trial with port / DFO / conservation NGO) | $4,000 | First customer evidence; feeds monetization line 1 |
| Compute + data (Sentinel-1 processing, hosting planetar.ca through the sprint, AIS feed) | $3,000 | Direct validation-run costs |
| Contingency | $1,000 | Their templates typically include one |

*(Adapt lines to the template's categories; check the info kit's eligible-expenses list —
founder time may need to be framed per their rules.)* `[FOUNDER: confirm final split]`

## §Video — 3-minute script (record casual, per their guidance)

**[0:00–0:40] Who I am.** "I'm Steven Ness, in Victoria BC. I have a PhD in computer science
from UVic, where I spent years doing machine learning on Ocean Networks Canada hydrophone
data — I built the Orchive, a 30-year archive of orca recordings. I've since built
entity-resolution systems at scale in industry — I'm a named inventor on a US patent in that
area. What I care about is ocean infrastructure anyone can use. Knowledge gap I'll be honest
about: I'm an engineer-scientist, not a salesperson — customer discovery is exactly what this
program and this funding help me do."

**[0:40–1:30] The problem.** "Every sensor watching the ocean is easy to evade on its own.
A fishing vessel that wants to disappear just switches off its AIS transponder. Radar
satellites only pass overhead a few times a day. Cameras don't see at night. The tools that
fuse all of these exist — but they're closed, expensive, and sold to navies and insurers.
A port authority, a fisheries officer, or a whale-protection NGO can't afford them and can't
audit them. Meanwhile IUU fishing alone costs billions a year and dark vessels are the core
of it. That's urgent, and it's getting worse as fleets get smarter about hiding."

**[1:30–2:20] What I built + value.** "Planetar is open-source, real-time sensor fusion. Live
AIS, free Sentinel-1 satellite radar, cameras, and hydrophones flow into one entity graph
that re-identifies the same vessel across sensors — so going dark doesn't make you invisible,
it makes you a correlated track. It's running today on live data at planetar.ca — you can go
click on it. About twenty-four thousand lines of open code, nine public repositories,
commodity hardware, public data. The value: the fused picture the big closed platforms sell,
at a price and an openness smaller operators can actually adopt."

**[2:20–3:00] Impact of funds.** "Twenty-five thousand dollars funds a validation sprint:
one, a real benchmark — dark-vessel detection and re-identification performance measured on
live Salish Sea traffic, published openly; two, a packaged deployment a partner can run;
three, one design-partner pilot with a port, fisheries enforcement, or a conservation group.
Those three things turn a working system into a fundable, sellable one — and the Ocean
Startup network is exactly where those first partners are."

## Self-Identification section
`[FOUNDER]` — all optional with prefer-not-to-answer; not drafted here.

How did you hear about the Ocean Startup Challenge?
`[FOUNDER]`

## §Deck — civilian pitch-deck outline (build before submitting; NOT the CH14 one-pager)

1. Title: Planetar — open real-time maritime domain awareness · planetar.ca
2. Problem: single sensors are evadable; fusion is closed + unaffordable (IUU framing)
3. Solution: fuse AIS + SAR + EO + acoustic → one entity graph, dark-vessel re-id
4. Live today: screenshot of planetar.ca + the 4 working detectors + 24k LOC open source
5. Why me: PhD (UVic/ONC acoustics), entity-resolution patent credential, solo-built stack
6. Market: ports · fisheries enforcement · conservation NGOs · SAR (open-core model)
7. The $25K sprint: benchmark → packaged deploy → design partner
8. Ask + contact

## C2 note
No conflicts/relationships field exists on this form. The C2 disclosure (spouse at Open Ocean
Robotics) applies **where asked** — if an interview or later stage asks, disclose proactively
per `../planetar-brainstorm/DECISIONS.md`.
