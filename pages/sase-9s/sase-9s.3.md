# Bead: sase-9s.3 — Resolve the epic launch workspace without provider env vars

[Bead Pages](../README.md) / [sase-9s](README.md) / sase-9s.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9s.3` · **Size:** small
**Created:** 2026-07-26 11:20:51 UTC
**Plan:** [sase/repos/plans/202607/detached\_epic\_launch.md](https://github.com/sase-org/sase--plans/blob/main/sase/repos/plans/202607/detached_epic_launch.md)

## Description

'Phase cwd: Resolve the epic launch workspace without provider env vars' section: populate a plan gate's `project_dir` from the shared runtime-neutral env contract and let the host claim an epic launch from `agent_project_file` alone.

## Notes

Implemented runtime-neutral plan-gate project_dir resolution via PROVIDER_PROJECT_DIR_ENV_VARS/SASE_ACTIVE_PROJECT_DIR and relaxed epic launch cwd resolution to accept agent_project_file without project_dir. Added regressions for plan gates, headless epic cwd, shared epic launch cwd, and TUI tracked launch guard. Verification: just install passed; focused pytest suite passed: tests/test_plan_gates.py tests/test_plan_approval_actions.py tests/test_bead/test_epic_launch.py tests/ace/tui/test_notification_epic_launch.py. Required just check was run and failed in unrelated tests; rerunning listed nonvisual failures directly left only tests/sdd_store/test_repository_transaction.py::test_machine_managed_integration_does_not_create_rerere_cache failing, which is outside this bead's touched code.

## Dependencies

- **Blocks:** [sase-9s.5](sase-9s.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9s.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9s.3/README.md) | [sase-9s.3](sase-9s.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`657f14f`](https://github.com/sase-org/sase/commit/657f14f778c6dcaf636f9b6ec2e8a73cefd1440c) | fix: resolve epic launch workspace from shared env contract (sase-9s.3) | [sase-9s.3](sase-9s.3.md) | 2026-07-26 12:06:36 |
