# Bead: sase-1vy.4 — Stale index-lock recovery flake under loaded scoped check (sase-1kr)

[Bead Pages](../README.md) / [sase-1vy](README.md) / sase-1vy.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1vn.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vn.land.md) · **Assignee:** `sase-1vy.4` · **Size:** large
**Created:** 2026-11-28 03:14:45 EST · **Closed:** 2026-11-28 07:04:58 EST
**Plan:** [202611/backlog\_epic\_2.md](https://github.com/sase-org/sase--plans/blob/main/202611/backlog_epic_2.md)

## Description

index-lock-flake: fix sase-1kr. Read sase-1kr and all of its notes first (7 corroborations; pairs with sase-1s4, a test that leaves a stale lock in a real checkout). Make test_run_workspace_git_command_recovers_stale_index_lock robust under the loaded scoped lane, or fix the product recovery path it guards if the flake exposes a real race. Do not close on a single green rerun; show the node green across repeated loaded runs. Run sase tool run check, then close sase-1kr and the phase bead.

## Notes

[2026-11-28T12:04:58Z · sase-1vy.4] Implemented deterministic owner-probe injection at the imported executor seams for core workspace commands, agent reverts, commit finalization, dev-update reporter/capture/streaming, bare-Git initialization, and managed sidecar sync. The helper still invokes the public retry executor and Rust policy, validates every observed lock/Git-dir/worktree path stays inside the temporary repo, and exposes probe evidence. Direct integration tests now use explicit absent-owner facts for removal and churn identity coverage; young bare-Git and managed-sync fixtures are aged with age_git_index_lock. Workspace caller tests prove absent ownership permits real staging/removal while active and permission-denied/incomplete ownership preserves the same lock contents and fails.

Focused pytest: 100 passed in 9.93s across changed caller modules, git_lock_retry, and git_lock_observe; the genuine open-descriptor owner test passed without injected observations.

Contention: SASE_CONTENTION_CPUS=0,1; SASE_CONTENTION_WORKERS=8; SASE_CONTENTION_REPEAT=5; elapsed 126.7s. Selection: tests/test_sase_utils.py::test_run_workspace_git_command_recovers_stale_index_lock; tests/test_sase_utils.py::test_workspace_git_lock_owner_facts_control_stale_lock_recovery; tests/ace/test_revert_agent_execute.py::test_revert_git_runner_recovers_stale_index_lock; tests/llm_provider/test_commit_finalizer_auto_sdd_status.py::test_auto_commit_git_runner_recovers_stale_index_lock; tests/ace/tui/test_session_proc_reporter_git_lock.py; tests/test_bare_git_init.py::TestInitBareGitProject::test_git_runner_removes_persistent_index_lock_after_retries; tests/test_bead/test_sync_remote_worker.py::test_managed_sync_worker_converges_sidecar_store_mutations; tests/test_git_lock_recovery_integration.py. Per-node tally: 5/5 passed for each selected node (19 nodes per repeat, 95 executions total, zero failures), including workspace owner cases absent/active/incomplete.

sase tool run check ToolRun da5427b19d524e135897e85ef0b3f20a succeeded, exit 0, 478.565s; all check stages passed, including scoped tests (105/6007 selected). Its SASE validation output also recorded the expected linked sase-core 0.45.0 versus published pin 0.44.2 diagnostic; no core policy or pin change was needed.

sase bead epic-symbols sase-1vy.4 reported no epic symbols. Closed only assigned phase sase-1vy.4 as authorized.

## Dependencies

- **Depends on:** [sase-1vy.3](sase-1vy.3.md) ✓ · ⧖ 2026-11-28
- **Blocks:** [sase-1vy.5](sase-1vy.5.md) ✓ · ⧖ 2026-11-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vy.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vy.4.md) | [sase-1vy.4](sase-1vy.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`53acb95`](https://github.com/sase-org/sase/commit/53acb952ef758d42bffd592857c76183135d6e5c) | test(git-lock): make stale-lock caller tests deterministic | [sase-1vy.4](sase-1vy.4.md) | 2026-11-28 07:07:56 EST |
