OBSERVATION

Not scored. No payment of ours in pre-run 20: families only, on the desk's private node, plus our own heavy lane at the N shown per minute.

# HOLD-2, desk, pre-run 20

> Our own TN10 testing: what we observed in this run, on our own desk node. Counts only. Included is what the desk's private TN10 node accepted on chain, read by the desk counter, by accepting chain block time. Mini's files are a second read.

HOLD-2 in pre-run 20 is probe 1, a reachable target (one lane, N=30, from 150): first greedy at 100 percent of its reference (never steps down), then reset to 150 on the normal rule (under 90 percent up, 2 minutes at or over 90 percent down): L30-greedy100 7 whole minutes, L30-normal 6 whole minutes. Families only for payments (no payment of ours); our own heavy lane ran at the N and rate shown per minute (N = how many lane chains may each hold one ready transaction in the mempool). The HOLD file names are kept so the bot's and Mini's gates read as in earlier pre-runs. Not scored.

Families offer 1.2 hop/s, 16 families live, one family-sender process and one builder: floor (families 1–4) 100 sompi/gram on the desk's private node, r150 (families 5–8) 150 sompi/gram on the desk's private node, r300 (families 9–12) 300 sompi/gram on the desk's private node, r450 (families 13–16) 450 sompi/gram on the desk's private node. No payment sender was started.

## Tiers against the mempool, per minute

| Minute (UTC) | Lane 1 N / rate | Lane 2 N / rate | floor (100) | r150 (150) | r300 (300) | r450 (450) | Our heavy in mempool / ready | Our heavy landed, lane 1 / lane 2 | Lane submits OK, lane 1 / lane 2 | Outside heavy at 100 (>200k mass) / ready | Outside at 100, n | Ready mass, blocks | Mempool | Fee estimate priority |
|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 2026-11-13T08:06 | 30 / 150 | 0 / 150 | 128 | 171 | 191 | 201 | 26 / 26 | 510 / 0 | 508 / 0 | - / - | - | 19.94 | 63 | 239.6 |
| 2026-11-13T08:07 | 30 / 150 | 0 / 150 | 118 | 161 | 196 | 205 | 26 / 26 | 510 / 0 | 512 / 0 | - / - | - | 19.42 | 53 | 250.1 |
| 2026-11-13T08:08 | 30 / 188 | 0 / 150 | 93 | 136 | 202 | 212 | 26 / 26 | 543 / 0 | 542 / 0 | - / - | - | 17.43 | 81 | 307.4 |
| 2026-11-13T08:09 | 30 / 235 | 0 / 150 | 74 | 121 | 179 | 192 | 26 / 26 | 512 / 0 | 518 / 0 | - / - | - | 20.08 | 104 | 338.9 |
| 2026-11-13T08:10 | 30 / 235 | 0 / 150 | 57 | 112 | 175 | 191 | 25 / 25 | 502 / 0 | 500 / 0 | - / - | - | 18.97 | 151 | 387.1 |
| 2026-11-13T08:11 | 30 / 294 | 0 / 150 | 49 | 88 | 169 | 196 | 23 / 23 | 525 / 0 | 514 / 0 | - / - | - | 19.30 | 165 | 445.7 |
| 2026-11-13T08:12 | 30 / 368 | 0 / 150 | 40 | 75 | 158 | 177 | 20 / 20 | 512 / 0 | 522 / 0 | - / - | - | 18.58 | 164 | 425.1 |
| 2026-11-13T08:13 | 30 / 150 | 0 / 150 | 122 | 159 | 194 | 199 | 24 / 24 | 510 / 0 | 511 / 0 | - / - | - | 18.10 | 56 | 263.6 |
| 2026-11-13T08:14 | 30 / 150 | 0 / 150 | 128 | 175 | 196 | 212 | 27 / 27 | 523 / 0 | 513 / 0 | - / - | - | 20.88 | 56 | 271.3 |
| 2026-11-13T08:15 | 30 / 150 | 0 / 150 | 141 | 166 | 194 | 209 | 26 / 26 | 498 / 0 | 507 / 0 | - / - | - | 18.89 | 47 | 235.0 |
| 2026-11-13T08:16 | 30 / 120 | 0 / 150 | 154 | 180 | 204 | 202 | 25 / 25 | 510 / 0 | 504 / 0 | - / - | - | 18.14 | 45 | 246.0 |
| 2026-11-13T08:17 | 30 / 120 | 0 / 150 | 157 | 184 | 199 | 207 | 23 / 23 | 515 / 0 | 523 / 0 | - / - | - | 17.40 | 62 | 199.8 |
| 2026-11-13T08:18 | 30 / 100 | 0 / 150 | 158 | 174 | 191 | 205 | 24 / 24 | 478 / 0 | 470 / 0 | - / - | - | 17.83 | 52 | 204.1 |

