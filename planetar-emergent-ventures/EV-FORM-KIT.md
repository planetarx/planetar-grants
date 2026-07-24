# Emergent Ventures — form kit (matched to the LIVE form, 2026-07-23)

> Form: https://mercatus.tfaforms.net/5099527 · **rolling; one page; incomplete apps auto-rejected.**
> Verified live 2026-07-23. Voice: first-person, direct, zero grant-speak. `[FOUNDER]` = only you.
> Claims are auditable — keep exact. Paste top-to-bottom.

## Discrete fields

- **Affected Region** (required dropdown): `[FOUNDER]` — the demo is North America (Salish Sea); the
  problem (IUU fishing / dark vessels) is global. Pick **North America** or the best global option.
- **Project Topic** (optional dropdown): `[FOUNDER]` — closest fit; "does not affect review priority."
- **First Name:** Steven · **Initial:** R · **Last Name:** Ness · **Suffix:** —
- **Email:** sness@sness.net · **Email Type:** Personal
- **Phone (incl. country code):** `[FOUNDER]` · **Phone Type:** `[FOUNDER]`
- **Twitter (optional):** `[FOUNDER]` (leave blank if none)
- **Country:** Canada · **State/Province:** British Columbia · **City:** Victoria
- **Multimedia URL:** https://planetar.ca
- **Uploads:** none needed (EV reads the proposal first; **no PDFs accepted** anyway — the deck/budget
  PDFs don't fit its allowed types, and aren't required). The proposal + planetar.ca stand on their own.
- **Checkboxes:** 13+ ✓ · charitable/scientific/educational-use, no lobbying ✓ · consent ✓ · reCAPTCHA.

## "How do you describe your idea in a tweet?" (required, ≤295 chars)

Ships that want to vanish just switch off their AIS transponder — that alone defeats most ocean monitoring on Earth. I'm building planetar: open-source, real-time sensor fusion that re-identifies dark vessels across radar, camera and acoustics. Live now at planetar.ca, built solo.

## "Tell us about your proposal" (required, ≤1500 words)

**Follows EV's prescribed structure: about you → a consensus view you hold → the idea.**

I'm Steven Ness, in Victoria, British Columbia. My whole career has been teaching machines to recognize the same thing across messy, noisy real-world signals. My PhD work built a system for a 20,000-hour, 30-year archive of orca recordings from Ocean Networks Canada's undersea hydrophones — finding and classifying whale calls in continuous ocean audio, with a human kept in the loop to correct the machine. I published on hydrophone event-detection on that operational data (IEEE PacRim 2011) and on large-scale killer-whale call identification (Interspeech 2021). Then I spent years doing entity resolution at industry scale — linking records that describe the same real-world entity across systems that never agree — and I'm an applicant-named inventor on US Patent 10,936,582 for that architecture (one of nineteen inventors). The through-line is a single problem I keep returning to: recognizing one identity across sensors and sources that each see only a fragment. And a conviction that the infrastructure for it should be open, not locked inside a defense contractor or a proprietary platform.

One mainstream view I hold without reservation — and I mention it because the temptation in an application like this is to sound clever and contrarian — is that the scientific consensus on climate change is correct, and that ocean health is not a soft concern but a hard, measurable, civilizational one. It's why I care about who is actually on the water. You cannot protect, regulate, or even understand an ocean you cannot see, and right now most of what happens at sea happens unobserved. I don't think there's anything brave about saying this. I just believe it plainly, and it's the reason this project is about the ocean and not something more lucrative. *(Founder: confirm this is genuinely your view, or swap it for your own — this answer must be sincerely yours.)*

The idea. A ship that wants to disappear simply switches off its AIS transponder — the beacon that's supposed to announce its identity and position. That one gesture defeats most maritime monitoring on Earth, and it's how illegal fishing fleets, sanctions evaders, and smugglers operate in plain sight. The sensors that could still see a dark vessel exist — satellite radar, coastal cameras, hydrophones — but the systems that fuse those feeds into one picture are closed, priced for navies, and impossible to audit.

I'm building the open-source alternative, alone. planetar is live today at planetar.ca: a real-time fusion platform with its own message bus (a single-file C broker I wrote, benchmarked at nanosecond-median latency — measured, not estimated), a typed envelope that carries provenance on every message, and working ingest pipelines for AIS, Sentinel-1 satellite radar, coastal cameras, and hydrophone acoustics, fused into an entity graph and a live analyst interface, running over two real operating areas. All of it is public and open source. You can go click on it.

The moonshot is the next step, and it's what this grant funds. Here is the insight: while a vessel is still broadcasting AIS, its radar signature, visual appearance, and acoustic signature all co-occur with a known identity. That means the ocean is continuously generating free, labeled training data — every cooperative ship is quietly teaching the system what its own non-cooperative signatures look like. I want to train a self-supervised cross-modal re-identification model on that co-occurrence, so that when a vessel goes dark, the system can match its radar, camera, or acoustic signature back to the identity it learned — tracking the same physical hull across sensors with no transponder at all. This is the direct descendant of my orca work: re-identifying an individual from the signal it can't help emitting. Nobody offers this openly. The closed equivalents are classified or cost millions.

The grant buys the two things a solo founder can't bootstrap: GPU compute to train the model, and a few months of focused runway to ship it into the live system and publish an honest evaluation — including where it fails. The result is public-good infrastructure: any coastal state, fisheries agency, or conservation group gets an auditable dark-vessel monitoring stack they can run themselves, and the same architecture serves search-and-rescue and naval domain awareness. It is deliberately dual-use and deliberately open. That combination — genuinely open infrastructure for a problem usually kept classified — is the unusual bet here.

Two honest notes. I work on this essentially full-time and have built the entire existing stack myself — the bus, the envelope, four sensor pipelines, the entity-resolution graph, and the UI. And a Government of Canada defence-R&D proposal on this same fusion research is currently under evaluation; this grant is independent of it, and its purpose is to keep the open-source core moving regardless of how that decision goes. The government path, if it comes, funds a controlled deliverable. Emergent Ventures would fund the open one — the version anyone can run.

## Estimated Budget (optional short text)

US$50,000 (flexible)

## Breakdown of Expenses (optional textarea)

- Founder runway — a few focused months to ship the cross-modal re-ID model into the live system and publish an honest evaluation: US$25,000
- GPU training compute for the self-supervised re-identification model: US$15,000
- Satellite data access + hosting for the live planetar.ca demonstrator: US$10,000

Ballpark, as requested — profit/self-sufficiency is the eventual goal; this grant de-risks the open-source research phase.
