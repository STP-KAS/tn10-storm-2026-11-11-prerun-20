> **Experimental. We are just trying this.** [Disclaimer](DISCLAIMER.md) · Kaspa Testnet-10 only; tKAS has no value.
>
> **This is a pre-run. Pre-run 20.** It is not the Wednesday run. It is not the Tuesday run. It is not pre-run 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19. A read does not start a runner.

# tn10-storm-2026-11-11-prerun-20

**Pre-run 20 of the Wednesday neuron.** The neuron stays [tn10-storm-2026-11-11](https://github.com/STP-KAS/tn10-storm-2026-11-11). This repo does not edit that repo, does not write `REVIEW_CLOSED`, and does not set or move a clock for it. [tn10-storm-2026-11-10](https://github.com/STP-KAS/tn10-storm-2026-11-10) (Tuesday) is not edited from here either.

> **Our own testing.** This is our own Kaspa Testnet-10 testing, run on our own machines and nodes. What these pages report is what we observed in this run; it is not a claim of how TN10 or Kaspa behave in general.

**Where this starts.** Pre-runs 1 to 4 failed and are closed. Pre-runs 5 to 12 finished through RETURN and are closed. Pre-run 13 ran through the pinned HOLD-4 minute and failed in RETURN on its coin-count abort line; it is closed. Pre-runs 14, 15 and 16 finished through RETURN and are closed. Pre-run 17 failed before RETURN on its own abort line and is closed. Pre-runs 18 and 19 finished through RETURN and are closed. The index of all of them is the [pre-run 2 README](https://github.com/STP-KAS/tn10-storm-2026-11-11-prerun-2#pre-runs-in-this-rehearsal); the cumulative findings are in [tn-master](https://github.com/STP-KAS/tn-master). This repo starts from [pre-run 19's locks/LOCKED.md](https://github.com/STP-KAS/tn10-storm-2026-11-11-prerun-19/blob/ea9b489/locks/LOCKED.md) at commit ea9b489, copied here as [locks/LOCKED.md](locks/LOCKED.md), with a pre-run 20 section added at the end.

## What pre-run 19 left open

[Pre-run 19](https://github.com/STP-KAS/tn10-storm-2026-11-11-prerun-19) ran one greedy heavy lane of ours alone (it wants 110 percent of its own reference and never steps down). As we observed it, the lane climbed 150 → 719 one step a minute with flat landings (458–559 a minute) until its moved cap stopped it: the target was above what the blocks hold for one heavy transaction each, a ceiling, not competition. Two things it left open:

- **Does a greedy rule settle when its target can be met?** Pre-run 19's 110 percent was out of reach from the first minute. What does the same never-down rule do at 100 percent of its own reference, and what does the normal rule (which may step down) do on the same lane?
- **Why did the fixed tiers lose places the lane did not take?** The desk node's own block template shrank from about 470,000 mass (6–9 transactions) at 150 to 268,000–350,000 (2–4) at 368–575, while 23–28 of our heavy transactions were ready. Our reading: with many of our heavy transactions ready at several times every other rate, the selector keeps drawing ours, which do not fit, and closes the template with room left. If that is right, **fewer of ours ready at the same high rate should leave a fuller template.**

## What pre-run 20 tries: two cheap probes

> **We run our own heavy lane on TN10 again, and it slows other TN10 users' transactions.** In this pre-run we submit one bounded stream of our own heavy transactions (about 266,700 storage mass each, 8 or 30 chains, at 150, at rates our two rules set between 100 and 2,000 sompi/gram, and at a fixed 460) from our own test coins. While it runs, other TN10 users' transactions paying up to about the lane's rate wait longer; at 460, most of them. The operator gave the explicit OK for our lane (2026-11-12), said tKAS is not a limit and asked us to test at will, and on 2026-11-13 said to do what is best needed for the study. The lane is calibrated on the node first (at 100 and at 2,000), capped by ready count, by a per-minute submit cap, by a rate cap, by a cap guard and by a spend cap, stepped down to zero at the end, and every step is in this repo. This is our own testing; tKAS has no value.

- **One lane.** Pre-run 19's lane process (lane 2 at N = 0), each transaction about 266,700 storage mass, from the key-16 pile. About one such transaction fits a 500,000 block.
- **Probe 1, a reachable target (HOLD-2, 7 + 6 minutes).** First the greedy rule with its target at **100 percent** of the lane's own reference: under it, rate × 1.25 (cap 2,000); never down. Then the lane is reset to 150 and runs the **normal rule**: under 90 percent × 1.25; at or over 90 percent two minutes running × 0.8 (floor 100). The reference is the lane's median in HOLD-1 (minutes 2–4, at 150). A minute that is unread, partial or lagging holds. Every decision is in `logs/duel.log`.
- **Probe 2, fewer chains ready at a high rate (HOLD-3, 5 + 3 minutes).** The lane at a fixed **460** with **N = 8** chains, then N = 30 at the same 460 as the in-run control (pre-run 19 saw the lane at 460 with N = 30 for one minute). A read-only watcher reads the desk node's block template every 3 s (count, mass, how many of over 200,000 mass, the ready count and mass).
- **A stopped lane freezes the rule.** If the lane meets a cap, the runner logs `FROZEN` and moves no rate after it (pre-run 19 logged paper rates after its cap).
- **Cap guard.** If the lane sits at 2,000 for 4 decided minutes in a row, the runner records it (`CAP_REACHED`) and puts it back to 150.
- **Bystanders.** The sixteen covenant families run at four fixed rates, node rates: floor (1–4) **100**, r150 (5–8) **150**, r300 (9–12) **300**, r450 (13–16) **450**. None of them moves.
- **Funds.** Before this repo, with the operator's OK, the lane's sink outputs from pre-runs 13 to 19 were swept back into the payment key and an old sender key's leftovers were moved there too (all between our own keys; figures in [PLAYBOOK.md](PLAYBOOK.md#status-when-this-repo-was-opened)). Key 0 was refilled to 63,851 usable tKAS; the runner checks before genesis that the usable tKAS projected at the end (760 a planned family minute, 43 planned) stays at least 8,000 over the 18,000 line, or it holds the run.
- **Calibrated on the node before the open.** One hop at 100 and one at 450, and one lane transaction at 2,000 and one at 100, read back from the desk mempool.
- **Steps on one timeline:** BASE (the lane N = 0, 4 minutes), HOLD-1 (one lane, N = 30 at 150, no escalation: the reference, 4 minutes), HOLD-2 (probe 1, a reachable target: the lane N = 30 greedy at 100 percent of its reference, never steps down, 7 minutes; then reset to 150 on the normal rule, 6 minutes), HOLD-3 (probe 2, fewer chains ready at a high rate: the lane at a fixed 460 with N = 8, 5 minutes, then N = 30 at 460 as the control, 3 minutes), then the lane N = 0 (the drain and the after-run control) through the pinned HOLD-4 minute and RETURN (4 minutes), then the counter's 5-minute tail. All are `OBSERVATION`. The HOLD file names are kept so the bot's and Mini's gates read as before.
- **Guards.** The lane keeps pre-run 19's guards (pause at N + 2 entries, hold at mempool 90,000 or ready mass over 80 blocks, stop on a non-timing rejection or a drift from the calibration, 1,200 submits a minute) with the fee cap at **12,000 tKAS**, the moved cap at 13,000 and the pile floor at 3,000 (pre-run 19: 4,500 / 4,700 / 1,000). If the lane meets a cap it stops for the rest of the run, and that is recorded as "gave up (budget)". The family lane's abort line stays **18,000 usable tKAS**.
- **What this can and cannot say.** One lane of ours, on one node, with a fixed reference and rules we chose; short segments; probe 2 changes the ready count and, with it, how many the lane lands; the outside heavy fee-100 stream may be there too. It cannot say how other people's wallets, other rules, other nodes or miners' templates would behave.

The prediction, written before the run, is in [plan/PLAN.md](plan/PLAN.md#prediction-written-before-the-run).

All locked lines from earlier pre-runs stay, except where the pre-run 20 block in [locks/LOCKED.md](locks/LOCKED.md) says what changes and why.

## Machines

| Machine | Go file | First sentence |
|---|---|---|
| Desk | [GO-DESK.md](GO-DESK.md) | DESK. I send and count on pre-run 20. This is not Wednesday. |
| Mini | [GO-MINI.md](GO-MINI.md) | MINI. I count pre-run 20 as the second read. I do not send. This is not Wednesday. |
| Bot | [GO-BOT.md](GO-BOT.md) | GROKBOT. I send payments on the pre-run 20 HOLD-4 only. I do not count. This is not Wednesday. |

The operator does not paste. On 2026-11-12 he asked TN10 ops for covenant pre-runs under congestion and competition, pre-run 11 and then 12, 13 or more as needed (voice, 09:06 and 09:09 Brussels time), and at 10:04 in chat said "Keep exploring". For our own heavy lane he gave the explicit OK in chat at about 11:08 and 11:10 Brussels time ("Do whatever you think is needed", then "No need to keep it short. Tn is for testing. Test at will"), and at 15:19 he said tKAS is not a limit ("Use all the tkas you want"). At 23:26 Brussels time he asked "Can we solve the fee escalation open question?", and at 23:28 said "launch run until you’re happy … Use all the tkas you want", and at about 23:30 "Yes keep going. At will." His word at 23:28 ("launch run until you’re happy … Use all the tkas you want") still stands, and on 2026-11-13 at 08:06 Brussels time he wrote, in effect, to do what is best needed for the study. That is the arm for pre-run 20, its one heavy lane and its two probes, and for the sink sweep before it. The agents start the runners once the gates are facts. [GO.md](GO.md) is the map, [PLAYBOOK.md](PLAYBOOK.md) has the roles and gates, and [plan/PLAN.md](plan/PLAN.md) has the targets and the reasons.

## Gates, in order

No clock. Each gate is a fact read from a node or from origin.

1. Mini's TN10 node is up from its own data, synced, DAA moving.
2. The desk's private TN10 node is up from its own data (PowerShell 7), synced, DAA moving.
3. No other runner or waiter is up. The family lane is above its abort line (18,000 usable tKAS). The desk's private candidate list is present.
4. `hashes/SIXTEEN.md` is on origin: sixteen rows and an On origin line, from the sixteen-family path.
5. The desk pushes `logs/PRE-RUN-OPEN.md`; Mini pushes `logs/MINI-ARMED.md`.
6. The probe and the desk counter are up. Then the families, our heavy lane at N = 0, and the observation steps on the lane's timeline.

Before the open: the hop calibration (node rate within 1 percent of 100 and of 450) and the lane's calibration (at 2,000 and at 100) passed.

## What a decent result is

- `hashes/SIXTEEN.md` on origin before the first family submit.
- Every step file on origin, each with hops per minute for the four tiers (floor, r150, r300, r450), each tier's node rate, each lane's N and rate, our heavy lane and the outside heavy apart, and the probe's table for the same minutes.
- `counts/chain/TIMELINE.md` and `counts/chain/MEMPOOL.md` after the tail, and RETURN on origin.
- Probe 1: the lane's rate path under each rule, minute by minute, its landings against its rate, and an answer (settled, ratcheted up, or gave up on budget). Probe 2: the template's mass and count every 3 s and the tiers' pace with N = 8 against N = 30 at 460, and whether the template stayed fuller with fewer of ours ready; or an honest "not answered" with the reason.
- A HOLD-4 desk file, a bot file or a legal `NO SEND`, and a Mini file.
- The spend, the sweep before the run and this run's parked sink outputs stated in the write-up.
- No id, txid, key, address, host, or port in this repo.

A miss stays in this repo. A next attempt is a new repo and starts from this repo's lock file.

**Part of [tn-master](https://github.com/STP-KAS/tn-master).** The rule is [docs/NEURON.md](https://github.com/STP-KAS/tn-master/blob/main/docs/NEURON.md). This pre-run is its own row. It is not row 47.
