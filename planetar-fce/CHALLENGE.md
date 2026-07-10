# Reliable AI sensor fusion for real-world missions — research note

> **Source:** canada.ca IDEaS Competitive Projects challenge pages, retrieved by the
> user 2026-06-22 (full text pasted into the session and reproduced below verbatim).
> Announced via IDEaS email forward 2026-06-05 (D. Huang → applicant). Two sibling
> challenges were announced together; **this folder is for Challenge 1 (sensor fusion /
> the Fusion Compliance Engine)**. Challenge 2 (urban data) is summarized at the bottom —
> if pursued it gets its own folder per workspace convention.
>
> **Authoritative criteria/deadline live in the CanadaBuys Solicitation Guide + the DIP
> portal**, not on the canada.ca challenge page (same as `../planetar-true-north`). The
> Guide was **not yet retrieved** — solicitation number, exact evaluation point-weights,
> mandatory criteria (MC-1/MC-2), and the formal deadline still need portal confirmation.
> See "Unconfirmed" at the bottom.

---

## Key facts (public record, 2026-06-22)

| | |
|---|---|
| Program | IDEaS **Competitive Projects** (DND/CAF) |
| Challenge | *Reliable AI sensor fusion for real-world missions* — build a **Fusion Compliance Engine (FCE)** |
| Sibling challenge | *Turning urban data into real-time insight through AI* (same funding ladder; see bottom) |
| CFP opened | **2026-06-04** (Ch1 page "date modified"; Ch2 modified 2026-06-10) |
| **Proposal deadline** | **2026-07-14, 14:00 EDT** (confirmed on CanadaBuys notice) |
| Funding ladder (phased, by TRL) | **1a** TRL 1–3 ≤**$250K** ≤6 mo · **1b** TRL 4–5 ≤**$1.5M** ≤12 mo · **2** TRL 6–9 ≤**$5M**. Up to **$6.75M total** if a solution advances all stages. |
| Eligibility | individuals, startups, not-for-profits, SMEs, academia, other non-traditional innovators; "all stages of development" |
| Data provided by DND/CAF | **None** — innovators must obtain/generate their own datasets |
| Solicitation number | **`W7714-248676/014`** — this is **CFP6 Challenge 14 (CH14)**, same CFP6 umbrella as our CH13 (`/013`) and True North (`/012`) |
| CanadaBuys notice | https://canadabuys.canada.ca/en/tender-opportunities/tender-notice/cb-0-11990877 (published 2026-06-04) |
| Portal | https://defence-innovation-portal.my.site.com/ · Contracting: paidees.apideas@tpsgc-pwgsc.gc.ca |

### The "Guide" — where the scored criteria actually live

Two PDFs attached to the CanadaBuys notice above (both **public**, no DIP login):

1. **Challenge-specific (CH14)** — authoritative for *this* challenge's outcomes + criteria + which Components are open. Bilingual EN/FR:
   `https://canadabuys.canada.ca/sites/default/files/webform/tender_notice/96363/cfp6-ch14-reliable-ai-sensor-fusion---ap-6-defi-14--fusion-de-capteurs-par-lia-fiable.pdf`
2. **Umbrella Solicitation Guide** — *"W7714-248676 IDEaS CFP 006 – Amendment 2"* — CFP-wide submission/evaluation/scoring/certifications. **Same doc used for CH13 (`/013`)** — already in hand:
   `https://canadabuys.canada.ca/sites/default/files/webform/tender_notice/96363/w7714-248676-ideas-cfp-006---amendment-2.pdf`

**Relationship to what we just submitted:** this is the *same Competitive Projects element*
as CH13 ("Multi-modal AI for advanced situational decisions," `CP6-132484`, filed
2026-06-01). CH13 was effectively the 1a (TRL 1–3 / $250K) rung of a fusion challenge;
this is a sibling challenge with the **full ladder open** and a **compliance/provenance**
thesis instead of a learned-fusion thesis.

---

## The challenge (verbatim essentials)

> "DND/CAF are seeking innovative AI solutions that **embed compliance-by-design into
> multi-sensor, multi-domain fusion workflows**. The goal is to develop a **modular Fusion
> Compliance Engine (FCE)** that automatically enforces classification rules, legal
> constraints, and policy adherence in real time during data aggregation and analysis."

The FCE is **a policy-aware gatekeeper that sits between raw sensor ingestion and the
fusion analytics pipeline** — tagging, filtering, and routing data by classification
markings and release authorities, **without adding latency that degrades tactical
decision-making**. Today this is done by manual review / checklists that can't keep pace.

**Framing hooks (verbatim):** supports the CAF Digital Campaign Plan, the DND/CAF AI
Strategy, **NORAD modernization**, the Cyber Forces mandate. "Canada currently lacks a
**sovereign, Canadian-developed and Canadian-controlled** compliance engine for
multi-domain fusion." A successful FCE is "a reusable building block for every future
fusion system — from **Arctic surveillance** to coalition interoperability hubs."

**Sensors named:** UAS, distributed acoustic sensors, SIGINT receivers, EO/IR platforms,
radar.

**Application examples (verbatim, "not limited to"):**
1. **Joint ISR Fusion** — automated classification enforcement when combining SIGINT,
   EO/IR imagery, and radar tracks; FCE tags every element with provenance metadata,
   blocks unauthorized cross-domain merges, generates an audit trail.
2. **Maritime Domain Awareness** — compliance checks during multi-sensor anomaly
   detection. ← *planetar's home turf, called out by name.*
