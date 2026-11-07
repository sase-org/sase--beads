# Bead: sase-1rq.2.1.4.1.2 — Fix the measured cause of contention runner death

[Bead Pages](../README.md) / [sase-1rq.2.1.4.1](sase-1rq.2.1.4.1.md) / sase-1rq.2.1.4.1.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.2.1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.1.4.md) · **Assignee:** `sase-1rq.2.1.4.1.2` · **Size:** medium
**Created:** 2026-11-07 11:04:38 EST
**Plan:** [202611/contention\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202611/contention_repair.md)

## Description

survival: Use the evidence phase's measurements to fix the dominant resource or process-lifecycle defect. Keep the full default selection, 26 workers, two pinned CPUs, one CI repeat, and 90-minute timeout. Produce a completed full repeat and failure inventory with before/after resource evidence.

## Notes

[2026-11-07T20:15:05Z · sase-1rq.2.1.4.1.2] EVIDENCE (survival, bounded reproducer, uncommitted tree on 578a317bcf, athena py3.14.7, host load ~14-18): MEASURED CAUSE: per-worker collection footprint, not a leak. Single-process collection of the default selection (60,553 items, 5,665 modules) = 1.10 GB RSS; tracemalloc at collection end: assertion-rewritten test-module code 284 MB, other module code 151 MB, fixture closures ~240 MB (29 root autouse fixtures -> 31-45 fixtures per item; 52,837 FuncFixtureInfo but only 2,653 distinct closures), nodes ~60 MB, dataclasses 44 MB; no single module >27 MB. --assert=plain saves only ~120 MB, so no per-item trim fits 26 full collections in 16 GB. One process collecting a 1/26 file shard = 0.33 GB. FIX: whole-suite contention soaks now shard collection: each of the 26 xdist workers collects, imports and runs only its disjoint LPT shard of the test files (tests/_test_shards.assign_shards over tests/shard_timings.json; 215-219 files per worker; simulated max/mean 1.11, all 26 workers active ~87% of wall time, >=20 active ~96%), with a ShardScheduling(EachScheduling) scheduler whose crash replacement inherits only its own shard's unfinished tests. Selection, 26 workers, taskset 0,1, repeat count, timeouts unchanged; explicit paths/node IDs or explicit SASE_PYTEST_DIST keep whole collection. AFTER (same cap as kyhnsmgpcjx9: systemd-run --user scope MemoryMax=15G MemorySwapMax=4G, 26 workers on cpus 0-1, SASE_CONTENTION_REPEAT=1, full sharded collection, -k selecting 2 tests): all 26/26 workers finished collecting by +77..+92 s (BEFORE local: 0/26 by +386 s then OOM at +397 s; BEFORE hosted 42397793381: 0/26 by +1659 s then OOM at +1673 s); peak soak RSS 7.9G / PSS 7.3G (workers 7.8G, ~300 MB each), cgroup peak 7.7G of 15G, soak swap 0.0G, oom_kill +0, PSI memory full 0.0 (BEFORE local: RSS 17.07G / PSS 15.94G, swap 3.27G, cgroup at max 15.0G, oom_kill 1); whole run 95 s. SIDE FINDING (fixed in the same change): sharded import order exposed a real master circular import, sase.ace.revert_agent_resolution -> sase.ace.tui.models -> _loaders._done_common -> sase.ace.revert_agent (facade) -> revert_agent_resolution; `python -c "import sase.ace.revert_agent_resolution"` failed on clean master and so did tests/ace/test_revert_agent_workspace.py collected alone; fixed by importing agent_is_reverted from its leaf module sase.ace.revert_agent_marker, with a fresh-interpreter regression test. Also fixed evidence follow-up #6 (controller progress now force-persists on configure_node; sharded progress reports summed items). Full unchanged-shape repeat follows under a monitor.

## Dependencies

- **Depends on:** [sase-1rq.2.1.4.1.1](sase-1rq.2.1.4.1.1.md) ✓ · ⧖ 2026-11-07
- **Blocks:** [sase-1rq.2.1.4.1.3](sase-1rq.2.1.4.1.3.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.2.1.4.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.1.4.1.2.md) | [sase-1rq.2.1.4.1.2](sase-1rq.2.1.4.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`618dbb5`](https://github.com/sase-org/sase/commit/618dbb5fcfe3a37c336056c4c44af877f97edd70) | fix(test-contention): shard whole-suite collection so 26 workers survive a 16 GB runner | [sase-1rq.2.1.4.1.2](sase-1rq.2.1.4.1.2.md) | 2026-11-07 15:16:52 EST |
