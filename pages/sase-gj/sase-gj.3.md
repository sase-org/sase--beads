# Bead: sase-gj.3 — A bounded-parallelism middle gear for large selections

[Bead Pages](../README.md) / [sase-gj](README.md) / sase-gj.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ue](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ue/README.md) · **Assignee:** `sase-gj.3` · **Size:** medium
**Created:** 2026-08-06 16:02:10 EDT · **Closed:** 2026-08-06 17:57:34 EDT
**Plan:** [202608/scoped\_lane\_latency.md](https://github.com/sase-org/sase--plans/blob/main/202608/scoped_lane_latency.md)

## Description

gear: let a scoped run that exceeds the serial budget take a small non-blocking lease instead of escalating, falling back to serial rather than ever queueing.

## Notes

[2026-08-06T21:57:34Z · sase-gj.3] gear: over-budget selections now take a bounded, non-blocking suite-gate lease instead of escalating. New tests/_test_selection_gear.py (ceiling SASE_TEST_SELECTION_SCOPED_WORKER_CEILING=4, floor 2, refusal reasons); WorkerTokenLease.try_acquire() added by refactoring acquire()'s loop body into one _attempt(); select_tests keeps the rejected selection on Selection.gear_candidate ONLY when serial-budget-exceeded fired alone (change-set and ratio escalations are never offered to the gear); run_pytest runs the candidate at the granted width, de-escalates the manifest so the real duration and width reach the health store, and drops its belt-and-braces SASE_TEST_GATE_DISABLED in favour of the lease's own governed marker; refusal escalates, never queues. Manifest schema 6->7 with a gear block; _reject_scoped_worker_overrides still rejects -n/SASE_PYTEST_WORKERS with a rewritten reason; selection-health gained gear_runs/gear_refused_runs/duration_widths, SlowRun.worker_count, and now charges worker-seconds at the leased width. Verified: 22 new/updated tests incl. two end-to-end miniature-repo runs (free 4-slot pool -> -n 4, manifest gear granted, whole pool free again after; exhausted pool -> 'no bounded lease (tokens-unavailable)' + escalation, holder's token untouched, no wait). just check green (escalated to the full lane on root-conftest+selection-tooling: 26461 passed, 7 skipped, 142s) plus mypy/ruff/symvision/toobig; just selection-health renders the new gear lines against the real 90-record store. docs/development.md gained a 'middle gear' section and the serial-only claim is corrected. NOT COMMITTED: the working tree carries the change; no commit was requested.

## Dependencies

- **Depends on:** [sase-gj.2](sase-gj.2.md) ✓ · ⧖ 2026-08-06
- **Blocks:** [sase-gj.7](sase-gj.7.md) ◐ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gj.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gj.3/README.md) | [sase-gj.3](sase-gj.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ca6c1e0`](https://github.com/sase-org/sase/commit/ca6c1e09e8be639db7d4f386860c043f4da1a3af) | feat(test-selection): add a bounded-parallelism middle gear for large selections | [sase-gj.3](sase-gj.3.md) | 2026-08-06 17:58:47 EDT |
