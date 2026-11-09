# Bead: sase-1rq.2.1.4.1.5.3.1.2 — Repair remaining failures from a complete hosted tally

[Bead Pages](../README.md) / [sase-1rq.2.1.4.1.5.3.1](sase-1rq.2.1.4.1.5.3.1.md) / sase-1rq.2.1.4.1.5.3.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.2.1.4.1.5.3--1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.1.4.1.5.3.md) · **Assignee:** `sase-1rq.2.1.4.1.5.3.1.2` · **Size:** medium
**Created:** 2026-11-09 04:31:24 EST · **Closed:** 2026-11-09 17:17:28 EST
**Plan:** [202611/hosted\_contention\_gap.md](https://github.com/sase-org/sase--plans/blob/main/202611/hosted_contention_gap.md)

## Description

hosted-failures: repair every failure family from the completed hosted tally without weakening workload or gates, and prove a complete zero-failure hosted-shape repeat.

## Notes

[2026-11-09T22:17:28Z · sase-1rq.2.1.4.1.5.3.1.2--f] Hosted Telemetry 42578053332 on pre-fix SHA 7a7ecd6885 hit the 90-minute limit and was canceled with 30,422/60,600 items finished and 7 failures observed; its tally is incomplete. The first local wrapper exited 127 before tests because /usr/bin/time was unavailable. Full unchanged-shape local runs (26 workers, CPUs 0-1, one repeat) on SHA 9dc824f were red: fejmnp collected 60,629 with 60,611 passed, 17 skipped, 2 failed; k88h4 and pjph9 each collected 60,629 with 60,609 passed, 17 skipped, 4 failed. Focused matching-load passes: 152/152, 143/143, 481/481, and 247/247; intermediate red repros: xjhtxq 451 passed/4 failed, pbq3vp 621/3, pzaxxg 623/1, 23zveq 1,103/2, cevj8m 1,128/2. The reproduced test synchronization, focus, and timeout issues were repaired without weakening assertions or tested deadlines. sase tool run check bc7196df passed (exit 0). Final full run eytaw3184 ran 2026-11-09 20:46:24-22:04:07 UTC on SHA 9dc824fbb77099044752a9f6c101fe9cae02227b, dirty in 9 tracked files and 2 commits behind origin/master; test Python 3.14.7, pytest 9.0.2; 26 workers, CPUs 0-1, one repeat. Controller tally: 60,630 collected and 60,630 finished, 0 failed, 0 red repeats, exit 0. Pytest terminal summary: 60,614 passed, 17 skipped (one more status than the controller item count; skip detail was not retained). Harness elapsed 4,660.3s; wrapper 4,662.51s; child CPU 8,579.38 user/616.86 system seconds, max child RSS 1,138,924 KiB. Sampler: 302 samples, peak cgroup 16.7 GB, minimum available memory 16.3 GB, minimum free swap 41.8 GB, soak swap 1.0 GB, memory PSI full 2.56, swap-in/out 523,144/1,353,946, OOM-kill delta 0. Epic-symbol check found no entries.

## Dependencies

- **Depends on:** [sase-1rq.2.1.4.1.5.3.1.1](sase-1rq.2.1.4.1.5.3.1.1.md) ✓ · ⧖ 2026-11-09
- **Blocks:** [sase-1rq.2.1.4.1.5.3.1.3](sase-1rq.2.1.4.1.5.3.1.3.md) ◐ · ⧖ 2026-11-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.2.1.4.1.5.3.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.1.4.1.5.3.1.2.md) | [sase-1rq.2.1.4.1.5.3.1.2](sase-1rq.2.1.4.1.5.3.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bd97664`](https://github.com/sase-org/sase/commit/bd97664e07f78922f4f9803cb5688ba0b425f6fd) | fix(contention): repair remaining contention failures | [sase-1rq.2.1.4.1.5.3.1.2](sase-1rq.2.1.4.1.5.3.1.2.md) | 2026-11-09 17:19:20 EST |
