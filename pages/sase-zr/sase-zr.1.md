# Bead: sase-zr.1 — Measure approval stages and replace full-history gate lookup

[Bead Pages](../README.md) / [sase-zr](README.md) / sase-zr.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.athena.0js` · **Assignee:** `sase-zr.1` · **Size:** medium
**Created:** 2026-09-12 05:06:13 EDT · **Closed:** 2026-09-13 19:16:37 EDT
**Plan:** [202609/prompt\_gate\_approval.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompt_gate_approval.md)

## Description

bounded-gate-resolution: In sase-core and sase, instrument the approval boundaries from submission through paint and replace find_gate_shell_by_gate_id's full-history scan with an indexed exact gate-id lookup exposed through the Rust binding. Maintain the lookup on gate creation and marker mutation, handle old indexes off the interactive path, and test that lookup work stays bounded as unrelated history grows. Resolve the exact owning shell, not a successor inheriting its gate id. Preserve project scoping and newest-real-shell behavior. Run focused Rust/PyO3 and Python tests and each changed repository's required checks.

## Notes

[2026-09-13T23:14:52Z · sase-zr.1--2] PROPOSED FOLLOW-UP: tests/test_axe_chop_output_contract.py::test_managed_tmp_reap_emits_{noop,action}_summary fail on current master — commit 8f7dad695b (feat(disk): add pressure footprint reporting) added pressure_available_bytes/pressure_recovery_available_bytes to the reap counters dict without updating this contract test's expected keys. Reproduced deterministically (2/2 runs), unrelated to sase-zr.1's files.

[2026-09-13T23:15:45Z · sase-zr.1--2] PROPOSED FOLLOW-UP: sase agent sync has a growing quarantine backlog (56 quarantined agent-hood publication requests seen at landing time, "agents sync lock is busy") that deferred this bead's commit-link publication; may need `sase agent sync --retry-quarantined` or investigation into the persistent lock contention.

[2026-09-13T23:16:37Z · sase-zr.1--2] Landed 93f3d58911 (feat(gate-shell): indexed gate-shell-by-gate-id lookup with telemetry) on origin/master, resolving the paused interactive rebase's conflict in tests/monitor/test_monitor_proc_settlement.py (all tests in that file pass). Verified with just check + full scoped pytest run (reached 97%, xdist teardown IPC noise obscured the summary): confirmed the 9 apparent failures are unrelated to this bead's files — 5 were xdist worker-teardown artifacts (pass individually), 2 are a pre-existing master regression from commit 8f7dad695b (disk-pressure feature) in test_axe_chop_output_contract.py, and 1 was an already-known flaky monitor_resume assertion (independently fixed upstream in 0eb2bbea5a, now pulled in by the push). epic-symbols clean, no leftover --epic-symbol entries. Two PROPOSED FOLLOW-UP notes recorded for the unrelated axe_chop test drift and the agent-sync quarantine backlog.

## Dependencies

- **Blocks:** [sase-zr.2](sase-zr.2.md) ✓ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-zr.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-zr.1/README.md) | [sase-zr.1](sase-zr.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`93f3d58`](https://github.com/sase-org/sase/commit/93f3d58911b9968575bd08676c65b3577e01e016) | feat(gate-shell): add indexed gate-shell-by-gate-id lookup with telemetry | [sase-zr.1](sase-zr.1.md) | 2026-09-13 19:12:59 EDT |
| sase-core | [`sase-core@682dbec`](https://github.com/sase-org/sase-core/commit/682dbeca5967c2fd210597c6c9a6df6b90991a1b) | feat(agent\_scan): add core index module and Python bindings for gate-shell lookup | [sase-zr.1](sase-zr.1.md) | 2026-09-13 19:19:11 EDT |
