# Bead: sase-q0.3 — Refuse destructive preparation of an occupied checkout

[Bead Pages](../README.md) / [sase-q0](README.md) / sase-q0.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.06g](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.06g.md) · **Assignee:** `sase-q0.3` · **Size:** medium
**Created:** 2026-08-18 13:44:19 EDT · **Closed:** 2026-08-18 16:25:05 EDT
**Plan:** [202608/workspace\_exclusivity.md](https://github.com/sase-org/sase--plans/blob/main/202608/workspace_exclusivity.md)

## Description

guard: write a per-checkout occupant record when an agent takes a workspace and make every destructive preparation path verify exclusive occupancy before it cleans, resets, or checks out, failing the run instead of deleting another agent's work.

## Notes

[2026-08-18T20:23:09Z · sase-q0.3] PROPOSED FOLLOW-UP: `just check`'s symvision lint fails for every agent right now because of a stale `--epic-symbol "sase-pw.8(project_accent_map)"` entry in Justfile — bead sase-pw.8 is already closed. Not caused by this phase (no --epic-symbol entries exist for sase-q0.3); needs its own cleanup pass to remove the stale entry and its symbol.

[2026-08-18T20:23:46Z · sase-q0.3] PROPOSED FOLLOW-UP: two pre-existing test failures unrelated to this phase surfaced during `just test-scoped`: tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift and test_current_structural_view_matches_checked_in_snapshot (checked-in CLI completion spec is out of sync with the argparse tree — needs `just sync-completion-spec`), and tests/feature_flags/test_integrity.py::test_kind_mismatch_when_default_disagrees_with_kind (TypeError: demo_flag() got an unexpected keyword argument default — a test-helper signature drift). Neither touches workspace/occupancy code.

[2026-08-18T20:24:09Z · sase-q0.3] PROPOSED FOLLOW-UP: the plan text names per-phase VCS setup steps "gh__setup/gh__prepare/gh__checkout" as a guard call site, but no such named hooks exist in this repo (ws_setup_workflow in workspace_provider/_hookspec.py is an unwired stub). A family agent moving into an already-claimed workspace across phases always goes through the launcher claim funnel (agent/launch_spawn.py) then prepare_workspace_if_needed — both already guarded — so coverage is equivalent, but the epic land agent should confirm this reading is correct or point at the intended plugin.

[2026-08-18T20:24:30Z · sase-q0.3] PROPOSED FOLLOW-UP: occupant.json clearing on release is wired at the three primary release funnels (agent-finalize in run_agent_runner_lifecycle.py, SIGTERM release in run_agent_runner_signals.py, and the stale-claim reaper in ace/scheduler/stale_running_cleanup.py) rather than at all ~60 release_workspace() call sites across the codebase. This is safe today because the guard already treats a dead-pid occupant record as a legitimate takeover, not a conflict, but a future hardening pass could centralize the write/clear inside running_field._operations.py itself (deriving the checkout dir from workspace_num) so every release path clears it directly.

[2026-08-18T20:25:05Z · sase-q0.3] Implemented the guard phase: a per-checkout occupant record (.sase/occupant.json — pid, artifacts_timestamp, agent_name, workflow, project, workspace_num, cl_name, claim time) is written by both the launcher-preclaim/transfer path (agent/launch_spawn.py) and the deferred-claim path (axe/run_agent_phases.py::claim_deferred_workspace), and cleared on release at the three primary release funnels (agent-finalize, SIGTERM, stale-claim reaper). The conflict decision (decide_workspace_occupant_conflict) lives in sase_core (crates/sase_core/src/agent_launch/mod.rs), exposed via a new PyO3 binding in sase_core_py and a thin Python wrapper (core/agent_launch_claims.py); core/occupancy_guard.py supplies pid-liveness and the RUNNING-field cross-check and raises WorkspaceOccupiedError on conflict. The guard runs before every destructive prep site named in the plan: prepare_workspace_if_needed and prepare_linked_repo_workspaces_if_needed (axe/run_agent_runner_setup.py) and both retry re-prep call sites in axe/run_agent_exec_retry.py::handle_workflow_error. Verified: 7 new Rust unit tests (cargo test -p sase_core --lib occupancy, all pass) covering no-record/self/dead-pid proceed cases and live-other/RUNNING-disagreement refuse cases including the two disagreement sub-cases; 41 new Python tests across tests/workspace_provider/test_occupant.py, tests/test_core_occupancy_guard.py, and additions to test_run_agent_runner_setup_workspace.py, test_axe_run_agent_exec_retry.py, test_axe_run_agent_runner_deferred_workspace_claim.py, and test_run_agent_runner_lifecycle.py — including integration-style tests that a live foreign occupant refuses prep with the occupant named and a same-pid/dead-pid occupant proceeds. Ran the full existing test_run_agent_runner_setup_workspace.py, test_run_agent_runner_setup_linked_repos.py, test_axe_run_agent_exec_retry.py, test_axe_run_agent_retry_spawn.py, test_run_agent_runner_auto_dismiss.py, test_axe_run_agent_runner_deferred_workspace_claim.py, and test_run_agent_runner_lifecycle.py suites (156 tests) plus mypy — all green, no regressions from the new required-then-defaulted kwargs threaded through prepare_workspace_if_needed/prepare_linked_repo_workspaces_if_needed/install_workspace_release_sigterm_handler. just check is clean except lint(symvision), which fails on a pre-existing stale --epic-symbol for the already-closed, unrelated bead sase-pw.8 (sase-q0.3 itself has zero --epic-symbol entries, confirmed via sase bead epic-symbols). just test-scoped's only 3 failures are pre-existing and unrelated (CLI completion spec drift, a feature-flag test-helper signature mismatch). Filed 4 PROPOSED FOLLOW-UP notes on this bead for the epic land agent: the stale symvision entry, the two unrelated pre-existing test failures, a discrepancy between the plan's named gh__setup/gh__prepare/gh__checkout hooks (which don't exist in this repo) and the actual funnel points that provide equivalent coverage, and the narrower-than-universal scope of occupant-record clearing on release.

## Dependencies

- **Depends on:** [sase-q0.2](sase-q0.2.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-q0.4](sase-q0.4.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-q0.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-q0.3/README.md) | [sase-q0.3](sase-q0.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7a2906e`](https://github.com/sase-org/sase/commit/7a2906e136854a6904f5d3eda3146ac8fc63aa6a) | feat(core): guard destructive workspace prep against occupied checkouts | [sase-q0.3](sase-q0.3.md) | 2026-08-18 16:27:01 EDT |
