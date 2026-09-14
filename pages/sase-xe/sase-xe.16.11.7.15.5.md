# Bead: sase-xe.16.11.7.15.5 — Viewer consumes the new facts and drops noisy chrome

[Bead Pages](../README.md) / [sase-xe.16.11.7.15](sase-xe.16.11.7.15.md) / sase-xe.16.11.7.15.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.v](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.v.md) · **Assignee:** `sase-xe.16.11.7.15.5` · **Size:** medium
**Created:** 2026-09-13 18:38:06 EDT · **Closed:** 2026-09-14 09:54:10 EDT
**Plan:** [202609/remote\_agents\_display\_parity.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_agents_display_parity.md)

## Description

remote-render-integration: map timestamps, workspace numbers, clan identity, and human project labels into remote rows; suppress online/aging chrome on healthy rows and align viewer freshness thresholds with the worker poll cadence; keep render-cache keys honest.

## Notes

[2026-09-14T13:21:15Z · sase-xe.16.11.7.15.5] PROPOSED FOLLOW-UP: remote-render-integration populates Agent.workspace_num for remote rows for the first time (previously always None). Verified the two highest-risk consumers fail closed for remote origins: _keybinding_bindings.py already early-returns on fleet_origin_alias before reaching the workspace_num-gated tmux footer binding, and resolve_agent_workspace_dir (file_path_hints.py) fails closed via a real os.path.isdir check regardless of workspace_num since a remote synthetic /fleet/<id>/project.yml never resolves to a real local directory; also guarded agent_detail.py file-panel fallback with an explicit fleet_origin_alias check. Not individually traced: _kill_persistence.py, _revive_artifacts.py, _entry_relaunch.py, _dismiss_persistence.py, _mentor_review.py, which all read workspace_num/effective_workspace_num -- worth a dedicated audit to confirm they too fail closed (or are simply unreachable for remote rows) rather than acting on a phantom local workspace number.

[2026-09-14T13:53:25Z · sase-xe.16.11.7.15.5--1] PROPOSED FOLLOW-UP: just check-full has 4 pre-existing failures unrelated to this phase, introduced by commit 6a60ee5fb7 (feat(managed-tmp): make reaper horizons and pressure limits configurable) and eea8af0421 (feat(agent): isolate Cargo build-dir for launched and recipe builds): tests/test_justfile_lint.py::test_rust_dev_install_disables_cargo_incremental_cache (rm -rf incremental-cache line missing from rust-dev-install recipe), and 3 tests in tests/test_check_sase_core_rs_bindings_tool.py (test_scan_resolves_every_call_site_statically, test_scan_finds_artifact_context_query_bindings, test_dev_extension_exposes_every_collected_name) all failing because src/sase/core/managed_tmp_reaper.py:281 passes a non-string-literal name to require_rust_binding(), which check_sase_core_rs_bindings cannot statically resolve.

[2026-09-14T13:54:10Z · sase-xe.16.11.7.15.5--1] just check ran the lint/fmt/validation suite (all green) plus the full test suite (escalated from scoped via core-identity-changed rule): 41559 passed, 21 skipped, 4 failed. All 4 failures are pre-existing and unrelated to this phase's diff (verified via git blame): tests/test_justfile_lint.py::test_rust_dev_install_disables_cargo_incremental_cache and 3 tests in tests/test_check_sase_core_rs_bindings_tool.py, all traceable to prior commits 6a60ee5fb7 and eea8af0421 that never touched this phase's files (_fleet_agents_rows.py, _agent_list_render_agent.py, agent_detail.py, and their tests/snapshots). Logged as a PROPOSED FOLLOW-UP note for the epic land agent to triage.

## Dependencies

- **Depends on:** [sase-xe.16.11.7.15.2](sase-xe.16.11.7.15.2.md) ✓ · ⧖ 2026-09-13
- **Depends on:** [sase-xe.16.11.7.15.4](sase-xe.16.11.7.15.4.md) ✓ · ⧖ 2026-09-13
- **Blocks:** [sase-xe.16.11.7.15.6](sase-xe.16.11.7.15.6.md) ✓ · ⧖ 2026-09-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-xe.16.11.7.15.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-xe.16.11.7.15.5.md) | [sase-xe.16.11.7.15.5](sase-xe.16.11.7.15.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8ed00c4`](https://github.com/sase-org/sase/commit/8ed00c4ed67dc85abded7ea31ce8fce49b3cf865) | fix(ace-tui): map remote fleet-row identity fields and suppress stale online chrome | [sase-xe.16.11.7.15.5](sase-xe.16.11.7.15.5.md) | 2026-09-14 09:56:01 EDT |
