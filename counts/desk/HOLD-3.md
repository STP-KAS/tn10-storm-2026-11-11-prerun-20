OBSERVATION

Not scored. No payment of ours in pre-run 20: families only, on the desk's private node, plus our own heavy lane at the N shown per minute.

# HOLD-3, desk, pre-run 20

> Our own TN10 testing: what we observed in this run, on our own desk node. Counts only. Included is what the desk's private TN10 node accepted on chain, read by the desk counter, by accepting chain block time. Mini's files are a second read.

HOLD-3 in pre-run 20 is probe 2, fewer chains ready at a high rate (one lane at a fixed 460: first N=8, then N=30 as the control): L8-r460 5 whole minutes, L30-r460 3 whole minutes. Families only for payments (no payment of ours); our own heavy lane ran at the N and rate shown per minute (N = how many lane chains may each hold one ready transaction in the mempool). The HOLD file names are kept so the bot's and Mini's gates read as in earlier pre-runs. Not scored.

Families offer 1.2 hop/s, 16 families live, one family-sender process and one builder: floor (families 1–4) 100 sompi/gram on the desk's private node, r150 (families 5–8) 150 sompi/gram on the desk's private node, r300 (families 9–12) 300 sompi/gram on the desk's private node, r450 (families 13–16) 450 sompi/gram on the desk's private node. No payment sender was started.

## Tiers against the mempool, per minute

| Minute (UTC) | Lane 1 N / rate | Lane 2 N / rate | floor (100) | r150 (150) | r300 (300) | r450 (450) | Our heavy in mempool / ready | Our heavy landed, lane 1 / lane 2 | Lane submits OK, lane 1 / lane 2 | Outside heavy at 100 (>200k mass) / ready | Outside at 100, n | Ready mass, blocks | Mempool | Fee estimate priority |
|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 2026-11-13T08:19 | 8 / 460 | 0 / 100 | 171 | 174 | 188 | 198 | 5 / 5 | 244 / 0 | 228 / 0 | - / - | - | 3.81 | 17 | 387.1 |
| 2026-11-13T08:20 | 8 / 460 | 0 / 100 | 178 | 183 | 200 | 206 | 6 / 6 | 229 / 0 | 226 / 0 | - / - | - | 4.54 | 19 | 406.1 |
| 2026-11-13T08:21 | 8 / 460 | 0 / 100 | 169 | 177 | 193 | 203 | 4 / 4 | 225 / 0 | 224 / 0 | - / - | - | 3.93 | 18 | 384.9 |
| 2026-11-13T08:22 | 8 / 460 | 0 / 100 | 177 | 184 | 192 | 200 | 4 / 4 | 226 / 0 | 231 / 0 | - / - | - | 3.94 | 17 | 386.6 |
| 2026-11-13T08:23 | 8 / 460 | 0 / 100 | 183 | 190 | 205 | 211 | 5 / 5 | 234 / 0 | 233 / 0 | - / - | - | 3.80 | 23 | 397.3 |
| 2026-11-13T08:24 | 30 / 460 | 0 / 100 | 22 | 42 | 133 | 176 | 20 / 20 | 520 / 0 | 536 / 0 | 0 / 0 | 1 | 15.09 | 494 | 583.4 |
| 2026-11-13T08:25 | 30 / 460 | 0 / 100 | 20 | 50 | 144 | 179 | 26 / 26 | 547 / 0 | 550 / 0 | - / - | - | 20.68 | 392 | 609.2 |
| 2026-11-13T08:26 | 30 / 460 | 0 / 100 | 20 | 49 | 139 | 189 | 28 / 28 | 525 / 0 | 524 / 0 | 1 / 1 | 1 | 24.82 | 571 | 648.0 |

Lane 1 and lane 2 N / rate are the caps the runner set for that minute (N lane chains each, each chain with at most one ready transaction in the mempool) and each lane's fee rate (in the duel, the rate in effect at the start of the minute). Our heavy in mempool / ready is the probe's median count of our own lane entries; our heavy landed is what the desk counter read as accepted on chain from our lane in the minute; lane submits OK is the lane's own log. Hops are what the desk counter read as accepted on chain in that minute, per tier. Ready mass, blocks, is the median of the probe's samples in the minute (block limit 500,000). Outside at 100 is the median count of mempool entries not in our logs (our lane is in our logs) paying 100 sompi/gram, and heavy is how many of those had a mass over 200,000 (median of samples). The outside stream is not attributed to anyone.

