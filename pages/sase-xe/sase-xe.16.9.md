# Bead: sase-xe.16.9 — Fleet benches under faults and the remaining failure-table tests

[Bead Pages](../README.md) / [sase-xe.16](sase-xe.16.md) / sase-xe.16.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08c.md) · **Assignee:** `sase-xe.16.9` · **Size:** large
**Created:** 2026-09-08 10:21:39 EDT · **Closed:** 2026-09-08 13:24:12 EDT
**Plan:** [202609/remote\_dispatch\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_completion.md)

## Description

fleet-perf-faults: extend the j/k agents bench suite with fleet scenarios - a hung host, a reconnect storm, and an event burst - assert the p95 < 16 ms performance contract, and document the capture recipe in the perf runbook. Add the two failure-table fault tests still missing after landing: a host hang hits the facade deadline and leaves other hosts unaffected, and name/PID reuse is rejected by exact-instance fencing on remote rows. Wire or deliberately defer explicit-follow family promotion at reconciliation time (the follow store's reconcile path accepts promotions, but no production caller computes them from followed-batch family identity).

## Notes

[2026-09-08T17:24:12Z · sase-xe.16.9] Implemented Fleet fault benchmark and failure-table coverage from plan:202609/fleet_perf_faults.md. Verification: focused follow-store/Fleet refresh/Fleet model/federation/mutation tests passed (33 passed); slow Fleet j/k fault benchmark passed for hung_host, reconnect_churn, and event_burst with all j/k p95 values under 16 ms and no stall records; just check rerun passed fmt, Ruff, mypy, feature-flag, pyscripts, test-waits, changelog, terminology, symvision, toobig, SASE validation, and committed-plan lanes, then failed only two unrelated full-suite flakes (tests/main/test_proc_handler_run.py::test_run_prints_the_id_and_the_follow_hint and tests/test_clan_summary_script_execution.py::test_timed_out_summary_script_escalates_to_sigkill_when_sigterm_is_ignored), both of which passed immediately on unchanged targeted rerun (2 passed in 7.86s). Recorded follow-up evidence on sase-j7 and sase-xb. Pre-close epic-symbols check: no --epic-symbol entries for sase-xe.16.9.

## Dependencies

- **Depends on:** [sase-xe.16.7](sase-xe.16.7.md) ✓ · ⧖ 2026-09-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.9](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.16.9.md) | [sase-xe.16.9](sase-xe.16.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7ee2e51`](https://github.com/sase-org/sase/commit/7ee2e51778692064bb4bc588c07a943b616475b1) | feat(fleet): harden fault refresh performance coverage | [sase-xe.16.9](sase-xe.16.9.md) | 2026-09-08 13:27:02 EDT |
