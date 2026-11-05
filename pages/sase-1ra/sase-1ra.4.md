# Bead: sase-1ra.4 — FIFO fairness for pytest worker-token waiters (sase-1pw)

[Bead Pages](../README.md) / [sase-1ra](README.md) / sase-1ra.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.18d](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.18d.md) · **Assignee:** `sase-1ra.4` · **Size:** medium
**Created:** 2026-11-04 17:59:13 EST · **Closed:** 2026-11-04 19:44:27 EST
**Plan:** [202611/next\_ten\_task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202611/next_ten_task_beads.md)

## Description

token_fifo: give WorkerTokenLease waiters cross-process FIFO arrival tickets with bounded backfill and dead-waiter reclamation, proven by a fake-clock starvation test (sase-1pw).

## Notes

[2026-11-05T00:43:53Z · sase-1ra.4--1] PROPOSED FOLLOW-UP: Re-triage the two unrelated check reds tracked by closed sase-1hr and sase-1by — both exact nodes failed on clean base 394ff93 in ToolRun e66ef0c323f487776546942eca872dfe, and current ToolRun aaadee1e97c9102af3dc0e9820b07c73 classified them no_new_failures.

[2026-11-05T00:43:54Z · sase-1ra.4--1] TASK RESOLVED: sase-1pw — implemented pool-locked FIFO waiter tickets, one-grant bounded backfill, process-identity dead-waiter cleanup, and fake-clock race proof; focused lease/reclaim run 80c27f9a9876d121d2cd774a27c3f6fe passed 28 tests. Full check had no new failures; both red nodes were reproduced on clean base 394ff93.

[2026-11-05T00:44:27Z · sase-1ra.4--1] Verified FIFO tickets, bounded backfill, dead-waiter identity reclamation, and the fake-clock starvation race. Focused lease/reclaim run 80c27f9a9876d121d2cd774a27c3f6fe passed 28 tests. sase tool run check found no new failures; both red nodes reproduced on clean base 394ff93. epic-symbols reported no leftovers.

## Dependencies

- **Depends on:** [sase-1ra.3](sase-1ra.3.md) ✓ · ⧖ 2026-11-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ra.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ra.4.md) | [sase-1ra.4](sase-1ra.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0c67730`](https://github.com/sase-org/sase/commit/0c677302d95d9f1eb45c51b4697c2e978ac25393) | feat(tests): add fair FIFO worker-token leases | [sase-1ra.4](sase-1ra.4.md) | 2026-11-04 19:46:04 EST |
