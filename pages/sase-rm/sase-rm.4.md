# Bead: sase-rm.4 — Make research publication and family handoffs collision-safe

[Bead Pages](../README.md) / [sase-rm](README.md) / sase-rm.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08u](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08u.md) · **Assignee:** `sase-rm.4` · **Size:** large
**Created:** 2026-08-20 14:47:52 EDT · **Closed:** 2026-08-20 17:04:08 EDT
**Plan:** [202608/task\_backlog\_closeout.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_backlog_closeout.md)

## Description

successor_publication: eliminate research-output and artifact-directory collisions, drain stalled publication requests, reuse the successor engine, and stabilize pipe-family allocation.

## Notes

[2026-08-20T21:03:36Z · sase-rm.4] Close-ready evidence for successor_publication.

- sase-m0: Cause was unparameterized parallel #research children choosing names in the same shared month directory. Changed linked plugin files src/sase_research_artifacts/xprompts/research.md and src/sase_research_artifacts/xprompts/research_swarm.md so #research accepts an optional report_target, writes exactly $(sase repo path research --ensure)/$(date +%Y%m)/<target>, creates parents, and fails visibly instead of overwriting if the target exists. research_swarm now passes deterministic member-qualified targets research.{@1}.cdx.md and research.{@1}.cld.md. Verification: linked plugin .venv/bin/pytest tests/test_xprompt_loading.py -q passed 10 tests; linked plugin just check passed ruff, mypy, and pytest 35 passed / 4 deselected.

- sase-p0: Cause was deterministic research-hood publication format failures not being treated as terminal candidates, leaving requests unable to leave the active queue shape. Changed src/sase/agents_sync/commit_publication_transaction.py so repeated AgentsSyncFormatError preparation failures carry terminal_reason, not only the one exact no-publishable-runs string. Added tests/agents_sync/test_commit_publication_queue.py coverage for the research hood invalid relationships error: aged attempts=0 request advances to attempts=1 on first failure, retires with terminal_reason on the repeated identical failure, disappears from the active queue, and doctor recommends sase agent sync --drop-retired instead of retry-quarantined. Verification: primary focused suite passed 53 tests including this lifecycle test.

- sase-pb: Cause was create_followup_artifacts using create_artifacts_directory without a reserved timestamp, so two in-process handoffs in one wall-clock second shared one artifacts dir and overwrote agent_meta.json. Changed src/sase/axe/run_agent_helpers_artifacts.py to reserve one timestamp with reserve_launch_timestamp_batch(1) and pass it into create_artifacts_directory. Added tests/test_axe_run_agent_helpers_artifacts.py regression that freezes generate_timestamp, creates two genuine follow-up artifact dirs, and verifies 20260820161407 / 20260820161408 plus both metas, role_suffixes, relationships, workspace_dir, and workspace_num. Verification: primary focused suite passed 53 tests.

- sase-pc: Cause was plan feedback still hand-rolling the successor sequence rather than using continue_as_successor. Changed src/sase/axe/run_agent_successor.py to support a before_create callback, and changed src/sase/axe/run_agent_exec_plan.py to assemble the feedback prompt before the engine call, delegate via SuccessorRequest suffix_template=--plan-@, preserve relationship fields, fallback token, Full feedback prompt artifact, promotion path, and question_base_prompt ordering, and retain followup_agent_name in workflow metadata before artifact creation. Added tests in tests/axe/test_run_agent_successor.py and tests/test_axe_run_agent_exec_plan_followup_questions.py for callback order, unnamed fallback --plan-0, metadata-before-create including followup_agent_name, repeated feedback rounds, and prompt artifact persistence. Verification: primary focused suite passed 53 tests.

- sase-r2: Cause was the default pipe E2E flake shape being sensitive to repeated family/workspace transitions and artifact timestamp collision. Added tests/axe/test_run_agent_exec_pipe.py coverage for two real handle_pipe_marker transitions under one frozen clock with real create_followup_artifacts and prompt artifact writes, verifying unique dirs, fork prompts, piped_from, pipe_depth, family, workspace_dir, and workspace_num. Re-ran tests/fakey/test_pipe_e2e.py::test_default_pipe_creates_family_member_with_fork_and_shared_workspace in the focused suite, and before the final metadata tweak ran the exact node three consecutive times in isolation with all three passing. Verification: primary focused suite passed 53 tests.

