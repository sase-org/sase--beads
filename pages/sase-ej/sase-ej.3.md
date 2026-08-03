# Bead: sase-ej.3 — publications lumberjack and sidecar\_publication chop

[Bead Pages](../README.md) / [sase-ej](README.md) / sase-ej.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sh/README.md) · **Assignee:** `sase-ej.3` · **Size:** medium
**Created:** 2026-08-03 10:20:39 UTC · **Closed:** 2026-08-03 11:37:57 UTC
**Plan:** [202608/async\_sidecar\_publication.md](https://github.com/sase-org/sase--plans/blob/main/202608/async_sidecar_publication.md)

## Description

chop: add the new axe lumberjack plus the builtin chop that drains the queue for every project, in agents -> beads -> plan-header order, under bounded per-project locks, work budgets, and exponential backoff.

## Notes

[2026-08-03T11:37:57Z · sase-ej.3] Implemented the publications lumberjack and sidecar_publication builtin chop with lock-free queue discovery, deterministic agent_hood -> bead_pages -> plan_header -> sidecar_push draining, bounded per-project lock/work budgets, pre-attempt persistent exponential backoff, per-request failure/quarantine handling, and stable summary counters. Registered the sorted console script and default 30-second/5-minute lumberjack config; bounded bead/plan/push lock plumbing preserves manual-sync arbitration. Verified focused chop coverage for empty/full-order/contention/quarantine/budget/SIGKILL cases, related publication/lock/config tests (including the managed-sync lock-scope regression), CLI chop/lumberjack listing and dry-run structured no-op output, clean git diff, and full just check passing.

## Dependencies

- **Depends on:** [sase-ej.2](sase-ej.2.md) ✓
- **Blocks:** [sase-ej.4](sase-ej.4.md) ✓
- **Blocks:** [sase-ej.6](sase-ej.6.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ej.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ej.3/README.md) | [sase-ej.3](sase-ej.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`0d6ed1a`](https://github.com/sase-org/sase/commit/0d6ed1a194b2cdb8c398399e82fcbcc903ee51f8) | feat(axe): drain queued sidecar publications | [sase-ej.3](sase-ej.3.md) | 2026-08-03 11:39:46 |
