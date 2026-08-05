# Bead: sase-fb.2 — Refuse to evict a workspace sidecar clone that holds unpublished bead commits

[Bead Pages](../README.md) / [sase-fb](README.md) / sase-fb.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.t9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.t9/README.md) · **Assignee:** `sase-fb.2` · **Size:** medium
**Created:** 2026-08-05 15:46:04 EDT · **Closed:** 2026-08-05 16:24:23 EDT
**Plan:** [202608/bead\_close\_publication\_loss.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_close_publication_loss.md)

## Description

evict: teach the launch-time workspace bead safety net about the sidecar-repos layout and wire it into the eviction path so `clear_workspace_repos` can never trash a `sase--beads` clone with unpushed canonical bead commits.

## Notes

[2026-08-05T20:24:00Z · sase-fb.2] PROPOSED FOLLOW-UP: tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout is load-sensitive — under a full parallel `just test` run it reproducibly fails with 2 of its workers hitting "lock_timeout: timed out after 12000ms waiting for exclusive lock", while passing in isolation in ~4s; the 12s SASE_BEAD_MUTATION_LOCK_TIMEOUT budget is too tight for 36 seeded beads under xdist contention. Unrelated to the evict phase (bead mutation lock, not workspace eviction).

[2026-08-05T20:24:23Z · sase-fb.2] evict phase implemented in src/sase/axe/runner_workspace.py + src/sase/axe/run_workflow_runner.py, with regression tests in tests/test_bead/test_workspace_sidecar_bead_eviction.py.

What changed:
1. Sidecar-layout discovery: new _workspace_bead_store_dirs() finds the sidecar-repos stores at <workspace>/sase/repos/beads (split-beads clone root) and <workspace>/sase/repos/plans/beads (combined sidecar), in addition to the existing <repo_root>/beads and in-tree layouts. _beads_dir_belongs_to_repo was replaced by _bead_store_repo_root(), which resolves each store's OWN git root via bead_store_git_root and accepts it when it is the workspace repo or a clone nested inside the workspace — previously the guard returned early and protected nothing for the sidecar layout. Per-store publish/rescue logic moved into _protect_bead_store() so the recovery ref is created in the store's own repo, not the primary workspace repo.
2. Eviction barrier: prepare_launch_workspace_repos now runs the guard with refuse_on_unpublished=True BEFORE clear_workspace_repos() (only for workspace_num > 1, the only case that evicts). On unpublished commits it publishes synchronously first; if commits remain it retains the recovery ref and raises the new WorkspaceBeadEvictionRefused instead of warning and proceeding, so the sase/repos rename-into-.sase/trash never happens. run_workflow_runner catches it and fails workspace prep cleanly; run_agent_runner_setup already treats a raise as fatal. prepare_workspace keeps its original warn-and-proceed behavior (refuse_on_unpublished defaults to False).

Verified:
- New tests: eviction of a sidecar clone with an unpublished bead commit raises WorkspaceBeadEvictionRefused, the clone is neither trashed nor re-cloned (no .sase/trash, HEAD unchanged, ensure_workspace_sdd_clone never called), and a recovery ref pointing at the commit exists and is named in the stderr diagnostic; a fully published sidecar clone is evicted and re-cloned normally with no publish attempt; _workspace_bead_store_dirs covers both sidecar layouts and rejects a store-less directory.
- Confirmed the barrier test fails against the pre-change code (with the guard call disabled, test_eviction_refuses_to_trash_unpublished_sidecar_bead_commits fails while the others pass).
- just lint clean (ruff, mypy, symvision, toobig). just test: 25799 passed, 1 pre-existing load-sensitive failure in test_concurrent_bead_mutations_wait_past_the_old_lock_timeout (bead mutation lock timeout under xdist load; passes in isolation, unrelated to this phase) — recorded as a PROPOSED FOLLOW-UP note on this bead.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fb.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fb.2/README.md) | [sase-fb.2](sase-fb.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d1b6f01`](https://github.com/sase-org/sase/commit/d1b6f01a9e1ae04bb912cb17f360aaafd6b9df25) | fix(axe): refuse to evict workspace sidecar clones holding unpublished bead commits | [sase-fb.2](sase-fb.2.md) | 2026-08-05 16:25:27 EDT |
