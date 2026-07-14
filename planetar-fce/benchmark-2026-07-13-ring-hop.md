# planetar-broker ring-hop benchmark — 2026-07-13 (closes Q7)

**Purpose:** make the CH14 narratives' latency claim literally true on planetar-broker itself
(Q7, `08-OPEN-QUESTIONS.md`). Until this run, the headline p50 80–140 ns / p99 400–900 ns was the
predecessor `zbroker0`'s measurement (`../../planetar/docs/benchmark-2026-04-27.md`).

## Result — headline bracket (four clean runs)

> **p50 95–100 ns · p99 1.0–1.6 µs** (per-message latency, writer store → reader dequeue,
> 1M messages/run, 64 B payload)

p50 falls inside the old zbroker0 bracket (80–140 ns) — confirmed. p99 is consistently **above**
the old 400–900 ns bracket → per §Q7 branch (b), the headline was updated to the measured bracket
in MC-1, PRC-1, PRC-2, PRC-4, PRC-6, and `submission/09-mc1-rd-activities.md`, which now cite
planetar-broker directly (predecessor framing dropped). Rounding is conservative: bracket low end
rounded down (1,055 → 1.0 µs), high end rounded up (1,519 → 1.6 µs).

## Environment

- **Machine:** the i9-9900K workstation (`bb`) — Intel Core i9-9900K @ 3.60 GHz, 16 threads;
  same box class as the 2026-04-27 zbroker0 measurement.
- **Kernel:** Linux 6.17.0-35-generic. **Not quiesced:** pm2 planetar tier (broker/ui/bridge/
  ontology/ais) running throughout; load average ≈ 3.3–4.7. Untuned, no isolcpus, no RT priority.
- **Harness:** `planetar-broker/tests/ring-hop.c` — direct SHM ring hop (writer → ring → reader,
  **no broker process in path**), byte-for-byte the broker's `ring_header_t`/`ring_entry_hdr_t`
  contract; CPU-pinned writer cpu2 → reader cpu4; reports ns percentiles. Per its header and the
  perf script's warning, this is deliberately **not** `make perf` (TCP/UDP broker path, µs scale) —
  the two must not be conflated.

## Commands

```
cd ~/github/planetarx/planetar-broker
make tests/ring-hop        # was already built
./tests/ring-hop 1000000   # repeated 4×, sequential, ~2 s apart, no concurrent workload
```

## Clean runs (the headline bracket)

| Run | Min | Avg | p50 | p90 | p99 | Max |
|---|---|---|---|---|---|---|
| 1 | 51 | 123 | 96 | 135 | 1,058 | 43,733 |
| 2 | 50 | 123 | 95 | 134 | 1,083 | 22,138 |
| 3 | 49 | 123 | 95 | 134 | 1,055 | 11,857 |
| 4 | 54 | 143 | 100 | 135 | 1,519 | 60,314 |

All values ns. Rate 1M msg/s (1 µs send gap).

## Discarded runs (recorded for honesty)

An earlier batch of four runs is **not** used for the bracket: runs 2–4 of that batch executed
while a recursive `grep` workload from the working session ran concurrently on the same box,
inflating tail percentiles (p99 up to 747 µs; p50 unaffected at 96–99 ns). Run 1 of that batch
(no concurrent workload: p50 98 / p99 1,044 ns) is consistent with the clean runs. Across all
8 runs, p50 ∈ [95, 100] ns.

## Interpretation for the bid

- The **median** hop is ~100 ns — the "nanosecond-scale chokepoint" claim holds on
  planetar-broker's own ring.
- The **p99 ≈ 1.0–1.6 µs** tail on a busy, untuned multi-service workstation still sits ~3 orders
  of magnitude below any tactical-decision threshold; the CH14 "no added tactical latency"
  argument is unchanged.
- The FCE's real 1a deliverable remains the **marginal FCE-on overhead** vs this baseline —
  distinct measurement, don't conflate (per §Q7 framing note).
