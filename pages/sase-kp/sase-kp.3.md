# Bead: sase-kp.3 — Monitor member lifecycle and supervisor process

[Bead Pages](../README.md) / [sase-kp](README.md) / sase-kp.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yy](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yy/README.md) · **Assignee:** `sase-kp.3` · **Size:** medium
**Created:** 2026-08-12 17:28:44 EDT · **Closed:** 2026-08-12 19:21:13 EDT
**Plan:** [202608/sase\_monitor.md](https://github.com/sase-org/sase--plans/blob/main/202608/sase_monitor.md)

## Description

engine-run: create the monitor family member, run and stream the monitored command from a detached supervisor, enforce the timeout, own the workspace claim, and write the terminal marker.

## Notes

[2026-08-12T23:20:58Z · sase-kp.3] PROPOSED FOLLOW-UP: `just lint`/`just check` fail at the patch/stitch terminology gate — tools/audit_patch_stitch_terminology flags 3 unclassified "changespec" defects in tests/test_validate_sase_core_rs_tool.py:430,504 and tools/validate_sase_core_rs:606. Confirmed pre-existing on a clean master checkout (unrelated to sase-kp.3); the audit-contract classification for these three sites needs to be added or the strings reclassified.

[2026-08-12T23:21:13Z · sase-kp.3] Implemented src/sase/monitor/ (models, naming, member, store, supervise, start, output, __init__) plus the plan_chain monitor-suffix parsing/canonicalization changes, and tests/monitor/ (53 tests). Verified: just lint (ruff, mypy, keep-sorted, pyscripts, test-waits, changelog, symvision, toobig all pass; patch/stitch terminology gate fails but confirmed pre-existing on clean master, unrelated — filed as PROPOSED FOLLOW-UP); just validate and validate-committed-plans pass; tests/monitor/ + tests/test_plan_chain_roles.py + tests/test_agent_artifact_marker_path_passing_audit.py = 53 passed; previously-flaky test_start_monitor_promotes_a_bare_lane_and_runs_to_completion reran 5x clean; full just test-scoped = 9165 passed, 0 failed.

## Dependencies

- **Depends on:** [sase-kp.1](sase-kp.1.md) ✓ · ⧖ 2026-08-12
- **Depends on:** [sase-kp.2](sase-kp.2.md) ✓ · ⧖ 2026-08-12
- **Blocks:** [sase-kp.4](sase-kp.4.md) ✓ · ⧖ 2026-08-12
- **Blocks:** [sase-kp.5](sase-kp.5.md) ✓ · ⧖ 2026-08-12
- **Blocks:** [sase-kp.7](sase-kp.7.md) ✓ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-kp.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-kp.3/README.md) | [sase-kp.3](sase-kp.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b32167c`](https://github.com/sase-org/sase/commit/b32167c31bca2e28d6dfbd6e8cd5dd86a07a883f) | feat(monitor): add monitor member lifecycle and supervisor process | [sase-kp.3](sase-kp.3.md) | 2026-08-12 19:21:48 EDT |