Overall verification: just install completed in both repositories. Linked plugin focused tests passed 10 and linked plugin just check passed. Primary focused command `.venv/bin/pytest tests/test_axe_run_agent_helpers_artifacts.py tests/axe/test_run_agent_successor.py tests/test_axe_run_agent_exec_plan_followup_questions.py tests/agents_sync/test_commit_publication_queue.py tests/axe/test_run_agent_exec_pipe.py::test_repeated_default_pipe_transitions_reserve_unique_artifacts tests/fakey/test_pipe_e2e.py::test_default_pipe_creates_family_member_with_fork_and_shared_workspace -q` passed 53 tests after the final metadata allow-list edit. Primary just check was run twice: the first run passed static gates, escalated to the full suite because of core-identity-changed, and failed one unrelated directive-completion node after 35402 passed / 13 skipped; the direct node rerun also failed. After reopening the linked sase-core repo with sase repo open, the direct node still failed. The final just check rerun after the metadata edit passed setup, fmt, keep-sorted, ruff, and mypy, then failed at lint (feature flags) because closed flag bead sase-rk still has a surviving admin_center_config_hub definition in this older checkout.

PROPOSED FOLLOW-UP: just check is currently blocked before tests by the closed flag bead sase-rk while this checkout still contains admin_center_config_hub in src/sase/feature_flags/registry.py, src/sase/config/sase.schema.json, docs/configuration.md, and related ACE tests/actions. This appears to be concurrent backlog work: sase-rk was closed at 2026-08-20T20:17:41Z with a note that the flag was removed, but this workspace HEAD f136f4fbd still predates that removal. Rebase or land the sase-rk removal into workspaces before treating this phase diff as a flag regression.

PROPOSED FOLLOW-UP: the earlier primary full-suite run exposed tests/ace/tui/widgets/test_directive_completion_candidates.py::test_id_parenthesized_completion_advertises_identity_keywords. Direct reruns fail because first-token %id(be / %id(fa / %id(tr contexts are classified as parenthesized positional free_text, so directive_completion_candidates returns no identity keyword rows until a positional identity already exists. The touched successor/publication files do not affect directive completion; linked sase-core source at 279f0e0 still documents this behavior in crates/sase_core/src/editor/completion.rs. Triage the ACE test expectation versus the Rust directive-completion contract separately.

[2026-08-20T21:04:08Z · sase-rm.4] Implemented successor_publication across sase and sase-research-artifacts: deterministic research report targets, reserved in-process successor artifact timestamps, feedback replans through continue_as_successor, terminal repeated AgentsSyncFormatError publication failures, and repeated pipe family/workspace collision coverage. Focused primary suite passed 53 tests; plugin xprompt suite passed 10 tests and plugin just check passed. Primary just check is documented on the bead: latest run failed at unrelated closed-flag stale checkout for sase-rk after fmt/ruff/mypy passed; earlier full-lane escalation failed one unrelated directive-completion node.

[2026-08-20T21:06:10Z · sase-rm.4] Finalizer verification: implementation completed for successor publication plan; plugin focused xprompt test passed; plugin just check passed; primary focused suite passed with 53 tests; epic-symbols clean. Primary just check remains blocked by unrelated closed flag bead sase-rk/admin_center_config_hub and unrelated directive completion node.

## Dependencies

- **Depends on:** [sase-rm.3](sase-rm.3.md) ✓ · ⧖ 2026-08-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rm.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-rm.4.md) | [sase-rm.4](sase-rm.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`982ad29`](https://github.com/sase-org/sase/commit/982ad299ee6a81eec30f496b303b4ff0a29eb15b) | fix: make successor handoffs collision-safe | [sase-rm.4](sase-rm.4.md) | 2026-08-20 17:07:14 EDT |
