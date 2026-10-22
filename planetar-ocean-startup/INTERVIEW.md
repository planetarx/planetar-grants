# OSC interview kit — Monday 2026-08-17, 3:00 PM EDT / 12:00 PM PDT

Prep for the 15-minute judging-panel interview (3-min pitch + 12-min Q&A). Written
2026-08-15. The panel already has: the written answers ([`FORM-KIT.md`](FORM-KIT.md)),
the 3-min video (recorded from the §Video script), and the deck
([`deck/planetar-osc-deck.pdf`](deck/planetar-osc-deck.pdf)). **The pitch is the warm-up;
the Q&A is the interview.**

## Logistics

- **Join by 11:58 AM PDT** — Zoom <https://us02web.zoom.us/j/82057750739> (also in the
  calendar invite). AV check first 2 minutes; slot is 12:00–12:12 PDT.
- Before the call: **verify planetar.ca is up and showing live vessels** (checked OK
  2026-08-15, HTTP 200 in 66 ms) — have it open in a tab, ready to share if invited.
- If presenting slides: use [`deck/planetar-osc-deck-interview.pdf`](deck/planetar-osc-deck-interview.pdf)
  (slide-6 licence card updated to the current GPLv3 + services model; source
  `deck/planetar-osc-deck-interview.html`) — **not** the filed PDF, whose slide 6 still
  says AGPL/commercial licences.
- Quiet room, tested mic/camera, phone hotspot as network backup, water, beat card by
  the camera.

---

## The 3-minute pitch (~380 words ≈ 2:40 at speaking pace — rehearse to ≤2:45)

**[0:00–0:25] Who I am.**  "I'm Steven Ness, in Victoria BC. I have a
PhD in computer science from UVic — years of machine learning on Ocean
Networks Canada hydrophone data, including a thirty-year orca acoustic
archive — and then industry entity-resolution at scale; I'm a named
inventor on a US patent in that field. What I build is ocean
infrastructure anyone can use."

**[0:25–1:05] The problem.**  "Every sensor watching the ocean is easy
to evade on its own. A vessel that wants to disappear just switches
off its AIS transponder — and to the tools most operators can afford,
it does disappear. Radar satellites pass only a few times a
day. Cameras fail at night. The platforms that fuse everything exist —
but they're closed, expensive, and sold to navies and insurers. A port
authority, a fisheries officer, or a whale-protection NGO can't afford
them and can't audit them. Illegal, unreported and unregulated fishing
runs on exactly that gap."

**[1:05–1:40] What I built.**  "Planetar is open-source, real-time
sensor fusion. Live AIS, free Sentinel-1 satellite radar, coastal
cameras, and hydrophones flow over a low-latency bus into one entity
graph that re-identifies the same vessel across sensors — so going
dark doesn't make you invisible, it makes you a correlated radar,
camera and acoustic track. It's live right now at planetar.ca — you
can click on real Salish Sea traffic today. Twenty-four thousand lines
of open code, nine public repositories, commodity hardware, public
data."

**[1:40–2:05] What's new since I applied.** *(the one thing the panel
hasn't seen)* "Since applying in July, two more layers have landed:
the first version of a maritime entity knowledge graph — vessels
linked to owners, flags, ports and incidents, with provenance on every
fact — and the design for the next step: a learned dark-vessel
detector, benchmarked on xView3, the public dataset built for exactly
this problem — dark fishing vessels in satellite radar."

**[2:05–2:40] The $25K + close.**  "Twenty-five thousand dollars funds
a validation sprint. One: a real benchmark — dark-vessel detection and
re-identification measured on live Salish Sea traffic, published
openly. Two: a packaged deployment a partner can actually run. Three:
one design-partner pilot — a port, fisheries enforcement, or a
conservation group. Those three things turn a working system into a
fundable, sellable one — and this network is where those first
partners are. The ocean is watched by closed systems. Let's open it."

### Beat card (glance copy)

1. **Who** — UVic PhD · ONC acoustics/orca archive · entity-resolution patent · open ocean infra
2. **Problem** — every sensor evadable alone · fusion exists but closed + navy-priced · IUU runs on the gap
3. **Built** — AIS + Sentinel-1 + cameras + hydrophones → one entity graph → dark ≠ invisible · **planetar.ca live** · 24k LOC / 9 repos
4. **New** — entity knowledge graph v1 · learned detector design → **xView3** benchmark
5. **$25K** — benchmark (published) · packaged deploy · 1 design partner → "closed systems — let's open it"

---

## Q&A brief — model answers (30–60 s each; say them aloud)

**1. "How do you make money?"** *(near-certain; the licence changed
after filing — own it)* "Three revenue lines, nearest first: paid
design-partner pilots and deployment/integration contracts; a hosted,
managed instance as a subscription; and support agreements as adoption
grows. One update since my application: I've simplified the licensing
— the platform is now plainly GPLv3, and revenue comes from those paid
services rather than dual licensing. Same revenue lines, simpler and
more trustworthy licence — important for public-interest adopters."

