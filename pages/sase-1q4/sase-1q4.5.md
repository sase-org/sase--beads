# Bead: sase-1q4.5 — The %wait target= keyword end to end

[Bead Pages](../README.md) / [sase-1q4](README.md) / sase-1q4.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5j.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5j.linker.w0.md) · **Assignee:** `sase-1q4.5` · **Size:** medium
**Created:** 2026-10-30 17:43:13 EDT
**Plan:** [202610/fork\_wait\_session\_turn\_target.md](https://github.com/sase-org/sase--plans/blob/main/202610/fork_wait_session_turn_target.md)

## Description

wait_directive: accept and validate %wait(..., target=) in the Python collector and Rust editor/typed parsers, feed the binder, round-trip it through PromptWaitDirective edits, and update docs.

## Notes

[2026-10-31T05:54:40Z · sase-1q4.5] PROPOSED FOLLOW-UP: typed-agent %wait(..., target=turn) does not pin through admission — WaitTargetWire has no target field, so typed-agent waits are stripped into LaunchUnitWire.waits and Python extract of remaining prompt cannot see target=; extend WaitTargetWire plus admission in a later phase

[2026-10-31T06:34:56Z · sase-1q4.5] PROPOSED FOLLOW-UP: tests/agents_sync/test_cli_names.py::test_repair_states_dispatches_and_reports_json NameError handle_agents_sync — already tracked by sase-1q7; reproduces on the unchanged test file, unrelated to %wait target=

[2026-10-31T06:36:00Z · sase-1q4.5] Close blocked: working-tree Justfile re-keyed wait_targets_with_descriptions onto parent epic sase-1q4 after the Rust editor suggestion path consumed WAIT_TARGETS_WITH_DESCRIPTIONS; origin/master still lists sase-1q4.5(wait_targets_with_descriptions) so sase bead close refuses. Host close after this stitch lands should succeed; the leftover check treats unconsumed upstream rows like unconsumed sibling rows.

## Dependencies

- **Blocks:** [sase-1q4.11](sase-1q4.11.md) ◐ · ⧖ 2026-10-30
- **Depends on:** [sase-1q4.4](sase-1q4.4.md) ✓ · ⧖ 2026-10-30
- **Blocks:** [sase-1q4.7](sase-1q4.7.md) ◐ · ⧖ 2026-10-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1q4.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1q4.5/README.md) | [sase-1q4.5](sase-1q4.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@80f5af4`](https://github.com/sase-org/sase-core/commit/80f5af40f4482f10187f207082249dd329cf329c) | feat(editor): parse and diagnose %wait target=session\|turn | [sase-1q4.5](sase-1q4.5.md) | 2026-10-31 02:37:20 EDT |
| sase | [`eed4ef9`](https://github.com/sase-org/sase/commit/eed4ef925b351e7aa9770dddbee969b79ec15589) | feat(macro): accept %wait(..., target=session\|turn) | [sase-1q4.5](sase-1q4.5.md) | 2026-10-31 02:38:38 EDT |
