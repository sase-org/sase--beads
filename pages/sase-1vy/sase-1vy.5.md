# Bead: sase-1vy.5 — Tool-admission overlap flake: rule out a real limit violation (sase-1vw)

[Bead Pages](../README.md) / [sase-1vy](README.md) / sase-1vy.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1vn.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vn.land.md) · **Assignee:** `sase-1vy.5` · **Size:** large
**Created:** 2026-11-28 03:14:45 EST · **Closed:** 2026-11-28 07:34:56 EST
**Plan:** [202611/backlog\_epic\_2.md](https://github.com/sase-org/sase--plans/blob/main/202611/backlog_epic_2.md)

## Description

admission-overlap-flake: fix sase-1vw. Read sase-1vw and all of its notes first (related sase-1ve tracks a different node in the same module). test_limit_two_with_four_runs_never_overlaps_more_than_two failed once under host load with no admission change in the finding diff, then passed 5/5 isolated plus a green whole-module run. Determine whether the overlap measurement needs a semantic wait or the failure is a real admission-limit violation with more than two concurrent runs at limit two; fix whichever it is. Do not close on a single green rerun. Run sase tool run check, then close sase-1vw and the phase bead.

## Notes

[2026-11-28T12:22:56Z · sase-1vy.5] Root cause: admit_before_spawn commits the durable admission record before spawn_child runs (src/sase/tool/executor_run.py run_recorded_body), with fingerprint/env prep in between; two admitted records can therefore precede two child start stamps on a loaded host. Original failure run 7d9af4cef7ba6b82066e96437690602e shows assert 1 == 2 at tests/tool/test_admission_processes.py:290, never reaching _max_overlap. Fix: keep admitted/waiting waits, then _wait_for >=2 starter stamps followed by exact ==2 assertion with stamp diagnostics; no sleep, no timeout change, no retries. Preserves 42255c3cce nested-wait pattern and all real-process overlap checks. Verification: focused node 5/5 green serial, whole module 8/8 green serial, SASE_PYTEST_WORKERS=2 governed lane 8/8 green. Full wrapped check to follow via prepared verify monitor.

[2026-11-28T12:34:56Z · sase-1vy.5] Verified: semantic startup wait landed in test_limit_two_with_four_runs_never_overlaps_more_than_two. Root cause confirmed as test race, not product violation: admit_before_spawn commits the durable admission record before spawn_child (executor_run.py run_recorded_body), so two admitted records precede two child start stamps under load; original run 7d9af4ce failed at assert 1 == 2 before reaching _max_overlap. Fix waits for >=2 starter stamps via existing _wait_for, then asserts exactly 2 with stamp diagnostics. Evidence: focused node 5/5 green serial; whole module 8/8 serial; SASE_PYTEST_WORKERS=2 lane 8/8; sase tool run check 57289fda (triage pass, exited_zero) green under load1 5-8. No sase-core change (test sync only). sase-1vw left for the parent epic land agent per plan.

## Dependencies

- **Depends on:** [sase-1vy.4](sase-1vy.4.md) ✓ · ⧖ 2026-11-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vy.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vy.5.md) | [sase-1vy.5](sase-1vy.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4c9ccea`](https://github.com/sase-org/sase/commit/4c9ccea4b2b63d9d7af6aadd3ac751575860c55e) | fix(tool): wait for holder children before measuring admission overlap | [sase-1vy.5](sase-1vy.5.md) | 2026-11-28 07:44:29 EST |