3. **Tactical Edge / Dismounted** — modular compliance layer on a ruggedized laptop /
   edge server enforcing classification separation for wearable sensor networks in
   denied/austere environments.

### Essential outcomes (MUST — pass/fail)

Proposed solutions **must**:

1. Develop a **modular AI-enabled component** that automatically enforces classification
   rules and policy constraints **during multi-sensor (≥2) data fusion**.
2. Apply enforcement controls from **machine-readable policy definitions** across:
   multiple sensor modalities (≥2); security domains (at least **Network security**);
   classification levels (at least **Protected B**).
3. Execute compliance checks **programmatically during ingestion and fusion**, **without
   human approval** for predefined policy conditions.
4. Generate + retain **provenance records** for all data in/out of the pipeline: source
   sensor ID, classification markings, timestamps, domain of origin.
5. Produce **audit logs**: policy rules applied, enforcement actions taken (**permit /
   restrict / downgrade / segregate**), resulting compliance dispositions.
6. Produce **audit records supporting data-lineage traceability** from ingestion through
   fusion output, **exportable** for compliance review / forensic analysis / accreditation.

### Desired outcomes (SHOULD — scored differentiators)

- **Real-time** compliance enforcement across ≥2 modalities and classification levels, at
  tactical-decision speed.
- **Adaptable policy framework** — rules (classification guides, release authorities,
  coalition caveats) updatable/reconfigurable **without system restart**.
- **SWaP / compute limits** incorporated for **edge deployment** while maintaining
  enforcement.
- **Explainability + operator trust** — human-readable compliance decisions, controlled
  **override** with accountability safeguards.

---

## Sibling: "Turning urban data into real-time insight through AI" (Challenge 2)

> Repurpose **existing urban infrastructure** (cameras, acoustic arrays, air-quality &
> vibration sensors, wireless APs) as a **distributed passive sensing network** for
> real-time situational awareness + anomaly detection — an **AI middleware layer** on top
> of existing feeds, **no new hardware**. Supports the CAF Digital Campaign Plan, SSE urban
> defence priorities; examples: **Urban Counter-UAS** (fuse traffic-cam video + acoustic +
> passive RF to detect/track unauthorized drones), Critical-Infrastructure anomaly mesh,
> environmental early warning.

**Essential outcomes (must):** AI module(s) ingesting ≥2 heterogeneous sources;
**real-time** anomaly/threat-indicator analysis; **machine-readable outputs** (alerts /
scores / flags) for operator review; **legal/privacy/data-protection compliance** for
civilian-derived data (offeror determines applicability).

**Desired:** rapid edge deployability; adaptive ingestion via **standard protocols** with
graceful source-degradation; **explainable** outputs (what, which sources, confidence);
scalable architecture compatible with international standards.

Same funding ladder, same deadline. Fit verdict for both challenges → [`FIT.md`](FIT.md).

---

## Unconfirmed at note time (resolve before committing)

Resolved 2026-06-22: ~~solicitation number~~ → **`W7714-248676/014` (CH14)**; ~~deadline~~ →
**2026-07-14 14:00 EDT confirmed**; ~~where the Guide is~~ → two CanadaBuys PDFs (above).

**Resolved by reading the CH14 challenge PDF** (`CH14-challenge.pdf` / `.txt`, retrieved
2026-06-22): the per-challenge PDF is **only** the Challenge Statement + Essential/Desired
Outcomes (3 pp EN, then FR) — verbatim-matching the canada.ca text reproduced above. It
contains **no** Components, Mandatory Criteria, point-weights, or character caps.

→ **Those are CFP-wide and identical to CH13** (same CFP6, same *Amendment 2* doc we used
for `/013`): MC-1/MC-2 (pass/fail), **PRC-1 (10) · PRC-2 (20) · PRC-3 (20) · PRC-4 (20) ·
PRC-5 GBA+ (5) · PRC-6 (15) · PRC-7 budget**, 70-pt threshold, **3,000-char** scored-narrative
caps, and the **1a/1b/2** Component ladder (applicant self-selects by honest TRL → **1a** for
us). So there is **no new evaluation machinery to learn** — CH14 reuses CH13's entirely.

Still open (verify in the in-hand Amendment 2, not challenge-specific):

1. **Multiple-bid rules** — may we submit to both CH14 and the urban sibling (CH15?)? Bandwidth
   aside.
2. **Any CFP6 Amendment newer than 2** for this challenge — the notice attaches Amendment 2
   (same as CH13); confirm no later amendment changes caps/criteria.

## Sources

- [Canada.ca — Reliable AI sensor fusion for real-world missions](https://www.canada.ca/en/department-national-defence/programs/defence-ideas/element/competitive-projects/challenges/reliable-ai-sensor-fusion-for-real-world-missions.html)
- [Canada.ca — Turning urban data into real-time insight through AI](https://www.canada.ca/en/department-national-defence/programs/defence-ideas/element/competitive-projects/challenges/turning-urban-data-into-real-time-insight-through-ai.html)
- [SpaceQ — DND issues $6.75M IDEaS challenge for multi-modal AI](https://spaceq.ca/dnd-issues-6-75m-ideas-challenge-for-multi-modal-ai-to-fuse-space-and-terrestrial-data/) *(note: states a "June 2" deadline — appears to conflate with the old CH13 date; trust the canada.ca/email July 14)*
- IDEaS email forward, 2026-06-05 (D. Huang)
