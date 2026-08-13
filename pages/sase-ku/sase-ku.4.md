# Bead: sase-ku.4 — Transactional monitor start and settlement

[Bead Pages](../README.md) / [sase-ku](README.md) / sase-ku.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-kp.land.w1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-kp.land.w1.md) · **Assignee:** `sase-ku.4` · **Size:** medium
**Created:** 2026-08-13 09:02:49 EDT · **Closed:** 2026-08-13 11:12:50 EDT
**Plan:** [202608/monitor\_hardening.md](https://github.com/sase-org/sase--plans/blob/main/202608/monitor_hardening.md)

## Description

transaction: take a per-lane lock inside `start_monitor()`, hold the command behind a go barrier until the workspace claim is secured, fingerprint the request for honest idempotency, and write the terminal marker only after settlement.

## Notes

[2026-08-13T14:38:47Z · zg] CONFLICT HEADS-UP: adjacent work touched src/sase/monitor/start.py, which your 'transaction' phase rewrites.

Two small edits landed there from '.sase/artifacts/home/.sase/plans/202608/monitor_wait_resolution.md':
1. The supervisor spawn no longer discards diagnostics. stdout now goes to a new SUPERVISOR_LOG_NAME = 'supervisor.log' inside the monitor member's artifacts dir, with stderr=subprocess.STDOUT; a helper _open_supervisor_log() falls back to DEVNULL if the file cannot be opened, and the parent closes the handle in a finally. start_new_session=True, stdin=DEVNULL, and close_fds=True are unchanged. This is complementary to sase-ku.2's fix (which records the supervisor's own error in done.json) and covers the case sase-ku.2 cannot: a process that dies ABOVE run_supervisor()'s guard -- an import error, a crash in _read_meta(), an external SIGKILL. Please preserve it when you restructure the spawn behind the go barrier.
2. DEFAULT_STOP_STATUS is now DEFAULT_MONITOR_STOP_STATUS imported from src/sase/monitor_state.py, so the 'MONITORED' literal has one home. src/sase/core/dismissed_agent_completion.py imports it too.

ALSO -- your phase owns a flake I hit. tests/monitor/test_monitor_start.py::test_start_monitor_promotes_a_bare_lane_and_runs_to_completion fails under full-suite parallel load: _wait_for_done() returns the moment done.json appears, then asserts get_claimed_workspaces(project_file) == [], but _finish_monitor() writes the terminal marker BEFORE _release_claim_and_notify() runs. Observed failure: 'Left contains one more item: WorkspaceClaim(workspace_num=3, workflow=ace-monitor, ...)'. I verified this is pre-existing: it reproduces on a clean master tree with my changes stashed ('just test', 2 failures, this being one). This is exactly the 'Terminal state precedes settlement' defect your phase description names, and the kp.6 flake the epic plan already records. Writing the marker only after settlement should fix the test as written.

[2026-08-13T15:12:18Z · sase-ku.4] PROPOSED FOLLOW-UP: Fix project handler fresh-interpreter circular import — `import sase.main.project_handler` now cycles through project_aliases -> xprompt -> memory.read_log -> project_aliases and fails `tests/main/test_project_handler_list_show.py::TestListAndShow::test_project_handler_imports_in_fresh_interpreter`.

[2026-08-13T15:12:50Z · sase-ku.4] Implemented transactional monitor start/settlement. Verified .venv/bin/python -m pytest tests/main/test_monitor_handler_show.py tests/main/test_monitor_handler_stop.py tests/main/test_monitor_handler_list.py tests/main/test_monitor_handler_start.py tests/monitor -q (125 passed). Ran just check: fmt/ruff/mypy/custom lint passed and full scoped pytest reached 2700 passed/3 skipped, but failed unrelated fresh-interpreter project_handler circular import; recorded PROPOSED FOLLOW-UP on this bead.

[2026-08-13T15:14:05Z · sase-ku.4] Verified focused monitor/handler tests passed (125 passed); just check passed formatting, Ruff, mypy, and custom lint gates before failing on unrelated project-handler import-cycle test recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-ku.3](sase-ku.3.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-ku.5](sase-ku.5.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-ku.8](sase-ku.8.md) ✓ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ku.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ku.4/README.md) | [sase-ku.4](sase-ku.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a54aec6`](https://github.com/sase-org/sase/commit/a54aec6ab7f43b1d874828e3c7ca54cbb06fe160) | fix(monitor): make monitor startup transactional | [sase-ku.4](sase-ku.4.md) | 2026-08-13 11:15:44 EDT |
