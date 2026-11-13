> **Experimental. We are just trying this.** [Disclaimer](../../DISCLAIMER.md) · Counts only. No key, seed, txid, covenant id, address, host, or port.
>
> Mini's second chain read for pre-run 20. The desk does not write this folder.

# Mini counts

Mini publishes a scored file when the desk's matching file is on origin. HOLD-4 waits for the bot file, the halt file, or 10 minutes, as [GO-MINI.md](../../GO-MINI.md) says. Mini counts only on its own synced TN10 node.

| File | Target |
|---|---|
| BASE.md | no payments, families plus our heavy lane at N = 0 (control), 4 whole minutes, an observation. The first line is `OBSERVATION` |
| HOLD-1.md | our one heavy lane, N = 30 at 150: the reference (4 whole minutes; pre-run 20 has no payment offer) |
| HOLD-2.md | probe 1: one lane N = 30, greedy at 100 percent (7 whole minutes), then the normal rule from 150 (6) |
| HOLD-3.md | probe 2: one lane at a fixed 460, N = 8 (5 whole minutes), then N = 30 (3) |
| HOLD-4.md | the observation minute |
| RETURN.md | lane N = 0 (drain), 4 whole minutes |

In pre-run 20 the desk counter is the first chain count and Mini is the second read. Each file's first line is Mini's own read: `READ`, `PARTIAL`, or `NOT READ`. The chat does not publish this folder.
