> **Experimental. We are just trying this.** [Disclaimer](../DISCLAIMER.md) · Kaspa Testnet-10 only; tKAS has no value.
>
> Our own testing. What we observed in this run, on our own nodes. Not a claim about how TN10 or Kaspa behave in general. No key, seed, txid, covenant id, address, host or port.

# Lessons, pre-run 20

Written after the run, 2026-11-13, from the files on origin and the desk's own logs (read-only). Times are UTC unless marked Brussels.

## Short version

- **Pre-run 20 ran through RETURN.** Every step file is on origin for the desk and for Mini, then TIMELINE, MEMPOOL and METHOD; every whole minute was clean; no repair, no restart. All 11,474 lane transactions landed (0 rejected, 0 lost) and every OK family hop landed (floor 5,975, r150 6,795, r300 7,870, r450 8,175). No lane cap was met, so `FROZEN`, the cap guard and the budget hold were not exercised.
- **Probe 1, greedy at 100 percent of its reference: it ratcheted.** 150 → 188 → 235 → (hold at 105 percent) → 294 → 368 → (hold at 101 percent), 4 steps up in 6 decided minutes, never down, and it ended at 368 when the segment ended. Its landings stayed flat (502–543 a minute against a reference of 519). A reachable target did not make the never-down rule settle: noise alone put about half the minutes under 100 percent.
- **Probe 1, the normal rule on the same lane: it settled.** Reset to 150: 150 → 150 → 120 → 120 → 100 → 100, at the floor within 4 minutes, landings unchanged (478–523).
- **Probe 2, fewer chains ready at the same high rate: the template stayed full.** At a fixed 460, N = 8 chains: the desk node's own block template (read every 3 s, never submitted) held a median of 471,954 mass with almost always one of our heavy transactions in it and about 205,000 mass of other transactions, as at 150. N = 30 at the same 460: 348,296 mass, 5 transactions, and only about 82,000 mass beside our heavy one. So the shrink pre-run 19 saw comes with many of our heavy transactions ready at a high rate, not with the rate alone (likely, not proven: N = 8 also landed fewer, 229 a minute against 525).
- **Bystanders followed the ready count more than the rate.** Percent of BASE (floor 100 / r150 / r300 / r450): N = 30 at 150 68 / 86 / 97 / 99; greedy at 235–368 28 / 51 / 85 / 95; normal rule settled at 100–120 82 / 92 / 99 / 101; N = 8 at 460 92 / 94 / 96 / 100; N = 30 at 460 10 / 25 / 69 / 89; HOLD-4 and RETURN 103 / 105 / 102 / 101.
- Our lane slowed other TN10 users' transactions while it ran, most at N = 30 and 460 (below).

## The questions

Pre-run 19 showed one greedy lane climbing alone against a target (110 percent of its own reference) it could never reach, and the desk node's template shrinking while it climbed. Pre-run 20 asked two cheap questions with one lane:

1. **Does a never-down greedy rule settle when its target can be met (100 percent of its own reference)? And the normal rule (which may step down) on the same lane?** Our offline check (`tools/sim/sim20.py`, the runner's rule fed pre-run 19's observed landed/reference ratios) said: greedy100 ratchets (median end 235, 10–90 percent 188–368), the normal rule settles at 100.
2. **Is the template shrink about the rate or about how many of our heavy transactions are ready?** Same rate (460), N = 8 then N = 30.

## What happened

