# Bead: sase-fl.2 — Agent runners survive mid-run editable source swaps

[Bead Pages](../README.md) / [sase-fl](README.md) / sase-fl.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tl](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tl/README.md) · **Assignee:** `sase-fl.2` · **Size:** medium
**Created:** 2026-08-05 18:32:24 EDT · **Closed:** 2026-08-05 18:55:15 EDT
**Plan:** [202608/epic\_launch\_false\_failure.md](https://github.com/sase-org/sase--plans/blob/main/202608/epic_launch_false_failure.md)

## Description

skew_guard: preload the post-gate import surface once at agent-runner start so a later `sase dev update` cannot tear a deferred import, snapshot the source revision the process booted against, and label failures whose cause is an import error after a swap as a code swap rather than an unusable store.

## Notes

[2026-08-05T22:54:39Z · sase-fl.2] PROPOSED FOLLOW-UP: symvision fails on master — `progress_fingerprint` in src/sase/llm_provider/commit_finalizer_git.py is an unused public symbol; reproduced with my changes stashed, so it predates this phase and blocks `just check`.

[2026-08-05T22:54:49Z · sase-fl.2] PROPOSED FOLLOW-UP: tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout is flaky under the 24-worker `just test` run (worker 2: lock_timeout after 12000ms); passes in isolation and is unrelated to this phase.

[2026-08-05T22:54:57Z · sase-fl.2] Import preload cost measured on this host: 113ms for 161 modules (sase.sdd + sase.bead walk, the named deferred modules, and the sase_workspace/sase_vcs/sase_llm entry-point distributions), well under the ~1.5s budget. Runner stack import for comparison: 1430ms.

[2026-08-05T22:55:15Z · sase-fl.2] Added src/sase/axe/source_skew.py: preload_post_gate_modules() walks sase.sdd + sase.bead, imports the named deferred modules (agents_sync.prompt_archive, notifications.senders, vcs_provider.plugins._git_commit_dispatch) and the sase_workspace/sase_vcs/sase_llm entry-point distributions, best-effort per module with a SASE_DISABLE_IMPORT_PRELOAD=1 kill switch and a debug elapsed-ms log; snapshot_source_revision() records the boot revision of the checkout sase was imported from (None outside a git checkout); code_swap_explanation() labels a failure as a mid-run code swap only when the exception chain contains an ImportError/AttributeError AND the revision moved. Wired snapshot at run_agent_runner import and preload in launch_agent_run just before run_execution_loop; handle_accepted_plan now records both epic store-failure branches through _store_failure_detail(), which names the swap and both revisions instead of blaming the store. Verified: just install; 10 new tests in tests/axe/test_source_skew.py pass; tests/test_axe_run_agent_exec_plan_followup_approvals.py + tests/test_sdd_commit_plan_accept.py (18) still pass with no assertion weakened; full just test 25932 passed with one pre-existing contention flake (noted) that passes in isolation; just check clean through fmt/ruff/mypy and fails only on the pre-existing symvision unused-symbol error reproduced on a stashed tree (noted). Measured preload cost 113ms/161 modules, under the ~1.5s budget.

## Dependencies

- **Blocks:** [sase-fl.3](sase-fl.3.md) ◐ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fl.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fl.2/README.md) | [sase-fl.2](sase-fl.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4895b8f`](https://github.com/sase-org/sase/commit/4895b8f32f64878321f3c4965f39b6d00c340eaa) | fix(axe): survive mid-run editable source swaps in agent runners | [sase-fl.2](sase-fl.2.md) | 2026-08-05 18:56:45 EDT |
