# Bead: sase-ns.6.3 — Make bead-work forced-reuse cleanup all-or-nothing

[Bead Pages](../README.md) / [sase-ns.6](sase-ns.6.md) / sase-ns.6.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ns.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.land.md) · **Assignee:** `sase-ns.6.3` · **Size:** medium
**Created:** 2026-08-16 21:02:35 EDT · **Closed:** 2026-08-16 21:26:22 EDT
**Plan:** [202608/task\_backlog\_top5.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_backlog_top5.md)

## Description

bead_work_atomic_cleanup: task bead sase-mt. Stop `sase bead work` from wiping some forced-reuse targets and then aborting, which silently leaves an epic with neither its old agents nor new ones.

## Notes

[2026-08-17T01:26:22Z · sase-ns.6.3] Made bead-work forced-reuse cleanup all-or-nothing: verify all destructive targets before wiping any (TOCTOU on a later target no longer leaves earlier targets wiped), and a genuine mid-wipe failure now names which owners were already wiped so the epic isn't silently left agentless. Added tests/test_bead/test_cli_work_cleanup_apply.py (3 tests) covering verify-before-wipe ordering, partial-wipe-failure messaging, and first-target-failure has no stale claim. Verified: new tests + existing cleanup/confirm suites (17 passed), ruff+mypy clean on changed files, and full 'just check' (all lint gates green; test-scoped 31807 passed/11 skipped, 2 failures — test_plan_approval_actions.py::test_headless_epic_approval_submits_while_inflight_launch_holds_anchor and test_snippet_name_modal.py::test_new_trigger_returns_empty_starting_body — confirmed flaky/parallel-load-only by passing cleanly in isolation; both are unrelated to this change's files.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ns.6.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ns.6.3/README.md) | [sase-ns.6.3](sase-ns.6.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4d8d24e`](https://github.com/sase-org/sase/commit/4d8d24eef0a4eb8717dafeefa92b5d69182c468d) | fix(bead): make forced-reuse cleanup all-or-nothing | [sase-ns.6.3](sase-ns.6.3.md) | 2026-08-16 21:27:05 EDT |
