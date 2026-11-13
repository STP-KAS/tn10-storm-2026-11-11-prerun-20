> **Experimental. We are just trying this.** [Disclaimer](../DISCLAIMER.md) · This page does not start a machine. Pre-run 20. Not Wednesday. Not Tuesday. Not pre-run 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19.

# Targets

There is no T0. There is no public clock. There is no latest minute. Nothing in pre-run 20 is scored: every step is an observation of whole minutes.

The hash file comes first and does not wait for the open. Nothing else in this page starts until the gates are true: Mini's TN10 node is synced with DAA moving; the desk's private TN10 node is up from its own data (PowerShell 7, no wipe) and synced; no Tuesday, Wednesday, or pre-run 1 to 19 runner is up; the operator has armed (no paste; see the README); our heavy lane's calibration on the node passed; and this repo's `logs/PRE-RUN-OPEN.md` is on origin.

## Order

1. **Nodes live.** Both TN10 nodes synced, DAA moving. No wipe.
2. **Calibration.** One lane transaction, read back from the desk mempool: node storage mass within 1 percent of our SDK's, fee rate 99–101. Otherwise the lane does not run and that is recorded.
3. **Hashes first.** [hashes/SIXTEEN.md](../hashes/README.md): sixteen rows, family label, tier, sha256 of the lowercase hex covenant id, and an On origin line.
4. **Families.** The sixteen covenant families start on the desk's private node, 1.2 hop/s offered. No payment sender of ours is started.
5. **Our one heavy lane** starts at N = 0 and follows one timeline of whole minutes set by the runner (lane 2 stays at N = 0 throughout):

| Order | File | The lane | Length |
|---:|---|---|---|
| 1 | BASE | 0 (control) | 4 whole minutes |
| 2 | HOLD-1 (the reference) | 30 at 150 | 4 whole minutes |
| 3 | HOLD-2 (probe 1) | 30, greedy at 100 percent of its reference, never steps down; then reset to 150 on the normal rule | 7 + 6 whole minutes |
| 4 | HOLD-3 (probe 2) | 8 at a fixed 460; then 30 at 460 (the control) | 5 + 3 whole minutes |
| 5 | drain, HOLD-4 | 0 | the pinned minute; the bot sends only on a free third public kaspad, or files `NO SEND` |
| 6 | RETURN (after-run control) | 0 | 4 whole minutes |
| 7 | tail | families and lane stopped, the counter reads on | 5 minutes |

The lane's N changes on the minute boundary, on a timeline fixed when the lane starts. The minutes between HOLD-3's end and the pinned minute are the start of the drain; they are in `counts/chain/TIMELINE.md`. The run is sized on the coins we hold after the sweep (key 0 about 760 usable tKAS a family minute, 8,000 over the 18,000 line at the end): 43 planned family minutes.

## Cohorts (families, node rates): the bystanders

| Cohort | Families | Rate, sompi/gram of node mass | Weight against the outside stream at 100, (rate/100)^3 |
|---|---|---:|---:|
| floor | 1–4 | 100, fixed | 1.00 |
| r150 | 5–8 | 150, fixed | 3.38 |
| r300 | 9–12 | 300, fixed | 27.0 |
| r450 | 13–16 | 450, fixed | 91.1 |

A hop is about 41,100–41,700 node mass (storage mass; compute 9,123), a lane transaction about 266,700. kit24 is pre-run 17's, unchanged; no family reads a live rate in this run.

## The two rules (probe 1)

