# Bead: sase-17m.4.1.3 — Remaining agent package runtime identifiers

[Bead Pages](../README.md) / [sase-17m.4.1](sase-17m.4.1.md) / sase-17m.4.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.4.md) · **Assignee:** `sase-17m.4.1.3` · **Size:** medium
**Created:** 2026-09-24 13:32:31 EDT · **Closed:** 2026-09-24 16:29:30 EDT
**Plan:** [202609/agent\_session\_runtime\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_runtime_cutover.md)

## Description

agent-runtime: rename the family-concept identifiers, comments, and messages left in src/sase/agent/ after the attach and names phases. That covers launch_executor, launch_validation, detached_child, multi_prompt_launch_execution, launch_request_*, launch_hold_preview, wait_watch internals, and relaunch_prompt internals. User-facing syntax and wait -j output values are left to later phases.

## Notes

[2026-09-24T20:29:17Z · sase-17m.4.1.3] PROPOSED FOLLOW-UP: Repair the existing ACE mypy errors in _agent_detail_display.py, _agent_detail_state.py, command_line/input.py, and command_line/screen.py; they remain after this phase’s restart-render import fix and keep just check red.

[2026-09-24T20:29:30Z · sase-17m.4.1.3] Renamed remaining agent-runtime family-concept identifiers across detached successor spawning, restart/relaunch handling, wait-watch internals, request/hold paths, and their test coverage. Verified just install; just fix; focused runtime tests (detached child, durable launch context, restart/relaunch, wait CLI/watch/live, running snapshot, and launch validation); and sase bead epic-symbols (no entries). sase tool run check now passes formatting, keep-sorted, Ruff, and this phase’s mypy paths; its remaining 15 ACE mypy errors are unrelated and recorded as a follow-up.

## Dependencies

- **Depends on:** [sase-17m.4.1.2](sase-17m.4.1.2.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17m.4.1.4](sase-17m.4.1.4.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.4.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.3/README.md) | [sase-17m.4.1.3](sase-17m.4.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`44ec3e6`](https://github.com/sase-org/sase/commit/44ec3e62d3d94851cc4a01abc03ba1a161f72e05) | refactor(agent-session): rename agent runtime identifiers (sase-17m.4.1.3) | [sase-17m.4.1.3](sase-17m.4.1.3.md) | 2026-09-24 16:31:11 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.4.1.3][1] | Confirm assigned phase closure and recorded verification after completion | 2 |
| read-by | [agent:sase-17m.4.1.8][2] | Check PROPOSED FOLLOW-UP notes from earlier phases | 1 |
| read-by | [agent:sase-17m.4.1.land][3] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.3/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.8/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.land/README.md

<!-- sase:referenced-by:end -->