## Chain, desk counter

| Minute (UTC) | Included, all non-coinbase | Our payments included | Floor hops (100) | R150 hops (150) | R300 hops (300) | R450 hops (450) | Other traffic | Chain blocks | DAA gap max | Sink age max, ms | Final after, s | Counter |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|
| 2026-11-13T08:19 | 3,947 | 0 | 171 | 174 | 188 | 198 | 3,050 | 325 | 0 | 477 | 20 | kept pace |
| 2026-11-13T08:20 | 4,134 | 0 | 178 | 183 | 200 | 206 | 3,209 | 330 | 2 | 570 | 20 | kept pace |
| 2026-11-13T08:21 | 3,963 | 0 | 169 | 177 | 193 | 203 | 3,079 | 318 | 1 | 752 | 19 | kept pace |
| 2026-11-13T08:22 | 4,066 | 0 | 177 | 184 | 192 | 200 | 3,159 | 305 | 1 | 715 | 20 | kept pace |
| 2026-11-13T08:23 | 4,069 | 0 | 183 | 190 | 205 | 211 | 3,138 | 345 | 1 | 528 | 20 | kept pace |
| 2026-11-13T08:24 | 3,326 | 0 | 22 | 42 | 133 | 176 | 2,440 | 325 | 1 | 401 | 20 | kept pace |
| 2026-11-13T08:25 | 4,019 | 0 | 20 | 50 | 144 | 179 | 3,079 | 329 | 1 | 437 | 20 | kept pace |
| 2026-11-13T08:26 | 3,855 | 0 | 20 | 49 | 139 | 189 | 2,934 | 334 | 1 | 424 | 19 | kept pace |

