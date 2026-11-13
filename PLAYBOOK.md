> **Experimental. We are just trying this.** [Disclaimer](DISCLAIMER.md) · Kaspa Testnet-10 only; tKAS has no value.
>
> **This is the playbook for pre-run 20.** It is not Wednesday. It is not Tuesday. It is not pre-run 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19. It does not start a machine and it does not arm one.

# Playbook

Who does what, and the gates before each machine may start. The plan is [plan/PLAN.md](plan/PLAN.md), the locks are [locks/LOCKED.md](locks/LOCKED.md), and the go files are the three GO pages. This page does not override them.

## Oversight

TN10 ops oversees this rehearsal end to end: Mini, the desk (Build), and the bot. TN10 only. Never mainnet. Do not edit the Tuesday repo, the Wednesday repo, or pre-run 1's to 19's go files. Do not write `REVIEW_CLOSED`.

For pre-run 20 the operator does not paste. On 2026-11-12 he asked TN10 ops for covenant pre-runs under congestion and competition, pre-run 11 and then 12, 13 or more as needed (voice, 09:06 and 09:09 Brussels time), and at 10:04 in chat said "Keep exploring". That is the arm. The agents start their runners once the gates are facts.

## Start gates

1. **Mini node synced.** Existing TN10 kaspad, existing data, no wipe. `isSynced` true, DAA moving.
2. **Desk node synced.** Existing private TN10 kaspad, existing data, loopback only, started with `pwsh`. No wipe. Synced, DAA moving.
3. **No other runner.** No earlier runner, waiter, or counter on any machine. Lane above the abort line. The desk's private candidate list is present and not empty (`HELD candidates-missing` otherwise).
4. **Hashes.** `hashes/SIXTEEN.md` with sixteen rows and an On origin line, from [tools/sixteen](tools/sixteen/README.md).
5. **Open.** The desk pushes `logs/PRE-RUN-OPEN.md`. Mini then pushes `logs/MINI-ARMED.md`.
6. **Counter, families, senders.** The desk runner starts the counter on its private node and waits for its start line (`HELD counter-down` otherwise). Then the genesis from the bundle that wrote `hashes/SIXTEEN.md`, the families, and the payment steps.

## Who does what

