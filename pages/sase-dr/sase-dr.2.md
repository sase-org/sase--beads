# Bead: sase-dr.2 — Public CLI, task sizing, and model routing

[Bead Pages](../README.md) / [sase-dr](README.md) / sase-dr.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rl](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rl/README.md) · **Assignee:** `sase-dr.2` · **Size:** medium
**Created:** 2026-08-01 17:10:50 UTC · **Closed:** 2026-08-01 18:27:53 UTC
**Plan:** [202608/task\_bead\_plus\_one.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_bead_plus_one.md)

## Description

cli-routing: expose the +1 workflow, require sizes on every task creation path, and replace the sizeless task model alias with phase-size routing.

## Notes

[2026-08-01T18:14:19Z · sase-dr.2] PROPOSED FOLLOW-UP: Repair stale ACE admin-center test helper import — tests/ace/tui/test_admin_center_selection_resume.py cannot collect because _patch_store_loader is no longer exported by tests.ace.tui.test_tasks_pane on current master.

[2026-08-01T18:17:04Z · sase-dr.2] PROPOSED FOLLOW-UP: Reconcile saved-query picker tests with the current Artifacts tab map — seven tests in tests/ace/tui/modals/test_saved_query_picker.py expect key 5 to select prs, but current master leaves the subtab on files (and 2* opens the picker outside PRs).

[2026-08-01T18:21:54Z · sase-dr.2] PROPOSED FOLLOW-UP: Triage current Symvision unused-public baseline — just lint reports BulkUnreadToggleResult, PreparedPromptArchive, clean_prompt_archive_worktree, commit_prompt_archive_if_dirty, find_pending_task_triage, prune_prompt_artifact_pool, and resolve_task_launch_cwd on unchanged master code.

[2026-08-01T18:27:53Z · sase-dr.2] Implemented public task +1 CLI with attribution, refs, idempotent totals, canonical commit/push handling, and write guarding; required explicit task sizes in CLI and ACE; removed the shipped task_worker alias and routed tasks through phase-size models with legacy small fallback plus large/xlarge #plan. Verified 405 changed-surface tests, strict docs build, formatting, Ruff, mypy, script/changelog validation, and git diff hygiene. just check reaches the unrelated pre-existing Symvision findings recorded above.

[2026-08-01T18:28:56Z · sase-dr.2] Verified 405 changed-surface tests, strict docs build, formatting, Ruff, mypy, structure, and diff hygiene; repository-wide just check reaches only unrelated pre-existing Symvision findings recorded as proposed follow-ups.

## Dependencies

- **Depends on:** [sase-dr.1](sase-dr.1.md) ✓
- **Blocks:** [sase-dr.4](sase-dr.4.md) ◐
- **Blocks:** [sase-dr.5](sase-dr.5.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-dr.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-dr.2/README.md) | [sase-dr.2](sase-dr.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`767852a`](https://github.com/sase-org/sase/commit/767852ac977c63beae5e2e994fac7db5f15142c1) | feat(beads)!: add task promotion and size-based routing | [sase-dr.2](sase-dr.2.md) | 2026-08-01 18:30:57 |