Once a minute, at 22 seconds past the minute or later (the counter's line for the minute just closed is final about 20 seconds after it ends), the desk runner reads that minute and moves the lane's rate:

| What it is | Metric | Reference |
|---|---|---|
| the lane, 30 chains | lane transactions landed in the minute | the lane's median in HOLD-1 minutes 2–4 (at 150) |

- **greedy at 100 percent (7 minutes):** metric under 100 percent of the reference: rate × 1.25, rounded, at most 2,000; it never steps down; otherwise unchanged;
- **the normal rule (6 minutes, reset to 150 first):** metric under 90 percent: rate × 1.25 (at most 2,000); at or over 90 percent two decided minutes running: rate × 0.8 (at least 100);
- the last greedy minute is not decided (the rule changes); an unread, partial or lagging minute holds the rate;
- **cap guard:** 4 decided minutes in a row at 2,000 → `CAP_REACHED`, back to 150, counters cleared;
- **frozen:** if the lane process has stopped (a cap, the pile floor, a reject), `FROZEN` is logged once and the rate is not moved again.

The new rate takes effect about 22 seconds into the next minute. The per-minute snapshot of the rate and every decision are in `logs/duel.log` (lane 2 shows 150 and never moves; it is off).

## Probe 2: fewer chains ready at a high rate

The lane at a fixed 460 (no rule): 5 minutes with N = 8, then 3 minutes with N = 30. `tools/desk/tplwatch20.mjs` (read-only) asks the desk node for a block template every 3 s (never submitted) and records its transaction count, its mass, how many transactions over 200,000 mass it holds (ours are about 266,700; the outside heavy stream, if present, too), the mass of the rest, and the node's ready count and ready mass. The mempool probe keeps its 20-second full read.

## Prediction, written before the run

- **Probe 1, greedy at 100 percent.** Pre-run 19 says the lane's landings do not rise with its rate (a ceiling of about one heavy transaction a block). Our offline check (`tools/sim/sim20.py`: the runner's rule re-typed 1:1, each decided minute drawing the lane's landed/reference ratio from pre-run 19's 12 observed lane minutes, which were under 100 percent in 42 percent of minutes and under 90 percent in 8 percent): over 6 decided minutes the greedy rule ends at a median of **235** (10–90 percent: 188–368), above 150 in 96 percent of draws, about 2.5 steps up. **We expect it to ratchet up, more slowly than pre-run 19 (about one step every two minutes), not to settle:** with a target at the median, about half the minutes fall under it by noise alone, and a rule that never steps down keeps every step.
- **Probe 1, the normal rule.** The same check: 5 decided minutes end at **100** in the median (at or under 150 in 94 percent): 150 → 120 → 100 and held, as pre-runs 17 and 18 saw with two lanes. **We expect it to settle at the floor.**
- **Probe 2.** If our reading of pre-run 19 is right, with N = 8 at 460 the template stays fuller than with N = 30 at 460: about 450,000–490,000 mass and 6 or more transactions, against about 300,000–350,000 and 2–4 with N = 30; and the r300 and r450 tiers lose less with N = 8. If the template shrinks just as much with N = 8, our reading is wrong (a high-rate heavy transaction would close the template whatever the count). N = 8 also lands fewer (we guess 100–250 a minute against about 500), so the tiers will do better with N = 8 for that reason too; the template mass per block and the template count are the test, not the tiers alone. **Our best guess: about 65 percent that the template stays clearly fuller with N = 8.**
- **Bystanders.** At 150 as in pre-run 19 (floor about 70 percent of BASE, r150 about 85); worse the higher the greedy part climbs; at 460 with N = 30 about as in pre-run 19 (floor about 10 percent, r150 20, r300 60, r450 85).
- **Other users** at up to about the lane's rate lose more the higher it goes; at 460 most of them wait.
- **Cost.** About 0.40 tKAS a lane transaction at 150, 1.23 at 460. Our guess for the lane: about 6,000–9,000 tKAS of fees in all, under the 12,000 cap.

## Our heavy lane

