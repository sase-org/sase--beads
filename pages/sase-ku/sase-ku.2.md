# Bead: sase-ku.2 — Rebuild the supervisor's stream and wait loop

[Bead Pages](../README.md) / [sase-ku](README.md) / sase-ku.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-kp.land.w1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-kp.land.w1.md) · **Assignee:** `sase-ku.2` · **Size:** medium
**Created:** 2026-08-13 09:02:34 EDT · **Closed:** 2026-08-13 09:28:13 EDT
**Plan:** [202608/monitor\_hardening.md](https://github.com/sase-org/sase--plans/blob/main/202608/monitor_hardening.md)

## Description

stream: replace the blocking line-oriented `readline()` loop with a pipe-backed bounded writer plus a `child.poll()` tick loop, guard the whole supervisor lifecycle in `try`/`finally`, make every reader rotation-aware, and pass the monitor workflow to `release_workspace()`.

## Notes

[2026-08-13T13:27:21Z · sase-ku.2] PROPOSED FOLLOW-UP: Patch/stitch terminology audit has pre-existing unclassified changespec tokens — `just check` fails in tests/test_validate_sase_core_rs_tool.py lines 430/504 and tools/validate_sase_core_rs line 606, none touched by this phase.

[2026-08-13T13:28:13Z · sase-ku.2] Implemented pipe-backed monitor stream loop and rotation-aware readers. Verified focused pytest suite: tests/logs/test_pipe.py, task log bounds/tail tests, tests/monitor/test_monitor_output.py, tests/monitor/test_monitor_supervise.py, tests/main/test_monitor_handler_show.py, tests/agent/test_artifact_files_cache.py. just check passed fmt/ruff/mypy/test-waits/changelog and failed only the pre-existing patch/stitch terminology audit noted as PROPOSED FOLLOW-UP.

[2026-08-13T13:29:53Z · sase-ku.2] focused monitor/log tests passed; just check passed through fmt, ruff, mypy, test-waits, and changelog gates, then failed on pre-existing patch/stitch terminology audit entries recorded as PROPOSED FOLLOW-UP

## Dependencies

- **Blocks:** [sase-ku.3](sase-ku.3.md) ◐ · ⧖ 2026-08-13
- **Blocks:** [sase-ku.6](sase-ku.6.md) ◐ · ⧖ 2026-08-13
- **Blocks:** [sase-ku.7](sase-ku.7.md) ◐ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ku.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ku.2/README.md) | [sase-ku.2](sase-ku.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`afa8178`](https://github.com/sase-org/sase/commit/afa8178ceec76e7fbbe94110c3af9ed4b7ba6d39) | fix(monitor): decouple supervisor waits from output reads | [sase-ku.2](sase-ku.2.md) | 2026-08-13 09:31:19 EDT |