Coinbase is taken out as one per merged blue block (on this node a chain block's accepted list carries the coinbase of each blue block it merges). Other traffic is the rest: other users' load, the genesis, and anything not in our logs.

## Hop rate per cohort, as built

Floor (families 1–4, desk private node): 100 sompi/gram per hop. R150 (families 5–8, desk private node): 150 sompi/gram per hop. R300 (families 9–12, desk private node): 300 sompi/gram per hop. R450 (families 13–16, desk private node): 450 sompi/gram per hop. In pre-run 20 that rate is on the hop's node-side mass (kit21): the builder is asked for a bill rate on its own mass so that fee / node mass is the tier's rate.

| Tier | Node rate as built, median (min–max) | Bill rate, median | Node mass, median (min–max) | Node rate in the desk mempool, lowest–highest (probe) |
|---|---|---:|---|---|
| floor (100) | 100.16 (100–100.32) | 315 | 40,978 (40,377–42,175) | 100–100.31 |
| r150 (150) | 150.15 (150–150.32) | 471 | 40,945 (40,384–42,230) | 150–150.32 |
| r300 (300) | 300.18 (300–300.32) | 944 | 41,049 (40,403–42,407) | 300–300.31 |
| r450 (450) | 450.15 (450–450.32) | 1413 | 40,942 (40,422–42,604) | 450–450.32 |

Node rate as built is kit21's fee / node mass (rusty-kaspa v2.1.0 storage mass with UTXO plurality, or compute or transient/2 if larger). In the desk mempool the probe divides the node's fee by the larger of the storage and compute mass the node reports.

## Funding coins, as read from the desk node

The funding coins were not one size. Sizes seen, whole tKAS (coins): 17 (395), 18 (364), 16 (347), 4 (324), 6 (316), 5 (304), 8 (299), 7 (281), 10 (245), 15 (240), 19 (228), 9 (211), and 14 more sizes. The fee is not called the whole cause.

## Minutes

| Minute (UTC) | Pay submit-OK | Attempts | Rejects, rate | Rejects, full | Other | Floor OK / att / rate rej / full rej / waiting | R150 OK / att / rate rej / full rej / waiting | R300 OK / att / rate rej / full rej / waiting | R450 OK / att / rate rej / full rej / waiting | Family stalls logged | Family node mempool-high marks | Clean |
|---|---:|---:|---:|---:|---:|---|---|---|---|---:|---:|---|
| 2026-11-13T08:19 | 0 | 0 | 0 | 0 | 0 | 171 / 354 / 0 / 0 / 4 | 174 / 356 / 0 / 0 / 4 | 186 / 367 / 0 / 0 / 2 | 195 / 369 / 0 / 0 / 1 | 0 | 0 | yes |
| 2026-11-13T08:20 | 0 | 0 | 0 | 0 | 0 | 178 / 370 / 0 / 0 / 4 | 183 / 369 / 0 / 0 / 4 | 202 / 377 / 0 / 0 / 4 | 209 / 383 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T08:21 | 0 | 0 | 0 | 0 | 0 | 169 / 356 / 0 / 0 / 4 | 177 / 362 / 0 / 0 / 4 | 192 / 367 / 0 / 0 / 3 | 199 / 372 / 0 / 0 / 0 | 0 | 0 | yes |
| 2026-11-13T08:22 | 0 | 0 | 0 | 0 | 0 | 177 / 358 / 0 / 0 / 4 | 184 / 358 / 0 / 0 / 4 | 193 / 356 / 0 / 0 / 4 | 204 / 365 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T08:23 | 0 | 0 | 0 | 0 | 0 | 184 / 361 / 0 / 0 / 4 | 191 / 369 / 0 / 0 / 4 | 205 / 382 / 0 / 0 / 4 | 211 / 389 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T08:24 | 0 | 0 | 0 | 0 | 0 | 21 / 294 / 0 / 0 / 4 | 40 / 301 / 0 / 0 / 4 | 133 / 345 / 0 / 0 / 4 | 176 / 365 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T08:25 | 0 | 0 | 0 | 0 | 0 | 20 / 294 / 0 / 0 / 4 | 51 / 306 / 0 / 0 / 4 | 144 / 349 / 0 / 0 / 4 | 178 / 368 / 0 / 0 / 3 | 0 | 0 | yes |
| 2026-11-13T08:26 | 0 | 0 | 0 | 0 | 0 | 20 / 293 / 0 / 0 / 4 | 49 / 305 / 0 / 0 / 4 | 139 / 344 / 0 / 0 / 4 | 190 / 368 / 0 / 0 / 4 | 0 | 0 | yes |

A family stall is a coordinator mark: no hop of that family landed for a while. The family was still attempting. It is logged, and it does not make the minute dirty.

A mempool-high mark means the family node read a mempool at or over 90,000. In pre-run 20 that does not stop the families: the skip does not apply to them. A skip, if one were set, is dirt with its reason (node-skip-fam) for every minute it covers, and it clears when the mempool falls back under the line.

Within 10 percent means 0 to 0 submit-OK in the minute.

## Public nodes (local numbers)

Kept: 1, 5. The family sender reads and submits every tier on the desk's private node, which the desk counter reads. The kept public kaspads are read for sync and DAA only; no payment of ours went to them.

Kept nodes are unique kaspads: each answered with its own node id at the preflight. 3 candidate endpoints passed the check and were 2 kaspads (node 4 is node 1; the second hostname was not used). 3 payment senders per kaspad.

| Node | Synced every sample | Last DAA | Pay submit-OK | Pay rejects | Dropped sockets | Answer ms, median |
|---:|---|---:|---:|---:|---:|---:|
| 1 | yes | 622224341 | 0 | 0 | 0 | 32 |
| 5 | yes | 622224342 | 0 | 0 | 0 | 38 |

## Hop submit to landing, per cohort

| Cohort | Landed of OK | Median ms | Slow tail (p95) ms |
|---|---:|---:|---:|
| floor | 940 of 940 | 1239 | 3083 |
| r150 | 1049 of 1049 | 1223 | 4464 |
| r300 | 1394 of 1394 | 1191 | 2218 |
| r450 | 1562 of 1562 | 1091 | 1673 |

Landing is the accepting block header time the desk's coordinator read. Waiting is submitted-OK not yet landed at the minute's end. Every tier has the same hop shape and the same node; only the rate differs.

## Mempool and template, desk node (probe)

| Minute (UTC) | Samples | Mempool | Ready (no parent in mempool) | Ready mass, blocks of 500k | Other traffic in mempool | Other ready | Other at 100, n | Other at 100, mean mass | Our payments in mempool | Our heavy in mempool / ready | Floor in mempool / ready | R150 in mempool / ready | R300 in mempool / ready | R450 in mempool / ready | Template txs | Template storage mass | Template txs over 100k storage mass | Template: payments | Template: our heavy | Template: floor | Template: r150 | Template: r300 | Template: r450 | Template: other | Fee estimate priority / normal / low | Public 1 mempool | Public 5 mempool |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|---:|---:|
| 2026-11-13T08:19 | 3 | 17 | 20 | 3.81 | 1 | 1 | - | - | 0 | 5 / 5 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 6 | 470,968 | 1 | 0 | 1 | 0 | 0 | 1 | 4 | 0 | 387.1 / 181.2 / 114.2 | 6 | 15 |
| 2026-11-13T08:20 | 3 | 19 | 23 | 4.54 | 1 | 1 | - | - | 0 | 6 / 6 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 6 | 472,752 | 1 | 0 | 1 | 0 | 0 | 2 | 3 | 0 | 406.1 / 182.5 / 114.3 | 14 | 14 |
| 2026-11-13T08:21 | 3 | 18 | 20 | 3.93 | 0 | 0 | - | - | 0 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 6 | 470,747 | 1 | 0 | 1 | 0 | 0 | 1 | 4 | 0 | 384.9 / 181.0 / 114.2 | 23 | 16 |
| 2026-11-13T08:22 | 3 | 17 | 17 | 3.94 | 0 | 0 | - | - | 0 | 4 / 4 | 3 / 3 | 4 / 4 | 4 / 4 | 4 / 4 | 6 | 471,346 | 1 | 0 | 1 | 0 | 0 | 2 | 3 | 0 | 386.6 / 181.1 / 114.2 | 3 | 8 |
| 2026-11-13T08:23 | 3 | 23 | 24 | 3.80 | 1 | 1 | - | - | 0 | 5 / 5 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 6 | 472,291 | 1 | 0 | 1 | 0 | 2 | 1 | 2 | 0 | 397.3 / 181.9 / 114.3 | 4 | 16 |
| 2026-11-13T08:24 | 3 | 494 | 494 | 15.09 | 465 | 465 | 1 | 113,703 | 0 | 20 / 20 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 7 | 351,468 | 1 | 0 | 1 | 0 | 0 | 1 | 2 | 4 | 583.4 / 190.0 / 114.9 | 488 | 492 |
| 2026-11-13T08:25 | 3 | 392 | 391 | 20.68 | 353 | 352 | - | - | 0 | 26 / 26 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 7 | 348,918 | 1 | 0 | 1 | 0 | 0 | 1 | 1 | 3 | 609.2 / 190.7 / 115.0 | 375 | 391 |
| 2026-11-13T08:26 | 2 | 571 | 571 | 24.82 | 531 | 530 | 1 | 338,284 | 0 | 28 / 28 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 14 | 391,164 | 1 | 0 | 1 | 0 | 0 | 1 | 2 | 10 | 648.0 / 191.5 / 115.0 | 578 | 578 |

Read by the probe on the desk's private TN10 node every 20 s, read-only; each cell is the median of that minute's samples. Pre-run 17: ready count and ready mass come from the full mempool read up to 10,000 entries and from the node's own figures (getFeeEstimateExperimental, verbose) above that, where the per-class columns stay blank (the node's wRPC replies are capped at 128 MiB, about 12,500 entries). Ready means no parent in the mempool: in rusty-kaspa v2.1.0 only those are in the selector's frontier. Ready mass is compared with one block's mass limit (500,000): at or under 1 the selector takes all ready transactions best-first; over 1 it samples at random weighted by (fee/mass)^3 (over 4, sample_inplace). Mass is the larger of compute and storage mass, as the v2.1.0 selector normalises it (transient mass is not in the RPC). Other traffic is every mempool entry not in our sender logs (our heavy lane is its own class, our heavy); its fee rate is the node's fee over that mass. Template transactions carry no id in the RPC, so each is matched to a mempool entry by its first input. The template is the desk node's own getBlockTemplate (never submitted): what this node would put in a block at that moment, not a miner's template. The fee estimate is the node's getFeeEstimate, read only; no sender reads it. Public mempool is getInfo's mempool size on each kept public kaspad.