- **Shape.** One input (the chain's own coin, from the payment key), two plain pay-to-key outputs: 0.0375 tKAS to a dedicated sink key of ours, and the change back into the chain. Storage mass about 266,670 (KIP-9: 10^12 / 3,750,000 sompi for the small output, the change and input terms nearly cancel). Compute mass about 2,000. Fee rate × mass: about 0.40 tKAS at 150, 2.67 at 1,000 and 5.34 at the 2,000 cap.
- **Why this shape.** Our SDK counts every output at UTXO plurality 1 (pre-run 12's source check); plain outputs have plurality 1 on the node too, so the two agree. A covenant output (plurality 2) would be under-read by the SDK by a factor of four.
- **One lane, pre-run 19's process.** The lane uses chain slots 1–100 of pre-run 18's two-lane process (one node connection, one key-16 pile, its own N, rate and submit bucket: 1,200 a minute, 20 a second); lane 2 (slots 101–200) stays at N = 0 all run, so the counter's lane-2 column (hv2) should read 0.
- **Ready count.** A chain's next transaction goes out only after the previous one has left the desk mempool. So each lane has at most N entries in the mempool and all are ready. About one 267,000-mass transaction fits a 500,000 block, so at about 10 blocks a second the chain takes at most about 600 heavy transactions a minute, shared with any outside heavy. In pre-run 19, 30 chains held 23–28 transactions ready (about 18–26 blocks of ready mass); 8 should hold at most 8.
- **Money.** Only from the payment key (key 16: after the sweep and the move of key 3's leftovers, 3,314 coins of 10 tKAS or more, 68,194 tKAS, before this run's refill of key 0, which moved 1,900 of them, 39,159 tKAS; 1,414 coins, 29,035 tKAS, after). Each chain takes one pile coin and runs it down to under 2 tKAS, then takes the next. The family lane (key 0) is not touched by the heavy lane. The operator said tKAS is not a limit; the caps stay as guards, and the spend is logged.
- **Caps.** 1,200 lane submits a minute; pause above N + 2 lane entries for three probe samples; hold at mempool 90,000 or ready mass over 80 blocks; rate at most **2,000**; stop at **12,000** tKAS of fees or **13,000** tKAS moved, or the pile estimate under **3,000** tKAS (pre-run 19: 4,500 / 4,700 / 1,000); stop on any rejection that is not a timing one, or if the node's rate or mass on our own entries drifts from the calibration.
- **Swept before this run.** The 0.0375 tKAS sink outputs of pre-runs 13 to 19 (136,543, 5,120.36 tKAS) were swept back into the payment key before this repo was opened (153.48 tKAS of fees). This run's outputs stay on the sink key until a later, logged sweep.

## Why this shape

- Pre-run 19 answered "does a greedy lane climb alone" with yes, against a target it could not reach. Probe 1 keeps the lane and the tiers and moves only the target (100 percent, then the normal rule's 90 with steps down), so a climb here would be the rule, not the room.
- Probe 2 keeps the rate (460) and changes only how many of ours are ready, so a fuller template with N = 8 would point at our own ready transactions as the cause of pre-run 19's shrink.
- HOLD-1 gives the lane its reference at the starting point (150); BASE gives the bystanders' reference.
- No payments: the only load is the families, our lane and whatever other TN10 traffic is there.

## What we read

For each minute: the lane's N and rate and every decision (`logs/duel.log`); the lane landed (counter); the desk node's template every 3 s (`tplwatch20.mjs`); hops per tier and each tier's node rate (as built and as the probe read it in the mempool) (desk counter, accepted on chain); our heavy in the mempool and ready (probe), our heavy landed (counter), lane submits (the lane's log); outside heavy at 100 (probe, entries not in our logs); the ready mass in blocks of 500,000 (from the full mempool read up to 10,000 entries, from the node's own figures above); the mempool size and the fee estimate. Mini is a second read of the hops.

## Selection rule

The desk node and the public kaspads answered serverVersion 2.1.0. In rusty-kaspa tag v2.1.0 (commit 01b532e8b553523216471682649693af92f0fd16), `mining/src/mempool/model/frontier.rs` takes every ready transaction best-first while the ready set's mass fits one block, and otherwise samples at random with weight (fee/mass)^3 (`ALPHA = 3`). Only a transaction with no parent in the mempool is ready, so a chained hop is not a candidate until its parent is out of the mempool. A higher fee raises the odds of being drawn; it does not buy a place in a queue. This is the source's rule, read from the code; the run reads the desk node's own template, not a miner's.

Abort line **18,000 usable tKAS** (key 0 coins over 3 tKAS, less 3 tKAS each). The coin count is logged, not a gate (pre-run 13 tripped on change fragments). Key 0 was consolidated and refilled before the open (sized on use; the runner's `BUDGET_CHECK`). Do not lower it.