| Who | Role | What not to do |
|---|---|---|
| **Desk (Build)** | Sends the sixteen families (four fixed tiers, one path, one build, kit24) and runs our own heavy lane in one lane process (one lane; the operator's OK, calibrated first). No payments. Its private TN10 node counts what the chain accepted (lock line (iv)) and its probe reads the mempool (xii). Publishes `hashes/SIXTEEN.md`, `logs/PRE-RUN-OPEN.md`, `counts/desk/` per step, `counts/chain/TIMELINE.md` and `MEMPOOL.md` after the tail, and `logs/METHOD.md`. | Do not stop or wipe the desk node. No Windows PowerShell 5.1, no `KaspaPublicNode`, no miner, no devnet. No 8- or 32-family publisher. No second runner. Never restart the runner mid-run. No payment sender. No heavy lane other than the runner's own lane process (which carries both lanes). |
| **Mini** | Second chain read on its own node. Does not send, mine, or hold a key. Publishes `logs/MINI-ARMED.md`, then `counts/mini/` when the matching desk file is on origin. | Do not wipe. Do not repeat the desk's head as Mini's. |
| **Bot (TN10 ops)** | Sends payments in the HOLD-4 minute only, on a synced public kaspad that is not one the desk kept, or publishes a legal `NO SEND`. | Do not send in any other step. One waiter. No local node. |

## Status when this repo was opened

Not a gate. Read on 2026-11-13 between 07:08Z and 07:27Z. This is our own TN10 testing; status lines are what we read on our own machines.

- Mini: existing TN10 kaspad 2.1.0 up, no wipe. Pre-run 19's Mini runner ended on its own after its tail (gone by 05:54Z); pre-run 20's Mini runner starts only after that was read again.
- Desk: existing private TN10 kaspad 2.1.0 up with `pwsh`, no wipe. It is not stopped for this pre-run. Pre-run 19's runner ended on its own at 05:44:42Z. `serve.mjs` and its keeper are not touched.
- Box: no local TN10 node. No bot waiter running.
- **Housekeeping before this repo (the operator's OK, 2026-11-13 08:06 Brussels: "do what is best needed").** All between our own keys, none rejected, rate 100, recorded privately on the desk:
  - **The sink is swept.** The lane's 0.0375 tKAS outputs from pre-runs 13 to 19 (136,543 coins, **5,120.36 tKAS**) went back to the payment key (key 16), 07:12:19Z–07:19:52Z: 1,626 transactions of 84 inputs, paced (8 every 2 s), **153.48 tKAS** in fees. The sink key held 0 coins after.
  - Key 16's own chain ends (4,680 coins of 1–10 tKAS, 11,339 tKAS) were merged into coins of about 20 tKAS (69 transactions, 5.46 tKAS in fees). Key 0's 1,029 small coins (2,485 tKAS) were merged (14 transactions, 1.19 tKAS).
  - **Key 3's old leftovers.** Key 3 (one of our own sender keys from the step-3 runs at the end of October, idle for about 12 days) held 56,701 tKAS in 12,415 coins. Its coins older than 24 hours (12,404, **56,621.44 tKAS**) were moved to key 16 in coins of about 20 tKAS (255 transactions, 15.02 tKAS in fees). Keys 1 and 2 were left as they are.
- **Family lane** (key 0), after the merge: 4,250 coins over 3 tKAS, **30,592 usable**. **Refilled from the payment pile** 07:24:24Z (`refill20.mjs`): 95 transactions, none rejected, 1,900 pile coins (39,159 tKAS) to key 0 at the same sizes, 4.37 tKAS in fees. Keys 1–15 got a fresh genesis coin (15 transactions, none rejected). After: key 0 6,135 coins over 3 tKAS, **63,851 usable**, no small coins; payment pile **1,414 coins, 29,035 tKAS**.
- **Budget.** The families use about 760 usable tKAS a family minute, and the runner asks for 8,000 over the 18,000 line at the end. This run plans **43 family minutes**. Read-only check `budget20.mjs`, 07:25Z: 63,851 − 760 × 43 = **31,171 projected at the end**, over 26,000: ok. The runner repeats this check before genesis and holds the run if it fails.
- **The lane's budget.** Fee cap **12,000 tKAS**, moved cap 13,000, pile floor 3,000 (pre-run 19: 4,500 / 4,700 / 1,000). If the lane meets a cap it stops for the rest of the run ("gave up (budget)"), and from this run the controller freezes then (`FROZEN`), so no paper rates follow.
- **Hop calibration on the node** (kit24, unchanged since pre-run 17), 07:25:21Z: one calibration covenant on key 0 (launch path `…-p20-cal`, not one of the sixteen families and not in `SIXTEEN.md`), its genesis, then two hops built by the family path and submitted on the desk's private node, each read back from the desk mempool:

| Hop | Builder bill rate (on 13,046) | kit24 storage mass | Node storage mass | Node compute mass | Fee, sompi | Node rate (fee ÷ node mass) |
|---|---:|---:|---:|---:|---:|---:|
| family 1 at 100 | 317 | 41,355 | 41,355 | 9,123 | 4,135,582 | 100.00 |
| family 13 (r450) at 450 | 1,433 | 41,542 | 41,542 | 9,123 | 18,694,918 | 450.02 |

  Storage mass matched to the unit and both node rates were within 1 percent of the asked rate (and not under it).
- **Our heavy lane's calibration:** at 2,000, 07:25:35Z: SDK storage mass 266,740, node 266,740 (0.00 percent off), compute 2,036, node rate 2,000.00 (fee 5.33 tKAS). At 100, 07:26:06Z: 266,671 on both sides, node rate 100.00. The sink key is the same one (now swept); this run's sink outputs stay there until a later sweep.
- The re-read just before `PRE-RUN-OPEN` (nodes synced, the Mini runner gone, the bot's free check) is recorded in the offline rehearsal section below.
- Known risks, not fixed mid-run:
  - Our lane slows other TN10 users' transactions at fees up to about its own rate while it runs. Probe 2 runs it at 460 on purpose; the greedy part may climb. The operator OK'd our lane; the rate is capped at 2,000, the lane's fees at 12,000 tKAS, the cap guard puts it back to 150 after 4 minutes at the cap, and the lane steps down to zero at the end.
  - Short segments: BASE 4 minutes, a 4-minute reference (median of minutes 2–4), 7 + 6 minutes for probe 1 and 5 + 3 for probe 2. One run.
  - With N = 8 the lane lands fewer transactions, so probe 2 changes two things at once (fewer ready, and fewer landed); the template every 3 s and the N = 30 control at the same rate are there to tell them apart.
  - The outside heavy fee-100 stream may also be there.
  - The rule reacts to the minute just closed and takes effect about 22 seconds into the next one.
  - The probe and the template watcher read the desk node's mempool and template, not a miner's.
  - Only two unique public kaspads answered in every check so far, and the desk keeps both, so the bot is expected to file `NO SEND no-free-node`.

## Offline rehearsal, recorded before `PRE-RUN-OPEN`

Rehearsal `p20-a` ran on the desk against the fake node (no network for the sends), 2026-11-13 07:27:30Z to 07:51:27Z, with 2-minute lane steps (`STORM_LANE_MIN=2`, `STORM_RET_MIN=2`) and the probe's full read capped at 5,000 entries, using this pre-run's runner, lane, counter, probe, template watcher, kit24 and family-fee files (the same files, by hash after line endings, as the live run and this repo's `tools/desk`).

- Preflight passed; `BUDGET_CHECK` logged (key 0 63,838 usable, 24 planned family minutes in the rehearsal, projected end 45,598, over the line plus margin); genesis 16 of 16 live; `FEE_SPLIT` verified floor 100, r150 150, r300 300, r450 450; `LANE_PLAN` BASE N0, HOLD-1 the reference, HOLD-2 greedy100 + normal, HOLD-3 N 8 at 460 + N 30 at 460, then the drain. The template watcher started with the probe (`KID tplwatch detached`) and wrote 445 rows every 3 s.
- One lane submitted with no rejections and no losses (5,868 OK); lane 2 stayed at N = 0.
- The controller did what the plan says: the reference from HOLD-1 (one minute in 2-minute steps); greedy at 100 percent held at 150 on a minute at 103 percent (no step down, the counter of good minutes only); the rule change reset the lane to 150 and held the last greedy minute (`segment-change`); the normal rule held at 150 on a first minute at 101 percent; then the fixed 460 with N = 8 and N = 30 was set on the minute boundaries, and the drain at N = 0. No `ERROR` line.
- Every step file, TIMELINE, MEMPOOL and METHOD published to the rehearsal's local origin; `RUNNER_EXIT 0`.
- Not reached in the rehearsal: the cap guard, the budget hold, and `FROZEN` (the lane never stopped).

## Status after the live run

AFTER_PLACEHOLDER

### Public statement

We run our own heavy lane on TN10 in this pre-run, with the operator's OK: 30 chains for 4 minutes at 150, 13 minutes at rates our two rules set between 100 and 2,000 sompi/gram, then 8 and 30 chains at a fixed 460 for 8 minutes. While it runs, other TN10 users' transactions paying up to about the lane's rate wait longer on the nodes that see them; at 460, most of them. The figures for this run are added here after it. This is our own testing; tKAS has no value.

## When something breaks

Append a worked fix to [locks/LOCKED.md](locks/LOCKED.md) in the form that page shows, and a repair line to `logs/FIXES.md`. If the run dies before RETURN, write `logs/FAILED.md`, stop every runner, waiter, and counter, and do not resume. The next attempt is a new repo that starts from this repo's lock file.
