# Stage-3 Pitch — 10-min presentation + 20-min Q&A

> DIANA's final stage is a **30-minute online panel: a 10-minute presentation/pitch + 20 minutes
> Q&A** (Stage-2/3 panels add DIANA's trusted-investor network). This is the plan + the Q&A prep.
> Everything here must match [../THESIS.md](../THESIS.md) and stay inside the guardrails (conservative
> benchmark, "applicant-named inventor", honest TRL). The hook is the **demonstrated cross-sensor
> re-ID** ([DEMO.md](../DEMO.md)) — lead with the thing that's real.

## The one sentence (open and close on this)

> *"planetar is an open, provenance-native engine that fuses multi-domain sensors and
> re-identifies the same vessel across them — including ones that go dark — and it already runs."*

## 10-minute deck — slide-by-slide (≈1 min each)

| # | Slide | Time | The beat (what you say) | Visual |
|---|---|---|---|---|
| 1 | **Title / hook** | 0:45 | "A vessel that wants to vanish just switches off AIS. Dark vessels drive illegal fishing, smuggling, sanctions evasion. Seeing them means fusing many sensors in real time — and today's tools that can are closed, single-vendor, and opaque." | Title + dark-vessel image; applicant: Zax Analytics (Steven Ness) |
| 2 | **The challenge fit** | 0:45 | "DIANA's ISR challenge asks for sensor fusion across platforms, formats and classifications, with causality-based, predictive intelligence. That's a spec for what we've built." | The challenge text ↔ planetar mapping (4 ticks) |
| 3 | **What planetar is** | 1:00 | The 5 layers in one breath: envelope → ns bus → detectors → entity graph → analyst shell. "Open backbone, not a silo." | The pipeline diagram (from the quad chart) |
| 4 | **DEMO — the dark-vessel re-ID** | **2:00** | *The centerpiece.* "Watch one vessel go dark, get re-acquired by satellite SAR, then by an EO camera — the entity graph fuses them into one auditable track." Narrate the gap (40 min), the score, the field-level provenance. | **Recorded screencast** (GraphTab re-ID card + map overlay) or the live `demo-reid` + API output |
| 5 | **Why it's novel** | 1:00 | "Provenance-native fusion: every conclusion is explainable to its source observations — that's the 'causality-based' the challenge wants. And it's open, so any ally's sensor can join without a vendor gate." | Auditable-lineage graphic; "open vs. closed C2" contrast |
| 6 | **It's real, and measured** | 1:00 | "Not slideware: a benchmarked nanosecond bus (p50 80–140 ns measured), four detectors on live/real data, 30-test entity graph, and the re-ID you just saw — all open-source, auditable." | Evidence row (repos + benchmark + patent) |
| 7 | **Maturity — honest TRL** | 0:45 | "Substrate at TRL 4, several parts at TRL 5 on live feeds, cross-sensor re-ID demonstrated. DIANA takes it to 5/6." | TRL ladder with the "you are here" mark |
| 8 | **Dual-use & NATO impact** | 1:00 | "Same code: civilian SAR/fisheries/pollution today, maritime domain awareness & contested ISR for the Alliance. An open fusion backbone = allied interoperability without lock-in; generalizes beyond maritime." | Dual-use split; "one codebase, two faces" |
| 9 | **Team** | 0:30 | "Steven Ness, PhD — named inventor on US Patent 10,936,582 for entity resolution; published bioacoustic ML on Ocean Networks Canada data; author of the whole stack." | Headshot + 3 credibility chips |
| 10 | **The ask + plan** | 1:00 | "DIANA's €100K + test-centre access to harden for contested, multi-classification ISR and validate in a NATO-relevant environment — TRL 4→5/6. Concretely: multi-classification routing, learned association, a NATO test-centre validation." | In-program milestones (4 bullets) |
| 11 | **Close** | 0:15 | Repeat the one sentence. "It already runs. Help us harden it for the Alliance." | The one sentence, full screen |

**Total ≈ 10:00.** If you must cut, compress slides 5 and 8; **never cut the demo (4)** — it's the differentiator and the only thing most applicants can't show.

## The demo (slide 4) — how to deliver it

- **Best:** a 60–90 s **recorded screencast** of the shell — the GraphTab card showing the
  "Re-identified · 2 cross-sensor matches" (SAR then EO) and the map's red/blue fused-entity overlay.
  Record it once the local `vite`/rolldown install is fixed (`rm -rf node_modules package-lock.json && npm i`).
- **Fallback (works today):** run `node tools/demo-reid.ts` live and `curl` the entity + its
  `reacquisition` links — the terminal output *is* a credible, honest demo of the fused re-ID.
- Either way: **narrate the story, not the UI** — dark → SAR re-acquire → EO re-acquire → one
  auditable entity. Keep it under 2 minutes.

## Q&A prep (the 20 minutes) — likely questions, honest answers

| Lens | Question | Answer (tight, honest) |
|---|---|---|
| TRL | "You claim TRL 4 but your IDEaS bid says TRL 1–3 — which is it?" | "Different scopes. The *platform substrate* — bus, envelope, detectors, entity resolution — is integrated and lab-validated at TRL 4, with the cross-sensor re-ID demonstrated. The IDEaS 1–3 framing scopes *new R&D layered on top*. Both are true." |
| Feasibility | "You're a solo founder — can you deliver?" | "The hard parts are already built and demonstrated; the in-program work is bounded engineering + validation, not invention. ~12k LOC, low dependencies, proven end-to-end. DIANA's mentors/test-centres are exactly the leverage a focused founder needs — and I'd bring in collaborators for the accelerator." |
| Technical | "How is this different from existing C2 / fusion suites?" | "Two things together no incumbent offers: auditable, provenance-native fusion (every conclusion traces to source observations) and an *open* backbone any ally's sensor can join without a vendor gate." |
| Security | "ISR data is classified — how do you handle multi-level?" | "The envelope already carries per-message provenance and routing metadata; classification-aware routing / multi-level partitioning is a primary in-program deliverable. We'd validate it in a NATO-relevant environment with DIANA." |
| Defence | "Is this really defence-relevant, or a maritime-safety tool?" | "Same backbone, both faces. Dark-vessel re-ID *is* the grey-zone maritime problem — sanctions evasion, smuggling. And the substrate generalizes: land/air/space sensors emit the same envelopes." |
| Commercial | "It's open-source — how do you make money / sustain it?" | "Open-core: permissive bus + envelope for adoption; AGPL platform with commercial licenses; integration/support services. Open *drives* the NATO interoperability value — adoption is the moat, dual-licensing + services are the revenue." |
| Validity | "Your benchmark — is it measured or aspirational?" | "Measured: p50 80–140 ns / p99 400–900 ns shared-memory, 1M-message benchmark; report is in the repo. We don't quote un-measured post-tuning numbers." |
| IP | "Tell us about the patent." | "I'm a *named inventor* on US Patent 10,936,582 for entity resolution across distributed systems (Salesforce-assigned, one of 19 inventors) — it grounds the re-ID approach. I don't claim ownership of the patent." |
| Risk | "Biggest risk to delivery?" | "Bandwidth and scope discipline. Mitigation: the spine is built and demonstrated, milestones are bounded, and the accelerator structure + test-centre access de-risk the validation step specifically." |
| Adoption | "Who's your first NATO user?" | "Civilian maritime users (e.g. ONC/research, fisheries) give referenceable traction now; DIANA's end-user network is the bridge to an allied operational pilot — that's a reason we want *this* program, not just funding." |
| Team | "Why should we back you over a bigger team?" | "Depth where it counts: I authored the entire stack and hold relevant entity-resolution IP and a decade of multi-sensor ML on real ocean data. DIANA adds the network and validation environment a solo deep-tech founder can't self-provision." |

## Delivery notes

- **Lead with the demo's outcome, not the tech tour.** Most panels have seen architecture diagrams;
  few see a working cross-sensor re-ID.
- **Stay honest on TRL and the benchmark** — the panel includes technical evaluators; the verifiable
  spine is your credibility, don't inflate it.
- **Name the open-source posture as a *NATO advantage*** (interoperability, no lock-in), not a
  giveaway.
- Have the `[TODO]` traction facts (repo stars, ONC/research conversations) ready as backup slides.
- Keep a one-line answer to "what do you need from DIANA?" — *test-centre validation + end-user
  access for the contested/multi-classification step*, money second.

---

# Backup / appendix slides

> Not shown in the 10-min run — held in reserve to pull up during Q&A. Verified facts are filled in;
> **`[TODO: …]` = a founder-only number to drop in.** Keep the guardrails (conservative benchmark,
> "named inventor", honest TRL). Order roughly by how likely you'll need them.

## B1 — Traction *(pull up on "who cares / any users?")*

The "proof of demand" slide. Fill the numbers; the structure is set.

- **Open source, public:** 8 repos, ~12k LOC (auditable), gitleaks-clean; permissive bus + envelope,
  AGPL platform. `[TODO: confirm public release date — one-pager says 2026-05-15; GitHub initial
  commits show 2026-06-10. Use the right one.]`
- **Repo signal:** `[TODO: GitHub stars / forks / contributors / commit cadence — aggregate or per key repo]`
- **Community/funding rails:** `[TODO: GitHub Sponsors + Open Collective backers / monthly, if live]`
- **Reach:** `[TODO: website visitors · demo-video views · any inbound]`
- **Pipeline / partners:** `[TODO: ONC / fisheries / research conversations — name + stage (intro,
  data-access talk, LOI). Letters of support if any.]`
- **Recognition:** `[TODO: any press, awards, talks]`
- *If traction is thin, say so honestly and lead with the demonstrated capability + the patent/IP
  spine — for a TRL-4 deep-tech bid, working code beats vanity metrics.*

## B2 — Architecture deep-dive *(pull up on "how does it actually work?")*

The 5 layers, with the detail behind the one-line tour:
1. **Envelope (`zmesg`)** — compact self-describing format: UUIDv7 ids, ns timestamps, topic,
   correlation/causation ids; zero-copy parse. *The provenance unit.*
2. **Bus (`planetar-broker`)** — ~1.4k LOC C11; SHM + TCP + UDP at once; write-ahead log w/ CRC.
   Measured **p50 80–140 ns / p99 400–900 ns** SHM (1M-message benchmark).
3. **Detectors** — AIS (`planetar-ais`), SAR (`planetar-sat`, real Sentinel-1 + CFAR), EO
   (`planetar-eo`, YOLO on live cams), acoustic (`planetar-acoustic`, cochlear model on live
   hydrophone). Each emits typed `zmesg` envelopes.
4. **Entity graph (`planetar-ontology`)** — resolves observations → canonical entities (identifier
   match + confidence-scored merge), field-level provenance, kinematic dark-vessel re-ID; Object API
   (REST + WS). 30 tests.
5. **Shell (`planetar-ui`)** — React analyst UI; live map + per-vessel channels + the entity-graph /
   re-ID views over a WS bridge.

## B3 — Verifiable spine *(pull up on "how do we trust these claims?")*

Every headline claim → an auditable source (this is the credibility play):

| Claim | Source |
|---|---|
| ns bus | `planetar-broker` + `planetar/docs/benchmark-2026-04-27.md` |
| 4 live/real detectors | `planetar-ais` · `planetar-sat` · `planetar-eo` · `planetar-acoustic` |
| Cross-sensor re-ID (demonstrated) | `planetar-ontology/tools/demo-reid.ts`; verified 2026-06 (`DEMO.md`) |
| Entity-resolution IP | US Patent 10,936,582 (applicant *named inventor*) |
| Track record | ONC/NEPTUNE bioacoustics (Sattar et al., IEEE PacRim 2011); ORCA-SLANG (Interspeech 2021) |

## B4 — The re-ID demo, in detail *(pull up if they want to dig into slide 4)*

The exact verified scenario (`DEMO.md`):
- Vessel `MV Shadow Runner` sends a last AIS fix, then goes dark.
- **SAR** (`planetar-sat`) re-acquires it 40 min later — no MMSI, matched by dead-reckoned kinematics
  (score 0.9).
- **EO** (`planetar-eo`) re-acquires it again 20 min after that (score 0.9).
- Result: one fused entity, `status: reacquired`, **field-level provenance fused** — mmsi/name/cog/sog
  from AIS, lat/lon/status from EO — and two auditable `reacquisition` links. The live AIS fleet was
  correctly excluded.

## B5 — In-program roadmap (TRL 4 → 5/6) *(pull up on "what exactly would you do?")*

Six-month accelerator (cohort starts Jan 2027). `[TODO: confirm phase durations against the portal's
programme calendar.]`
1. **Multi-classification routing** — classification-aware partitioning / multi-level handling.
2. **Learned multi-sensor association** + probabilistic track prediction (beyond the kinematic rule).
3. **New platform adapters** — autonomous/UAS, RF.
4. **NATO-relevant-environment validation** at a DIANA test centre — degraded comms, adversarial
   conditions; capture metrics. `[TODO: name a target test-centre / end-user if you have one.]`

## B6 — Team & collaborators *(pull up on "who's behind this?")*

- **Steven Ness, PhD** (Computer Science, UVic 2013), Director & CEO, Zax Analytics — author of the
  full stack; named inventor on US Patent 10,936,582; published ONC/NEPTUNE bioacoustic ML; h-index
  15, ~1,300 citations. `[TODO: confirm h-index/citation figures are current.]`
- `[TODO: collaborators / advisors / contractors you'd bring in for the accelerator — even named
  intent helps answer the "solo founder" question.]`

## B7 — Why us vs. alternatives *(pull up on "competition?")*

- **vs. closed C2 / fusion suites (Palantir-style):** open backbone (no vendor lock-in) +
  provenance-native, auditable fusion. Allies can join sensors/analytics freely.
- **vs. point-solution fusion startups:** we span four sensor domains *and* the bus + entity graph,
  with a demonstrated cross-sensor re-ID and a benchmarked substrate — not a single-sensor tool.
- **The moat:** open adoption + the provenance/IP spine; revenue via dual-licensing + services.
- `[TODO: name 1–2 specific comparators if you want to make it concrete.]`

## B8 — Use of funds *(pull up on "what would the money do?")*

€100K accelerator (top performers: up to €300K Mission Track). Indicative split — `[TODO: tune the
percentages to your real plan]`:
- `[TODO: ~%]` engineering (multi-classification routing + learned association)
- `[TODO: ~%]` test-centre validation + travel
- `[TODO: ~%]` new platform adapters
- `[TODO: ~%]` founder/contractor time
- *Open-source means no licensing/vendor costs — funds go to capability + validation, not seats.*

## B9 — Dual-use markets & adoption *(pull up on "who buys this?")*

- **Civilian:** maritime SAR, fisheries enforcement, pollution / whale-strike monitoring — same code,
  referenceable now. `[TODO: market-size figures if you want them.]`
- **Defence:** maritime domain awareness, contested multi-classification ISR (the DIANA face).
- **Adoption path:** civilian traction → DIANA end-user network → allied operational pilot.
