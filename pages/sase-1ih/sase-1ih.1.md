# Bead: sase-1ih.1 — Tool-run proc facts (session stamping and join tags)

[Bead Pages](../README.md) / [sase-1ih](README.md) / sase-1ih.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.43.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.43.linker.w0.md) · **Assignee:** `sase-1ih.1` · **Size:** small
**Created:** 2026-10-08 18:31:54 EDT · **Closed:** 2026-10-08 19:36:56 EDT
**Plan:** [202610/tools\_bg\_split\_tool\_run\_visibility.md](https://github.com/sase-org/sase--plans/blob/main/202610/tools_bg_split_tool_run_visibility.md)

## Description

tool-proc-facts: stamp a tool-run proc's session only when a live TUI submitted it; tag join monitors `tool-run-join:<id>` and teach the Procs pane to follow that tag.

## Notes

[2026-10-08T23:36:43Z · sase-1ih.1] PROPOSED FOLLOW-UP: symvision unused-public gate fails identically on the clean base tree (52-line baseline incl. BeadBoardSnapshot etc.; byte-identical output with and without this phase's changes) — triage as a pre-existing failure, not a phase regression

[2026-10-08T23:36:56Z · sase-1ih.1] tool-proc-facts done: submit_handoff_run stamps own_live_session_id (no latest-session fallback; resolve_session_ref untouched); join monitors tagged tool-run-join:<id> via new join_tags helper; tool_run_id_for_task falls back to join tag with owner winning (agent-jump mixin inherits it). Verified: 21 passed tests/tool/test_handoff.py (incl. 3 new session-stamping tests), full tests/tool/test_detach.py + tests/ace/tui/test_procs_pane_render.py + tests/monitor/test_monitor_join_engine.py + tests/monitor/test_monitor_join.py + tests/ace/tui/test_procs_pane.py + tests/test_sessions_registry.py + tests/test_procs_runner.py + tests/main/test_monitor_handler_start_launch.py all green; ruff check/format clean; mypy clean (5715 files). symvision fails byte-identically on clean base (pre-existing, recorded as PROPOSED FOLLOW-UP). Full just-check scoped suite exceeds the single-turn window (timed out at ~37% with all passes).

## Dependencies

- **Blocks:** [sase-1ih.3](sase-1ih.3.md) ✓ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ih.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ih.1/README.md) | [sase-1ih.1](sase-1ih.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`285da82`](https://github.com/sase-org/sase/commit/285da8234afd53ec70f46e55c9c18cbb252e486c) | feat(tool-proc): stamp sessions, tag monitor joins, follow runs in procs pane | [sase-1ih.1](sase-1ih.1.md) | 2026-10-08 19:39:18 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ih.1][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ih.1/README.md

<!-- sase:referenced-by:end -->
