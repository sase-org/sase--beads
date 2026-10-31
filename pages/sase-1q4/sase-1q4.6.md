# Bead: sase-1q4.6 — sase agent wait --target

[Bead Pages](../README.md) / [sase-1q4](README.md) / sase-1q4.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5j.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5j.linker.w0.md) · **Assignee:** `sase-1q4.6` · **Size:** small
**Created:** 2026-10-30 17:43:14 EDT
**Plan:** [202610/fork\_wait\_session\_turn\_target.md](https://github.com/sase-org/sase--plans/blob/main/202610/fork_wait_session_turn_target.md)

## Description

agent_wait_cli: add -T/--target session|turn to sase agent wait, using the shared binder to wait on one pinned turn.

## Notes

[2026-10-31T05:40:38Z · sase-1q4.6] PROPOSED FOLLOW-UP: tests/agents_sync/test_cli_names.py::test_repair_states_dispatches_and_reports_json NameError handle_agents_sync — already tracked by sase-1q7; reproduces on the unchanged test file, unrelated to wait --target

[2026-10-31T05:42:10Z · sase-1q4.6] Close blocked: local Justfile dropped sase-1q4.6 epic-symbols after wiring WaitTargetBinding/bind_wait_target; origin/master still lists those consumed rows so sase bead close refuses. Host close after this stitch lands should succeed; the leftover check treats consumed upstream rows like unconsumed sibling rows.

## Dependencies

- **Depends on:** [sase-1q4.4](sase-1q4.4.md) ✓ · ⧖ 2026-10-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1q4.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1q4.6/README.md) | [sase-1q4.6](sase-1q4.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ef4bc2b`](https://github.com/sase-org/sase/commit/ef4bc2b34a6b844fea782d6d5ccd97f35471a316) | feat(agent): add -T/--target session\|turn to sase agent wait | [sase-1q4.6](sase-1q4.6.md) | 2026-10-31 01:43:29 EDT |