**2. "Who's your first customer? Have you talked to them?"** *(the
honest gap — don't wobble)* "I'll be straight: I'm an
engineer-scientist, and structured customer discovery is exactly what
this program and this funding buy. The $25K's third workstream is a
scoped design-partner pilot. My target list is concrete: a harbour
authority here in Victoria, DFO Conservation & Protection on the
Pacific coast, and marine-conservation groups monitoring protected
areas — plus my Ocean Networks Canada relationships from the research
years." `[FOUNDER: add any real conversations already had — only real
ones.]`

**3. "You're solo. What's the plan / what if you're hit by a bus?"**
"Today, solo is honest — and mitigated: everything is public,
documented, and reproducible; nothing dies with me. The sprint is
deliberately sized for one person.  First hire comes with first
revenue or follow-on funding, on the go-to-market side — that's my
gap, not engineering." `[FOUNDER: confirm the hire-first stance.]`

**4. "Why does open source win here / why won't someone just take
it?"**  "Global Fishing Watch proved the demand for open vessel
transparency — but it's global batch analysis, not a live local
picture. Closed platforms are unaffordable and unauditable for my
buyers. GPLv3 means anyone building on the platform must share
improvements, and I'm the reference implementation and the expertise —
taking the code doesn't take the business. For agencies and NGOs,
auditability is a feature they can't get from the incumbents at any
price."

**5. "What exactly does $25K produce, and by when?"**  "Three
deliverables in roughly six months: a published dark-vessel detection
and re-identification benchmark on live Salish Sea traffic; a
containerized deployment a partner can run on commodity hardware; and
one completed design-partner pilot. Budget: $12K validation, $5K
packaging, $4K pilot, $3K compute and data, $1K contingency."

**6. "How accurate is it? False positives?"** *(don't overclaim)*
"Honestly: the detectors run on real data — the radar pipeline is
validated on a real 433-megapixel Sentinel-1 scene, and the live demo
tracks real traffic — but I haven't yet published quantified
precision/recall on dark vessels. That measured benchmark is
deliberately deliverable number one of the sprint, and I'll publish it
openly whatever the numbers say."

**7. "Incorporation? Haven't you started a company before?"**  "I
applied as an individual, per the challenge rules; on selection I
incorporate a new Canadian company with me as majority owner. I am CEO
of an established Victoria software consultancy — that stays a
separate business; this venture gets a clean cap table."

**8. Relationships / conflicts / 'how do you know the ocean-tech
scene?'** *(standing C2 rule: disclose proactively)* "One relationship
to put on the table: my spouse works at Open Ocean Robotics, here in
the same blue-economy ecosystem. No overlap with Planetar's product,
but I'd rather you hear it from me."

**9. "Are you pursuing other funding?"** *(honest if asked; don't lead
with defence)* "Yes — proposals under evaluation elsewhere, including
federal R&D programs and an ocean tech foundation. This platform is
one open codebase with several applications; the Ocean Startup
Challenge funds the civilian maritime validation — IUU, safety,
conservation — which is the application I'm building first."

**10. "What's your TRL / what's real versus planned?"**  "The platform
substrate — bus, four sensor services on real data, entity graph, live
console — is built and demonstrated: TRL 4, comfortably inside your ≤6
gate. What's *not* built yet, and I'm explicit about this, is the
quantified benchmark and the learned detector — that's the R&D the
sprint and the follow-on fund."

**11. "Why you?"**  "This problem sits at the intersection of ocean
sensing and entity resolution, and I've spent a career in each half:
peer-reviewed machine learning on Ocean Networks Canada hydrophone
data on one side, and industry-scale entity resolution — where I'm a
named inventor on a US patent — on the other. And I've already built
the system: it's live."

**12. "What does success look like in 3 years?"**  "Planetar as the
default open infrastructure for coastal domain awareness — the thing a
port, an enforcement office, or an NGO installs the way they'd install
open-source GIS.  A handful of paying deployments and a hosted service
sustaining a small Canadian team, with the open benchmark as the
credibility engine." `[FOUNDER: adjust ambition to taste.]`

### Traps to avoid

- **Patent phrasing:** always "applicant-named inventor on US Patent 10,936,582"
  (Salesforce-assigned) — never "my patent."
- **Civilian face (D3):** IUU · SAR · conservation · pollution. Don't volunteer defence
  framing; answer honestly if asked (Q9), then return to the civilian application.
- **Don't overclaim:** no accuracy numbers exist yet (Q6); "validated" means the
  433-Mpx scene and live operation, not a published benchmark.
- **Licence consistency:** the filed answers say AGPL/dual-licence; the current model is
  GPLv3 + services. Use the Q1 "I've simplified" line — never pretend the filed text
  said otherwise.
- **3 minutes means 3 minutes:** rehearsed target ≤2:45.