Lane 1 and lane 2 N / rate are the caps the runner set for that minute (N lane chains each, each chain with at most one ready transaction in the mempool) and each lane's fee rate (in the duel, the rate in effect at the start of the minute). Our heavy in mempool / ready is the probe's median count of our own lane entries; our heavy landed is what the desk counter read as accepted on chain from our lane in the minute; lane submits OK is the lane's own log. Hops are what the desk counter read as accepted on chain in that minute, per tier. Ready mass, blocks, is the median of the probe's samples in the minute (block limit 500,000). Outside at 100 is the median count of mempool entries not in our logs (our lane is in our logs) paying 100 sompi/gram, and heavy is how many of those had a mass over 200,000 (median of samples). The outside stream is not attributed to anyone.

## Chain, desk counter

| Minute (UTC) | Included, all non-coinbase | Our payments included | Floor hops (100) | R150 hops (150) | R300 hops (300) | R450 hops (450) | Other traffic | Chain blocks | DAA gap max | Sink age max, ms | Final after, s | Counter |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|
| 2026-11-13T08:06 | 4,217 | 0 | 128 | 171 | 191 | 201 | 3,035 | 320 | 0 | 797 | 20 | kept pace |
| 2026-11-13T08:07 | 4,170 | 0 | 118 | 161 | 196 | 205 | 2,995 | 336 | 1 | 385 | 20 | kept pace |
| 2026-11-13T08:08 | 4,091 | 0 | 93 | 136 | 202 | 212 | 2,918 | 341 | 1 | 435 | 20 | kept pace |
| 2026-11-13T08:09 | 4,134 | 0 | 74 | 121 | 179 | 192 | 3,065 | 316 | 1 | 747 | 20 | kept pace |
| 2026-11-13T08:10 | 3,823 | 0 | 57 | 112 | 175 | 191 | 2,789 | 313 | 1 | 514 | 20 | kept pace |
| 2026-11-13T08:11 | 3,953 | 0 | 49 | 88 | 169 | 196 | 2,927 | 322 | 1 | 678 | 20 | kept pace |
| 2026-11-13T08:12 | 3,951 | 0 | 40 | 75 | 158 | 177 | 2,990 | 316 | 1 | 385 | 20 | kept pace |
| 2026-11-13T08:13 | 4,463 | 0 | 122 | 159 | 194 | 199 | 3,281 | 342 | 0 | 449 | 20 | kept pace |
| 2026-11-13T08:14 | 4,214 | 0 | 128 | 175 | 196 | 212 | 2,997 | 327 | 1 | 636 | 20 | kept pace |
| 2026-11-13T08:15 | 4,186 | 0 | 141 | 166 | 194 | 209 | 3,007 | 304 | 1 | 401 | 20 | kept pace |
| 2026-11-13T08:16 | 4,214 | 0 | 154 | 180 | 204 | 202 | 2,989 | 323 | 1 | 841 | 19 | kept pace |
| 2026-11-13T08:17 | 4,387 | 0 | 157 | 184 | 199 | 207 | 3,167 | 346 | 2 | 312 | 20 | kept pace |
| 2026-11-13T08:18 | 4,299 | 0 | 158 | 174 | 191 | 205 | 3,140 | 308 | 0 | 556 | 20 | kept pace |

