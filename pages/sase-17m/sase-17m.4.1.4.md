# Bead: sase-17m.4.1.4 — Axe, monitor, gate, shell, and bead lanes

[Bead Pages](../README.md) / [sase-17m.4.1](sase-17m.4.1.md) / sase-17m.4.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17m.4.md) · **Assignee:** `sase-17m.4.1.4` · **Size:** medium
**Created:** 2026-09-24 13:32:32 EDT · **Closed:** 2026-09-24 17:08:08 EDT
**Plan:** [202609/agent\_session\_runtime\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_runtime_cutover.md)

## Description

lanes: rename family-concept identifiers, constants (GATE_FAMILY_ROLE, MONITOR_FAMILY_ROLE, spawn_family_successor), comments, and messages in axe, monitor, monitor_state.py, gate_shell, plan_shell, question_shell, notification_gates, sudo, runner_slots (both trees), dispatch, shells, and bead, plus their tests.

## Notes

[2026-09-24T21:07:40Z · sase-17m.4.1.4] PROPOSED FOLLOW-UP: pre-existing mypy failures (16 errors in 5 untouched ACE files: _agent_detail_display.py, _agent_detail_state.py, _launch_prompt_inputs.py, command_line/input.py, command_line/screen.py) reproduce identically on the clean base tree and block `sase tool run check`; needs a tracking task bead

[2026-09-24T21:07:51Z · sase-17m.4.1.4] PROPOSED FOLLOW-UP: core-contract must flip the "family_name" successor-evidence keys in gate_shell/handoff.py collect_successor_evidence (sent to Rust decide_gate_followup; marked with core-contract legacy comment)

[2026-09-24T21:08:08Z · sase-17m.4.1.4] lanes rename done: GATE/MONITOR_AGENT_SESSION_ROLE, spawn_shell_agent_session_successor, create_agent_session_shell_member, ShellStateConfig.agent_session_role, agent-session records/members/metadata identifiers + prose across axe/monitor/gate_shell/shells/bead/dispatch/notification_gates/plan_question shells; 4 test files renamed to agent-session names; ruff/fmt/keep-sorted pass; targeted suites pass (80+158+51 tests); full check blocked only by 16 pre-existing mypy errors in 5 untouched ACE files reproducing identically on clean tree; epic-symbols clean

## Dependencies

- **Depends on:** [sase-17m.4.1.3](sase-17m.4.1.3.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17m.4.1.5](sase-17m.4.1.5.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.4.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.4/README.md) | [sase-17m.4.1.4](sase-17m.4.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e747d75`](https://github.com/sase-org/sase/commit/e747d7548dad59497f8505c31cd27aa557a7551b) | refactor(lanes): rename family-concept identifiers to agent-session terminology | [sase-17m.4.1.4](sase-17m.4.1.4.md) | 2026-09-24 17:10:06 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.4.1.4][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-17m.4.1.8][2] | Check PROPOSED FOLLOW-UP notes from earlier phases | 1 |
| read-by | [agent:sase-17m.4.1.land][3] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.4/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.8/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.land/README.md

<!-- sase:referenced-by:end -->
