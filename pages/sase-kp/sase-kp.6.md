# Bead: sase-kp.6 — sase monitor command group

[Bead Pages](../README.md) / [sase-kp](README.md) / sase-kp.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yy](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yy/README.md) · **Assignee:** `sase-kp.6` · **Size:** medium
**Created:** 2026-08-12 17:29:21 EDT · **Closed:** 2026-08-13 06:35:16 EDT
**Plan:** [202608/sase\_monitor.md](https://github.com/sase-org/sase--plans/blob/main/202608/sase_monitor.md)

## Description

cli: add `sase monitor start|stop|list|show` with multi-format output, duration parsing, and monitor id resolution.

## Notes

[2026-08-13T10:28:08Z · sase-kp.6] PROPOSED FOLLOW-UP: tests/monitor/test_monitor_start.py::test_start_monitor_tears_down_the_member_when_the_supervisor_cannot_spawn deterministically fails once "today" != 2026-08-12 — it hardcodes the starter timestamp "20260812120000" and globs Path(starter_dir).parent (the Aug-12 day shard) for the new member, but create_followup_artifacts stamps the new member with the real current timestamp, landing it in a different day shard when the date has rolled over.

[2026-08-13T10:28:31Z · sase-kp.6] PROPOSED FOLLOW-UP: tests/monitor/test_monitor_start.py::test_start_monitor_promotes_a_bare_lane_and_runs_to_completion is intermittently flaky (~2/15 in a local repro, reproduces on origin/master too, unrelated to sase-kp.6) — it asserts get_claimed_workspaces(project_file) == [] immediately after _wait_for_done observes monitor_state=="completed", but supervise.py _finish_monitor() writes the done marker before calling _release_claim_and_notify(), leaving a race window where the claim can still be held when the assertion runs.

[2026-08-13T10:28:47Z · sase-kp.6] PROPOSED FOLLOW-UP: `just _lint-patch-stitch-terminology` fails on a clean origin/master checkout (unrelated to sase-kp.6) — tools/audit_patch_stitch_terminology flags 3 unclassified "changespec" defects at tests/test_validate_sase_core_rs_tool.py:430, :504, and tools/validate_sase_core_rs:606.

[2026-08-13T10:35:16Z · sase-kp.6] Implemented sase monitor start|stop|list|show (+hidden _supervise) in new parser_monitor.py/monitor_handler.py/monitor_render.py, modeled on the task trio; registered in parser.py, parser_full_registrars.py, entry.py. Extended the monitor engine (models.py: MonitorRefError, MonitorRecord.elapsed_seconds; naming.py: short_monitor_id; store.py: list_monitors, resolve_monitor_ref, project-optional scanning) since the cli phase's own spec calls out 'monitor id resolution' as its responsibility. Routed the monitor supervisor spawn (start.py) through the new 'sase monitor _supervise' CLI entrypoint (matching the plan's vocabulary table) instead of the old direct 'python -m sase.monitor.supervise' invocation, and renamed supervise.py's _run_supervisor to public run_supervisor to satisfy symvision's no-cross-file-private-import rule. Verified: full new/extended test suite green (parser help/wiring, list/show/start/stop handlers incl. real-subprocess end-to-end start+stop flows, JSON envelope stability, markdown table output, --follow streaming); just fmt/ruff/mypy/symvision/toobig/validate/validate-committed-plans clean; just test-scoped green except two pre-existing, confirmed-unrelated flakes in tests/monitor/test_monitor_start.py (already on origin/master, reproduced without my changes) noted as PROPOSED FOLLOW-UP. Caught and fixed a real dest-collision bug via manual CLI smoke test: -c/--command's default dest clashed with the root parser's dest="command", breaking entry.py's top-level routing for real invocations (invisible to handler-level unit tests) -- added dest="monitor_command" plus a parser-level and an entry.main()-level regression test.

[2026-08-13T10:35:59Z · sase-kp.6] Implemented sase monitor start|stop|list|show CLI (parser_monitor.py, monitor_handler.py, monitor_render.py) wired into parser.py/parser_full_registrars.py/entry.py; extended engine layer (list_monitors, resolve_monitor_ref, MonitorRefError, short_monitor_id, elapsed_seconds); routed supervisor spawn through sase monitor _supervise; fixed -c/--command dest collision with root command dest; full test/lint/mypy/symvision gates green modulo two pre-existing unrelated flakes recorded as PROPOSED FOLLOW-UP notes.

## Dependencies

- **Blocks:** [sase-kp.10](sase-kp.10.md) ✓ · ⧖ 2026-08-12
- **Depends on:** [sase-kp.4](sase-kp.4.md) ✓ · ⧖ 2026-08-12
- **Depends on:** [sase-kp.5](sase-kp.5.md) ✓ · ⧖ 2026-08-12
- **Blocks:** [sase-kp.8](sase-kp.8.md) ◐ · ⧖ 2026-08-12
- **Blocks:** [sase-kp.9](sase-kp.9.md) ✓ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-kp.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-kp.6/README.md) | [sase-kp.6](sase-kp.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8340b45`](https://github.com/sase-org/sase/commit/8340b457af2d9b6f3f8348bdf8057ab41077c9ef) | feat(monitor): add sase monitor start\|stop\|list\|show CLI | [sase-kp.6](sase-kp.6.md) | 2026-08-13 06:36:37 EDT |