Coinbase is taken out as one per merged blue block (on this node a chain block's accepted list carries the coinbase of each blue block it merges). Other traffic is the rest: other users' load, the genesis, and anything not in our logs.

## Hop rate per cohort, as built

Floor (families 1–4, desk private node): 100 sompi/gram per hop. R150 (families 5–8, desk private node): 150 sompi/gram per hop. R300 (families 9–12, desk private node): 300 sompi/gram per hop. R450 (families 13–16, desk private node): 450 sompi/gram per hop. In pre-run 20 that rate is on the hop's node-side mass (kit21): the builder is asked for a bill rate on its own mass so that fee / node mass is the tier's rate.

| Tier | Node rate as built, median (min–max) | Bill rate, median | Node mass, median (min–max) | Node rate in the desk mempool, lowest–highest (probe) |
|---|---|---:|---|---|
| floor (100) | 100.16 (100–100.32) | 314 | 40,922 (40,377–42,162) | 100–100.32 |
| r150 (150) | 150.14 (150–150.32) | 471 | 40,917 (40,383–42,235) | 150–150.31 |
| r300 (300) | 300.18 (300–300.32) | 943 | 40,979 (40,403–42,409) | 300.01–300.32 |
| r450 (450) | 450.15 (450–450.32) | 1416 | 41,043 (40,422–42,597) | 450–450.32 |

Node rate as built is kit21's fee / node mass (rusty-kaspa v2.1.0 storage mass with UTXO plurality, or compute or transient/2 if larger). In the desk mempool the probe divides the node's fee by the larger of the storage and compute mass the node reports.

## Funding coins, as read from the desk node

The funding coins were not one size. Sizes seen, whole tKAS (coins): 18 (453), 17 (386), 19 (372), 4 (347), 8 (342), 5 (325), 7 (303), 6 (297), 10 (276), 16 (262), 9 (248), 11 (233), and 15 more sizes. The fee is not called the whole cause.

## Minutes

| Minute (UTC) | Pay submit-OK | Attempts | Rejects, rate | Rejects, full | Other | Floor OK / att / rate rej / full rej / waiting | R150 OK / att / rate rej / full rej / waiting | R300 OK / att / rate rej / full rej / waiting | R450 OK / att / rate rej / full rej / waiting | Family stalls logged | Family node mempool-high marks | Clean |
|---|---:|---:|---:|---:|---:|---|---|---|---|---:|---:|---|
| 2026-11-13T08:06 | 0 | 0 | 0 | 0 | 0 | 128 / 343 / 0 / 0 / 4 | 171 / 363 / 0 / 0 / 4 | 191 / 370 / 0 / 0 / 4 | 201 / 368 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T08:07 | 0 | 0 | 0 | 0 | 0 | 118 / 332 / 0 / 0 / 4 | 161 / 354 / 0 / 0 / 4 | 196 / 370 / 0 / 0 / 4 | 205 / 373 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T08:08 | 0 | 0 | 0 | 0 | 0 | 93 / 325 / 0 / 0 / 4 | 136 / 347 / 0 / 0 / 4 | 202 / 382 / 0 / 0 / 4 | 212 / 389 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T08:09 | 0 | 0 | 0 | 0 | 0 | 74 / 316 / 0 / 0 / 4 | 121 / 337 / 0 / 0 / 4 | 179 / 363 / 0 / 0 / 4 | 192 / 369 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T08:10 | 0 | 0 | 0 | 0 | 0 | 57 / 305 / 0 / 0 / 4 | 112 / 339 / 0 / 0 / 4 | 175 / 364 / 0 / 0 / 4 | 191 / 369 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T08:11 | 0 | 0 | 0 | 0 | 0 | 49 / 309 / 0 / 0 / 4 | 88 / 326 / 0 / 0 / 4 | 169 / 361 / 0 / 0 / 4 | 196 / 377 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T08:12 | 0 | 0 | 0 | 0 | 0 | 40 / 304 / 0 / 0 / 4 | 75 / 316 / 0 / 0 / 4 | 157 / 359 / 0 / 0 / 3 | 177 / 360 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T08:13 | 0 | 0 | 0 | 0 | 0 | 122 / 334 / 0 / 0 / 4 | 158 / 351 / 0 / 0 / 3 | 195 / 375 / 0 / 0 / 4 | 199 / 374 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T08:14 | 0 | 0 | 0 | 0 | 0 | 128 / 336 / 0 / 0 / 4 | 176 / 353 / 0 / 0 / 4 | 195 / 368 / 0 / 0 / 3 | 211 / 373 / 0 / 0 / 3 | 0 | 0 | yes |
| 2026-11-13T08:15 | 0 | 0 | 0 | 0 | 0 | 138 / 338 / 0 / 0 / 1 | 165 / 354 / 0 / 0 / 3 | 195 / 370 / 0 / 0 / 4 | 210 / 373 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T08:16 | 0 | 0 | 0 | 0 | 0 | 157 / 345 / 0 / 0 / 4 | 180 / 361 / 0 / 0 / 3 | 202 / 378 / 0 / 0 / 2 | 200 / 385 / 0 / 0 / 2 | 0 | 0 | yes |
| 2026-11-13T08:17 | 0 | 0 | 0 | 0 | 0 | 157 / 347 / 0 / 0 / 4 | 185 / 370 / 0 / 0 / 4 | 201 / 388 / 0 / 0 / 4 | 209 / 389 / 0 / 0 / 4 | 0 | 0 | yes |
| 2026-11-13T08:18 | 0 | 0 | 0 | 0 | 0 | 158 / 348 / 0 / 0 / 4 | 174 / 360 / 0 / 0 / 4 | 191 / 360 / 0 / 0 / 4 | 205 / 370 / 0 / 0 / 4 | 0 | 0 | yes |

A family stall is a coordinator mark: no hop of that family landed for a while. The family was still attempting. It is logged, and it does not make the minute dirty.

A mempool-high mark means the family node read a mempool at or over 90,000. In pre-run 20 that does not stop the families: the skip does not apply to them. A skip, if one were set, is dirt with its reason (node-skip-fam) for every minute it covers, and it clears when the mempool falls back under the line.

Within 10 percent means 0 to 0 submit-OK in the minute.

## Public nodes (local numbers)

Kept: 1, 5. The family sender reads and submits every tier on the desk's private node, which the desk counter reads. The kept public kaspads are read for sync and DAA only; no payment of ours went to them.

Kept nodes are unique kaspads: each answered with its own node id at the preflight. 3 candidate endpoints passed the check and were 2 kaspads (node 4 is node 1; the second hostname was not used). 3 payment senders per kaspad.

| Node | Synced every sample | Last DAA | Pay submit-OK | Pay rejects | Dropped sockets | Answer ms, median |
|---:|---|---:|---:|---:|---:|---:|
| 1 | yes | 622219569 | 0 | 0 | 0 | 32 |
| 5 | yes | 622219569 | 0 | 0 | 0 | 38 |

## Hop submit to landing, per cohort

| Cohort | Landed of OK | Median ms | Slow tail (p95) ms |
|---|---:|---:|---:|
| floor | 1419 of 1419 | 1554 | 5223 |
| r150 | 1902 of 1902 | 1304 | 2813 |
| r300 | 2448 of 2448 | 1113 | 1676 |
| r450 | 2608 of 2608 | 1068 | 1516 |

Landing is the accepting block header time the desk's coordinator read. Waiting is submitted-OK not yet landed at the minute's end. Every tier has the same hop shape and the same node; only the rate differs.

## Mempool and template, desk node (probe)

| Minute (UTC) | Samples | Mempool | Ready (no parent in mempool) | Ready mass, blocks of 500k | Other traffic in mempool | Other ready | Other at 100, n | Other at 100, mean mass | Our payments in mempool | Our heavy in mempool / ready | Floor in mempool / ready | R150 in mempool / ready | R300 in mempool / ready | R450 in mempool / ready | Template txs | Template storage mass | Template txs over 100k storage mass | Template: payments | Template: our heavy | Template: floor | Template: r150 | Template: r300 | Template: r450 | Template: other | Fee estimate priority / normal / low | Public 1 mempool | Public 5 mempool |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|---:|---:|
| 2026-11-13T08:06 | 3 | 63 | 71 | 19.94 | 28 | 27 | - | - | 0 | 26 / 26 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 11 | 470,492 | 1 | 0 | 1 | 0 | 0 | 2 | 4 | 3 | 239.6 / 161.2 / 112.3 | 46 | 67 |
| 2026-11-13T08:07 | 3 | 53 | 71 | 19.42 | 38 | 36 | - | - | 0 | 26 / 26 | 3 / 3 | 3 / 3 | 3 / 3 | 4 / 4 | 8 | 471,297 | 1 | 0 | 1 | 0 | 0 | 2 | 3 | 2 | 250.1 / 163.5 / 112.5 | 48 | 67 |
| 2026-11-13T08:08 | 3 | 81 | 80 | 17.43 | 41 | 40 | - | - | 0 | 26 / 26 | 4 / 4 | 3 / 3 | 3 / 3 | 4 / 4 | 9 | 471,693 | 1 | 0 | 1 | 0 | 0 | 2 | 3 | 3 | 307.4 / 173.1 / 113.5 | 101 | 103 |
| 2026-11-13T08:09 | 3 | 104 | 120 | 20.08 | 79 | 78 | - | - | 0 | 26 / 26 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 8 | 472,369 | 1 | 0 | 1 | 0 | 1 | 1 | 3 | 2 | 338.9 / 176.8 / 113.8 | 101 | 149 |
| 2026-11-13T08:10 | 3 | 151 | 144 | 18.97 | 110 | 109 | - | - | 0 | 25 / 25 | 4 / 4 | 4 / 4 | 3 / 3 | 4 / 4 | 6 | 391,180 | 1 | 0 | 1 | 0 | 0 | 1 | 3 | 2 | 387.1 / 181.2 / 114.2 | 145 | 152 |
| 2026-11-13T08:11 | 3 | 165 | 214 | 19.30 | 178 | 177 | - | - | 0 | 23 / 23 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 12 | 471,585 | 1 | 0 | 1 | 0 | 0 | 1 | 3 | 6 | 445.7 / 184.9 / 114.5 | 205 | 205 |
| 2026-11-13T08:12 | 3 | 164 | 163 | 18.58 | 132 | 131 | - | - | 0 | 20 / 20 | 4 / 4 | 4 / 4 | 4 / 4 | 3 / 3 | 6 | 349,206 | 1 | 0 | 1 | 0 | 0 | 0 | 2 | 2 | 425.1 / 183.7 / 114.4 | 172 | 184 |
| 2026-11-13T08:13 | 3 | 56 | 56 | 18.10 | 17 | 16 | - | - | 0 | 24 / 24 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 6 | 470,243 | 1 | 0 | 1 | 0 | 0 | 1 | 3 | 1 | 263.6 / 166.2 / 112.8 | 55 | 67 |
| 2026-11-13T08:14 | 3 | 56 | 69 | 20.88 | 25 | 24 | - | - | 0 | 27 / 27 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 7 | 473,725 | 1 | 0 | 1 | 0 | 0 | 1 | 3 | 1 | 271.3 / 167.6 / 112.9 | 66 | 72 |
| 2026-11-13T08:15 | 3 | 47 | 58 | 18.89 | 17 | 16 | - | - | 0 | 26 / 26 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 7 | 473,003 | 1 | 0 | 1 | 0 | 1 | 2 | 3 | 0 | 235.0 / 160.1 / 112.1 | 42 | 75 |
| 2026-11-13T08:16 | 3 | 45 | 59 | 18.14 | 14 | 13 | - | - | 0 | 25 / 25 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 7 | 470,875 | 1 | 0 | 1 | 0 | 1 | 1 | 4 | 1 | 246.0 / 162.6 / 112.4 | 86 | 86 |
| 2026-11-13T08:17 | 3 | 62 | 61 | 17.40 | 24 | 23 | - | - | 0 | 23 / 23 | 4 / 4 | 4 / 4 | 3 / 3 | 4 / 4 | 9 | 470,985 | 1 | 0 | 1 | 0 | 1 | 1 | 3 | 3 | 199.8 / 150.5 / 110.9 | 58 | 58 |
| 2026-11-13T08:18 | 3 | 52 | 51 | 17.83 | 12 | 11 | - | - | 0 | 24 / 24 | 4 / 4 | 4 / 4 | 4 / 4 | 4 / 4 | 9 | 471,488 | 1 | 0 | 1 | 0 | 2 | 2 | 3 | 0 | 204.1 / 151.8 / 111.1 | 41 | 50 |

Read by the probe on the desk's private TN10 node every 20 s, read-only; each cell is the median of that minute's samples. Pre-run 17: ready count and ready mass come from the full mempool read up to 10,000 entries and from the node's own figures (getFeeEstimateExperimental, verbose) above that, where the per-class columns stay blank (the node's wRPC replies are capped at 128 MiB, about 12,500 entries). Ready means no parent in the mempool: in rusty-kaspa v2.1.0 only those are in the selector's frontier. Ready mass is compared with one block's mass limit (500,000): at or under 1 the selector takes all ready transactions best-first; over 1 it samples at random weighted by (fee/mass)^3 (over 4, sample_inplace). Mass is the larger of compute and storage mass, as the v2.1.0 selector normalises it (transient mass is not in the RPC). Other traffic is every mempool entry not in our sender logs (our heavy lane is its own class, our heavy); its fee rate is the node's fee over that mass. Template transactions carry no id in the RPC, so each is matched to a mempool entry by its first input. The template is the desk node's own getBlockTemplate (never submitted): what this node would put in a block at that moment, not a miner's template. The fee estimate is the node's getFeeEstimate, read only; no sender reads it. Public mempool is getInfo's mempool size on each kept public kaspad.
