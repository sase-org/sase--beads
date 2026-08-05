# Bead: sase-fa.1 — Restore synchronous sidecar publication on the commit path

[Bead Pages](../README.md) / [sase-fa](README.md) / sase-fa.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.t4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.t4/README.md) · **Assignee:** `sase-fa.1` · **Size:** medium
**Created:** 2026-08-05 14:26:26 EDT · **Closed:** 2026-08-05 15:49:24 EDT
**Plan:** [202608/revert\_async\_sidecar\_publication.md](https://github.com/sase-org/sase--plans/blob/main/202608/revert_async_sidecar_publication.md)

## Description

commit: turn every enqueue-only writer back into an inline publisher so `sase commit`, planner approval, and the bead-store launch push perform their agents/beads/plans sidecar work before returning.

## Notes

[2026-08-05T19:47:34Z · sase-fa.1] PROPOSED FOLLOW-UP: phase `chop` must delete drain_bead_pages_publication / drain_plan_header_publication / drain_sidecar_push_publication — this phase left them in place (deviating from plan items commit.4/5/6) because src/sase/scripts/sase_chop_sidecar_publication.py still imports them, and deleting them here would have broken the tree before the chop script is removed.

[2026-08-05T19:48:19Z · sase-fa.1] PROPOSED FOLLOW-UP: two load-sensitive tests fail intermittently under `just check` parallel load but pass in isolation and in a clean full `just test` run (25785 passed) — tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout (3.6s isolated vs 38-68s under load) and tests/ace/tui/test_artifacts_files_detail.py::test_rapid_navigation_loads_only_the_final_detail; both are wall-clock-budget tests and should be made load-tolerant.

[2026-08-05T19:49:24Z · sase-fa.1] Restored synchronous sidecar publication on the commit path. workflow_publication.py: queue_sidecar_publication_step -> run_agent_publication_step, publishing inline in pre-epic order (bead pages -> revision resolve -> prompt archive -> plan header -> agent hood), with the loud-failure contract back (FAILED on unresolvable revision, on an exception out of publish_committed_agent_hood, and on error-without-queued-or-skip, each with a 'sase commit --resume' hint); _print_publications_lane_status dropped and the deferred-message wording restored. workflow.py renamed the step/method. commit_publication.py: publish_committed_agent_hood restored as the exported enqueue-then-drain composition (the shim from tests/agents_sync/commit_publication_fixtures.py, now deleted); enqueue_committed_agent_publication removed and resolve_sidecar_publication_target privatized per symvision. bead_pages/publication.py: publish_committed_bead_pages restored over _publish_bead_lineage, mark_committed_bead_pages deleted. plan_header_refresh.py: mark_committed_plan_header and _canonical_plan_ref deleted. _commit_store.py: the SDD_STORAGE_SIDECAR_REPOS/sidecar_role enqueue short-circuit removed so sidecar stores push again. axe/run_agent_exec_plan_accept.py: direct publish_prompt_archive call restored with agent_artifacts_dir/prompt_content/plan_ref/prompt_name/yyyymm, returning outcome.prompt_path. cli_work_from_plan_store.push_store_after_launch kept its sdd_commit_targets loop (verified it resolves the beads store) and is now pinned by a test asserting the beads sidecar is pushed synchronously. Verified: new tests/test_commit_publication_inline.py acceptance test drives run_agent_publication_step over real beads/plans/agents sidecar git repos with a full footer and asserts the rendered lineage, rewritten plan header, agent page and prompt archive all reached their remotes and the outbox is empty when the step returns; new tests for the FAILED+--resume paths (unqueueable error and raised exception) and the queued-warning-but-OK path; resume test asserts each publisher runs once. Reverted the queue-era test rewrites in test_bead_page_publication, test_cli_mutation_push, test_sdd_commit_store, test_commit_workflow_checkpointing, test_axe_run_agent_exec_plan_followup_approvals. just lint clean (ruff, mypy 2745 files, symvision, toobig); full just test green (25785 passed, 7 skipped). Two wall-clock-budget tests flake only under just check's parallel load - noted as a follow-up.

## Dependencies

- **Blocks:** [sase-fa.2](sase-fa.2.md) ✓ · ⧖ 2026-08-05
- **Blocks:** [sase-fa.5](sase-fa.5.md) ✓ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fa.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fa.1/README.md) | [sase-fa.1](sase-fa.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`de78052`](https://github.com/sase-org/sase/commit/de7805278926e3a9abd97b475afca158363d7ffc) | fix: publish sidecar work inline on the commit path | [sase-fa.1](sase-fa.1.md) | 2026-08-05 15:51:02 EDT |