- Before the open, with the operator's OK (08:06 Brussels, "do what is best needed"): the sink swept into the payment key, key 16's and key 0's small coins merged, key 3's old step-3 leftovers moved into the payment key, key 0 refilled (63,851 usable), keys 1–15 funded; figures in [PLAYBOOK.md](../PLAYBOOK.md#status-when-this-repo-was-opened). Hop and lane calibrations matched the node; offline rehearsal p20-a exited 0; the bot's free check ran once, read-only, before arming.
- Live run: `PRE-RUN-OPEN` on origin 07:53:54Z, `MINI-ARMED` 07:54:41Z, desk runner from 07:55:35Z. `BUDGET_CHECK` key 0 63,838 usable, 43 planned family minutes, projected end 31,158 (over 26,000). BASE 07:58–08:01 (lane 0), HOLD-1 08:02–08:05 (30 at 150, reference **519** landed a minute), HOLD-2 = probe 1 08:06–08:18 (greedy100 from 08:05:59Z, the normal rule from 08:12:59Z), HOLD-3 = probe 2 08:19–08:26 (N = 8 at 460 from 08:18:59Z, N = 30 at 460 from 08:23:59Z), drain from 08:26:59Z, HOLD-4 pinned minute 08:31, RETURN 08:33–08:36, `RUN_STOP return-closed` 08:37:24Z, `RUN end` 08:43:06Z.
- The outside heavy fee-100 stream of pre-runs 14–16 was essentially absent (0–2 entries a minute).

## Probe 1: the rate paths

Rates in effect at the start of each minute (a decision lands about 22 s into the next minute). Decisions are in [duel.log](duel.log).

| Minute | Rule | Rate in effect | Landed | % of reference (519) | Decision |
|---|---|---:|---:|---:|---|
| 08:06 | greedy100 | 150 | 510 | 98 | 150 → 188 |
| 08:07 | greedy100 | 150 | 510 | 98 | 188 → 235 |
| 08:08 | greedy100 | 188 | 543 | 105 | hold 235 |
| 08:09 | greedy100 | 235 | 512 | 99 | 235 → 294 |
| 08:10 | greedy100 | 235 | 502 | 97 | 294 → 368 |
| 08:11 | greedy100 | 294 | 525 | 101 | hold 368 |
| 08:12 | greedy100 | 368 | 512 | — | segment change (reset to 150) |
| 08:13 | normal | 150 | 510 | 98 | hold 150 |
| 08:14 | normal | 150 | 523 | 101 | 150 → 120 |
| 08:15 | normal | 120 | 498 | 96 | hold 120 |
| 08:16 | normal | 120 | 510 | 98 | 120 → 100 |
| 08:17 | normal | 100 | 515 | 99 | hold 100 (floor) |
| 08:18 | normal | 100 | 478 | 92 | — (segment end) |

- **greedy100 ratcheted:** 4 steps up, 0 down, ending at 368, the top of our offline check's 10–90 percent band (188–368). It stepped up a little faster than our median guess (about one step every 1.5 minutes, not every two).
- **The normal rule settled at its floor** in 4 minutes, as predicted and as pre-runs 16–18 saw with two lanes.
- In both, the lane landed about the same (median 510–512 a minute) at every rate from 100 to 368: the lane is at the ceiling of about one heavy transaction a block, so a higher rate buys nothing. A never-down rule whose target is at the median of its own landings climbs on noise; one that steps down settles.

## Probe 2: the template

`tplwatch20.mjs` read the desk node's own block template every 3 s (read-only; never submitted). Medians per segment, with 10–90 percent ranges:

| Segment | Samples | Template mass | Template txs | Our heavy in template (mean) | Other mass beside it | Ready txs in mempool |
|---|---:|---|---|---:|---|---|
| BASE (lane 0) | 80 | 491,433 (260,578–494,552) | 12 (6–13) | 0.00 | 491,433 | 16 (5–19) |
| N = 30 at 150 (reference) | 79 | 471,689 (390,291–473,474) | 8 (6–11) | 0.89 | 205,230 | 63 (48–100) |
| greedy100 at 150–188 | 60 | 471,752 (408,201–473,069) | 7 (6–9) | 0.93 | 205,082 | 66 (49–104) |
| greedy100 at 235–368 | 80 | 431,434 (308,103–473,130) | 7 (4–10) | 1.00 | 164,735 | 172 (99–304) |
| normal 150 → 100 | 120 | 471,710 (409,244–474,720) | 8 (6–15) | 0.75 | 205,620 | 62 (46–100) |
| **N = 8 at 460** | 100 | **471,954** (470,299–473,497) | 6 (6–7) | 0.98 | **205,094** | 20 (14–24) |
| **N = 30 at 460** | 59 | **348,296** (267,628–392,810) | 5 (3–9) | 1.00 | **81,524** | 480 (325–633) |
| drain and HOLD-4 | 80 | 491,040 | 12 | 0.01 | 491,040 | 16 |
| RETURN | 80 | 490,542 | 12 | 0.01 | 490,542 | 16 |

- With N = 8 at 460 one of our heavy transactions was in nearly every template, as with N = 30, yet the template stayed as full as at 150 (about 472,000). With N = 30 at the same 460 it shrank to about 348,000, and the room beside our heavy transaction fell from about 205,000 to about 82,000. **Our prediction (about 65 percent) that the template would stay clearly fuller with N = 8 held.**
- Our reading (likely, not proven): with many of our heavy transactions ready at a rate far above everything else, the node's weighted random selection keeps drawing more of them after one is in, they do not fit, and the template closes with room left. With few of ours ready, the draws reach the other transactions. This matches the earlier finding that the floor slows once ready mass is over about 9 blocks: N = 8 kept ready mass at about 4 blocks, N = 30 at 15–25.
- What it does not separate: N = 8 also landed fewer of ours (225–244 a minute against 520–547), so part of the tiers' better pace with N = 8 is simply fewer heavy places taken. The template's room beside our heavy transaction is the reading that is not about our landings.

## Bystanders and other users

Per family, percent of BASE (BASE medians per family a minute: floor 47.9, r150 48.9, r300 50.5, r450 50.5); median (range):

| Segment | Floor 100 | R150 | R300 | R450 | Lane landed | Other traffic a minute | Node fee estimate |
|---|---|---|---|---|---|---|---|
| BASE | 100 (98–102) | 100 (95–101) | 100 (94–102) | 100 (95–101) | 0 | 3,154 (3,103–3,184) | 106 |
| N = 30 at 150 | 68 (63–73) | 86 (83–88) | 97 (94–97) | 99 (96–100) | 512 | 3,037 (2,993–3,143) | 218 |
| greedy100 150–188 | 62 (49–67) | 82 (70–87) | 97 (95–100) | 101 (100–105) | 510 | 2,995 (2,918–3,035) | 250 |
| greedy100 235–368 | 28 (21–39) | 51 (38–62) | 85 (78–89) | 95 (88–97) | 512 | 2,958 (2,789–3,065) | 406 |
| normal 150 → 100 | 77 (64–83) | 89 (81–94) | 97 (95–101) | 102 (99–105) | 510 | 3,074 (2,989–3,281) | 240 |
| N = 8 at 460 | 92 (88–96) | 94 (89–97) | 96 (93–101) | 100 (98–104) | 229 | 3,138 (3,050–3,209) | 387 |
| N = 30 at 460 | 10 (10–11) | 25 (21–26) | 69 (66–71) | 89 (87–94) | 525 | 2,934 (2,440–3,079) | 609 |
| HOLD-4 and RETURN | 103 (97–103) | 105 (96–110) | 102 (98–106) | 101 (97–106) | 0 | 3,134 (3,089–3,152) | 156 |

- **Our heavy lane slowed other TN10 users' transactions on our desk node:** other traffic landed about 4 percent under BASE with the lane at 150, about 6 percent at 235–368, and about 7 percent at N = 30 and 460 (23 percent in its worst minute, 2,440); with N = 8 at 460 it was within 1 percent of BASE. It was back at BASE pace in HOLD-4 and RETURN. The node's fee estimate rose with our rate whether or not the tiers were hurt (387 with N = 8 at 460, where the floor kept 92 percent): a user reading it would have paid more than needed.

## Prediction against outcome

| Written before the run | Observed |
|---|---|
| greedy100 ratchets, median end 235 (188–368), not settle | Ratcheted, ended 368 |
| normal rule settles at the floor | 100 after 4 minutes |
| N = 8 at 460 keeps the template fuller (about 65 percent) | Yes: 472,000 against 348,000 |
| N = 8 lands about 100–250 a minute | 225–244 |
| N = 30 at 460 tiers about 10 / 20 / 60 / 85 | 10 / 25 / 69 / 89 |
| Lane fees about 6,000–9,000 tKAS, under the 12,000 cap | 7,656.21 |

## Mini and the bot

- Mini: the runner (`MINI-ARMED` 07:54:41Z) published every step, each read in full, and matched the desk in 131 of 136 cohort cells, 0 removals after a minute had closed. The 5 that differ are off by 1–3 hops: 4 in BASE's first two minutes (07:58–07:59) and 1 in HOLD-3 (08:21, r150). Its TN10 kaspad was not wiped or restarted.
- Bot: the waiter read the desk's HOLD-3 4 s after it was on origin, pinned 08:31Z, checked for a free node 08:30:20–08:30:30Z (the two kept kaspads; every other node that answered was the same kaspad as one of them) and published `NO SEND no-free-node` at 08:32:03Z, first try. Nothing was sent.

## Spend (tKAS, fees unless marked)

- Families: floor 245.18, r150 418.08, r300 968.71, r450 1,509.55 = **3,141.53**.
- Our heavy lane: **7,656.21** in fees (N = 30 at 150 about 0.40 a transaction, at 460 about 1.24), 430.27 parked on our sink key (not swept), 421 pile coins taken.
- Run total about **10,798** in fees, plus a few tKAS for the calibrations. Housekeeping before the open (sweep, merges, key 3 move, refill): about 180 in fees.
- After the run (read-only): key 0 50,277 tKAS in 6,135 coins: 4,105 over 3 tKAS, **33,040 usable** (abort line 18,000; the budget check had projected 31,158), 2,030 small; payment pile (key 16) 1,414 coins, 20,943 tKAS; sink 430.35 (this run's outputs); keys 1–15 have no genesis coin.

## What we take from it

- A never-down rule with a target near the median of its own landings climbs; the target being "reachable" is not enough. A rule that also steps down settles. Pre-runs 16–20 together: the normal rule settled every time (two lanes or one); greedy climbed every time (with a rival, alone above the ceiling, alone at the median).
- On our node, the harm to low-fee transactions follows how many of our heavy transactions are ready at a high rate, more than the rate itself. Few heavy transactions at a high rate cost the bystanders little and left the template full.
- The node's fee estimate tracks the top of the mempool, not what a low-fee transaction actually needs while a heavy lane is there.
