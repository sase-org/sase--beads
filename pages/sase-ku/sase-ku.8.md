# Bead: sase-ku.8 — Close the monitor fidelity gaps

[Bead Pages](../README.md) / [sase-ku](README.md) / sase-ku.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-kp.land.w1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-kp.land.w1.md) · **Assignee:** `sase-ku.8` · **Size:** small
**Created:** 2026-08-13 09:03:17 EDT · **Closed:** 2026-08-13 11:37:57 EDT
**Plan:** [202608/monitor\_hardening.md](https://github.com/sase-org/sase--plans/blob/main/202608/monitor_hardening.md)

## Description

fidelity: print the start summary before the handoff kill, write `monitor_output_path` and `run_started_at`, and read the member's own marker files instead of re-querying the artifact index in every polling loop.

## Notes

[2026-08-13T15:37:37Z · sase-ku.8] PROPOSED FOLLOW-UP: tests/main/test_project_handler_list_show.py::TestListAndShow::test_project_handler_imports_in_fresh_interpreter fails on a clean master checkout (confirmed via git stash) with a circular import: sase.project_aliases -> sase.project_alias_prompts -> sase.xprompt -> ... -> sase.memory.read_log -> sase.project_aliases. Unrelated to the fidelity phase; surfaced while running just check.

[2026-08-13T15:37:57Z · sase-ku.8] Closed all 4 fidelity gaps from the plan: (1) reordered _handle_monitor_start() so the summary/--json envelope prints before maybe_handoff_monitor_from_agent(), which kills the runner via NoReturn kill_agent_runner_group() -- added will_handoff_monitor_to_agent_runner() predicate plus two regression tests covering the previously-unreachable handed_off=True path. (2) supervise.py now writes monitor_output_path to agent_meta.json when it opens the log; monitor_handler._output_path() and MonitorRecord already read/prefer it. (3) supervise.py now records run_started_at at the moment it spawns the child (not at member creation), so displayed runtime excludes creation/spawn latency. (4) added store.read_monitor_marker(project_name, artifacts_dir), which reads one member's agent_meta.json/done.json directly instead of a full-history index query, and switched to it in stop_monitor()'s wait loop, monitor_handler._follow_output(), and _wait_for_monitor(). Verified: just check passes (all lint gates + full-suite-escalated test-scoped run, 2678 passed) except one pre-existing, unrelated circular-import failure confirmed present on a clean master checkout via git stash (noted as PROPOSED FOLLOW-UP). New/updated tests: tests/main/test_monitor_handler_start.py, tests/main/test_monitor_handler_show.py, tests/monitor/test_monitor_store.py, tests/monitor/test_monitor_supervise.py -- all pass.

## Dependencies

- **Depends on:** [sase-ku.4](sase-ku.4.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-ku.9](sase-ku.9.md) ◐ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ku.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ku.8/README.md) | [sase-ku.8](sase-ku.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`df17a07`](https://github.com/sase-org/sase/commit/df17a078a430834d5113051d1712e54b139d97fd) | fix(monitor): close fidelity gaps between monitor output and reality | [sase-ku.8](sase-ku.8.md) | 2026-08-13 11:38:56 EDT |
