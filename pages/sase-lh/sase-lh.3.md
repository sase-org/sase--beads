# Bead: sase-lh.3 — Rename the sase task CLI command tree to sase proc

[Bead Pages](../README.md) / [sase-lh](README.md) / sase-lh.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.000](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.000.md) · **Assignee:** `sase-lh.3` · **Size:** medium
**Created:** 2026-08-13 17:19:34 EDT · **Closed:** 2026-08-13 21:04:08 EDT
**Plan:** [202608/background\_tasks\_to\_procs.md](https://github.com/sase-org/sase--plans/blob/main/202608/background_tasks_to_procs.md)

## Description

cli: rename `sase task` to `sase proc` with `task` registered as a legacy alias and facade shim modules, rename the parser/handler/render modules and the `--json` envelope key, and update the CLI help text, tests, and `docs/cli.md`.

## Notes

[2026-08-14T01:04:08Z · sase-lh.3] Verified just install; targeted proc CLI pytest suite (90 passed); just check passed.

[2026-08-14T01:19:25Z · sase-lh.3--1] Verified: just check-full completed with 1 failed / 29841 passed. The failure (tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop) is unrelated to this bead's proc CLI rename: the test file was last touched by an unrelated refactor commit (61859ebb8), and the test passes cleanly both in isolation and when run with its full test file (5 passed), confirming a pre-existing order-dependent flake, not a regression from this work.

[2026-08-14T01:19:36Z · sase-lh.3--1] PROPOSED FOLLOW-UP: Fix flaky order-dependent test — tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop fails only under full-suite just check-full runs (passes in isolation and within its own file), indicating cross-test pollution in the axe run-agent-runner test suite.

## Dependencies

- **Depends on:** [sase-lh.2](sase-lh.2.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-lh.6](sase-lh.6.md) ✓ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-lh.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-lh.3.md) | [sase-lh.3](sase-lh.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a0e9ae4`](https://github.com/sase-org/sase/commit/a0e9ae4ed310014524237059a39069cee9b7d566) | feat(cli)!: rename task command to proc | [sase-lh.3](sase-lh.3.md) | 2026-08-13 21:05:16 EDT |
