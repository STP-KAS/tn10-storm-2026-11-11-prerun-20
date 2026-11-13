> **Experimental. We are just trying this.** [Disclaimer](../../DISCLAIMER.md) · Kaspa Testnet-10 only; tKAS has no value. Counts only.

# Chain timeline, pre-run 20

Every minute the desk counter read, from its start to the end of the 5-minute tail after RETURN. Read on the desk's private TN10 node, by accepting chain block header time. Submit-OK is the desk sender log for scored minutes (a dash where the runner did not score the minute). A minute marked LAGGING, partial, or not final is what the node had accepted at that point, not a network figure. Nothing is filled in.

| Minute (UTC) | Step (lane) | Scored | Pay submit-OK | Our payments included | Our heavy landed | Floor hops (100) | R150 hops (150) | R300 hops (300) | R450 hops (450) | Other traffic | Included, all non-coinbase | Chain blocks | DAA gap max | Sink age max, ms | Counter |
|---|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|
| 2026-11-13T07:56 | BASE (pre) |  | - | 0 | 0 | 88 | 89 | 90 | 85 | 3,052 | 3,385 | 319 | 1 | 383 | partial |
| 2026-11-13T07:57 | BASE (pre) |  | - | 0 | 0 | 196 | 194 | 209 | 205 | 3,139 | 3,884 | 326 | 1 | 654 | kept pace |
| 2026-11-13T07:58 | BASE (N0-control) | yes | 0 | 0 | 0 | 190 | 194 | 205 | 204 | 3,162 | 3,906 | 340 | 1 | 633 | kept pace |
| 2026-11-13T07:59 | BASE (N0-control) | yes | 0 | 0 | 0 | 188 | 186 | 190 | 191 | 3,184 | 3,898 | 306 | 0 | 880 | kept pace |
| 2026-11-13T08:00 | BASE (N0-control) | yes | 0 | 0 | 0 | 193 | 197 | 199 | 202 | 3,103 | 3,864 | 301 | 0 | 1072 | kept pace |
| 2026-11-13T08:01 | BASE (N0-control) | yes | 0 | 0 | 0 | 195 | 197 | 207 | 202 | 3,147 | 3,887 | 317 | 1 | 673 | kept pace |
| 2026-11-13T08:02 | HOLD-1 (L30-r150-ref) | yes | 0 | 0 | 481 | 121 | 163 | 196 | 202 | 2,993 | 4,139 | 318 | 1 | 749 | kept pace |
| 2026-11-13T08:03 | HOLD-1 (L30-r150-ref) | yes | 0 | 0 | 505 | 129 | 170 | 196 | 202 | 3,001 | 4,191 | 321 | 0 | 469 | kept pace |
| 2026-11-13T08:04 | HOLD-1 (L30-r150-ref) | yes | 0 | 0 | 519 | 139 | 167 | 190 | 197 | 3,073 | 4,267 | 342 | 1 | 439 | kept pace |
| 2026-11-13T08:05 | HOLD-1 (L30-r150-ref) | yes | 0 | 0 | 547 | 133 | 172 | 196 | 194 | 3,143 | 4,367 | 330 | 1 | 362 | kept pace |
| 2026-11-13T08:06 | HOLD-2 (L30-greedy100) | yes | 0 | 0 | 510 | 128 | 171 | 191 | 201 | 3,035 | 4,217 | 320 | 0 | 797 | kept pace |
| 2026-11-13T08:07 | HOLD-2 (L30-greedy100) | yes | 0 | 0 | 510 | 118 | 161 | 196 | 205 | 2,995 | 4,170 | 336 | 1 | 385 | kept pace |
| 2026-11-13T08:08 | HOLD-2 (L30-greedy100) | yes | 0 | 0 | 543 | 93 | 136 | 202 | 212 | 2,918 | 4,091 | 341 | 1 | 435 | kept pace |
| 2026-11-13T08:09 | HOLD-2 (L30-greedy100) | yes | 0 | 0 | 512 | 74 | 121 | 179 | 192 | 3,065 | 4,134 | 316 | 1 | 747 | kept pace |
| 2026-11-13T08:10 | HOLD-2 (L30-greedy100) | yes | 0 | 0 | 502 | 57 | 112 | 175 | 191 | 2,789 | 3,823 | 313 | 1 | 514 | kept pace |
| 2026-11-13T08:11 | HOLD-2 (L30-greedy100) | yes | 0 | 0 | 525 | 49 | 88 | 169 | 196 | 2,927 | 3,953 | 322 | 1 | 678 | kept pace |
| 2026-11-13T08:12 | HOLD-2 (L30-greedy100) | yes | 0 | 0 | 512 | 40 | 75 | 158 | 177 | 2,990 | 3,951 | 316 | 1 | 385 | kept pace |
| 2026-11-13T08:13 | HOLD-2 (L30-normal) | yes | 0 | 0 | 510 | 122 | 159 | 194 | 199 | 3,281 | 4,463 | 342 | 0 | 449 | kept pace |
| 2026-11-13T08:14 | HOLD-2 (L30-normal) | yes | 0 | 0 | 523 | 128 | 175 | 196 | 212 | 2,997 | 4,214 | 327 | 1 | 636 | kept pace |
| 2026-11-13T08:15 | HOLD-2 (L30-normal) | yes | 0 | 0 | 498 | 141 | 166 | 194 | 209 | 3,007 | 4,186 | 304 | 1 | 401 | kept pace |
| 2026-11-13T08:16 | HOLD-2 (L30-normal) | yes | 0 | 0 | 510 | 154 | 180 | 204 | 202 | 2,989 | 4,214 | 323 | 1 | 841 | kept pace |
| 2026-11-13T08:17 | HOLD-2 (L30-normal) | yes | 0 | 0 | 515 | 157 | 184 | 199 | 207 | 3,167 | 4,387 | 346 | 2 | 312 | kept pace |
| 2026-11-13T08:18 | HOLD-2 (L30-normal) | yes | 0 | 0 | 478 | 158 | 174 | 191 | 205 | 3,140 | 4,299 | 308 | 0 | 556 | kept pace |
| 2026-11-13T08:19 | HOLD-3 (L8-r460) | yes | 0 | 0 | 244 | 171 | 174 | 188 | 198 | 3,050 | 3,947 | 325 | 0 | 477 | kept pace |
| 2026-11-13T08:20 | HOLD-3 (L8-r460) | yes | 0 | 0 | 229 | 178 | 183 | 200 | 206 | 3,209 | 4,134 | 330 | 2 | 570 | kept pace |
| 2026-11-13T08:21 | HOLD-3 (L8-r460) | yes | 0 | 0 | 225 | 169 | 177 | 193 | 203 | 3,079 | 3,963 | 318 | 1 | 752 | kept pace |
| 2026-11-13T08:22 | HOLD-3 (L8-r460) | yes | 0 | 0 | 226 | 177 | 184 | 192 | 200 | 3,159 | 4,066 | 305 | 1 | 715 | kept pace |
| 2026-11-13T08:23 | HOLD-3 (L8-r460) | yes | 0 | 0 | 234 | 183 | 190 | 205 | 211 | 3,138 | 4,069 | 345 | 1 | 528 | kept pace |
| 2026-11-13T08:24 | HOLD-3 (L30-r460) | yes | 0 | 0 | 520 | 22 | 42 | 133 | 176 | 2,440 | 3,326 | 325 | 1 | 401 | kept pace |
| 2026-11-13T08:25 | HOLD-3 (L30-r460) | yes | 0 | 0 | 547 | 20 | 50 | 144 | 179 | 3,079 | 4,019 | 329 | 1 | 437 | kept pace |
| 2026-11-13T08:26 | HOLD-3 (L30-r460) | yes | 0 | 0 | 525 | 20 | 49 | 139 | 189 | 2,934 | 3,855 | 334 | 1 | 424 | kept pace |
| 2026-11-13T08:27 | HOLD-4 (N0-drain) |  | - | 0 | 24 | 197 | 200 | 210 | 206 | 3,540 | 4,332 | 315 | 0 | 449 | kept pace |
| 2026-11-13T08:28 | HOLD-4 (N0-drain) |  | - | 0 | 0 | 200 | 210 | 209 | 201 | 3,094 | 3,859 | 315 | 0 | 534 | kept pace |
| 2026-11-13T08:29 | HOLD-4 (N0-drain) |  | - | 0 | 0 | 196 | 202 | 207 | 207 | 3,254 | 4,015 | 343 | 1 | 687 | kept pace |
| 2026-11-13T08:30 | HOLD-4 (N0-drain) |  | - | 0 | 0 | 199 | 204 | 208 | 202 | 3,252 | 4,020 | 326 | 1 | 748 | kept pace |
| 2026-11-13T08:31 | HOLD-4 (N0-drain) | yes | 0 | 0 | 0 | 197 | 205 | 207 | 204 | 3,152 | 3,923 | 330 | 0 | 509 | kept pace |
| 2026-11-13T08:32 | RETURN (N0-drain) |  | - | 0 | 0 | 194 | 201 | 200 | 200 | 3,094 | 3,843 | 320 | 0 | 537 | kept pace |
| 2026-11-13T08:33 | RETURN (N0-drain) | yes | 0 | 0 | 0 | 197 | 205 | 209 | 209 | 3,109 | 3,888 | 341 | 0 | 398 | kept pace |
| 2026-11-13T08:34 | RETURN (N0-drain) | yes | 0 | 0 | 0 | 185 | 188 | 198 | 198 | 3,134 | 3,865 | 338 | 1 | 577 | kept pace |
| 2026-11-13T08:35 | RETURN (N0-drain) | yes | 0 | 0 | 0 | 195 | 215 | 215 | 214 | 3,142 | 3,942 | 340 | 1 | 742 | kept pace |
| 2026-11-13T08:36 | RETURN (N0-drain) | yes | 0 | 0 | 0 | 198 | 199 | 200 | 196 | 3,089 | 3,845 | 321 | 1 | 281 | kept pace |
| 2026-11-13T08:37 | tail (N0-drain) |  | - | 0 | 0 | 86 | 86 | 87 | 84 | 3,091 | 3,415 | 308 | 1 | 568 | kept pace |
| 2026-11-13T08:38 | tail (N0-drain) |  | - | 0 | 0 | 0 | 0 | 0 | 0 | 3,157 | 3,157 | 327 | 1 | 646 | kept pace |
| 2026-11-13T08:39 | tail (N0-drain) |  | - | 0 | 0 | 0 | 0 | 0 | 0 | 3,131 | 3,131 | 344 | 1 | 256 | kept pace |
| 2026-11-13T08:40 | tail (N0-drain) |  | - | 0 | 0 | 0 | 0 | 0 | 0 | 3,158 | 3,158 | 326 | 1 | 400 | kept pace |
| 2026-11-13T08:41 | tail (N0-drain) |  | - | 0 | 0 | 0 | 0 | 0 | 0 | 3,258 | 3,258 | 352 | 0 | 398 | kept pace |
| 2026-11-13T08:42 | tail (N0-drain) |  | - | 0 | 0 | 0 | 0 | 0 | 0 | 2,818 | 2,818 | 316 | 0 | 411 | not final |

Whole run, as read: our payments submit-OK 0, of which included by the end of the tail 0 (- percent). Family hops included: floor 5,975, r150 6,795, r300 7,870, r450 8,175. Our heavy-lane transactions included: 11,474.
