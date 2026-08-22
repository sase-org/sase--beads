# Bead: sase-iu — Fix stale contract manifest and contract-set budget failure

[Bead Pages](../README.md) / sase-iu

**Status:** ✓ closed · **Resolution:** done · **Type:** ◆ task · **Task type:** · untyped · **+1 reports:** +16 · **↺ Reopened:** ↺2
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-il.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-il.5.md) · **Assignee:** `sase-iu` · **Size:** medium
**Created:** 2026-08-10 14:17:49 UTC · **Closed:** 2026-08-22 11:14:52 UTC

## Previously Closed

> ↺ Closed 2026-08-12T18:02:55Z · done
>
> Backlog cut to seven (owner-requested, 2026-08-12): fixed on master, verified at HEAD 42e60e5d6 after a clean 'just install'. '.venv/bin/python -m pytest tests/test_contract_manifest.py -q' -> 3 passed in 24.10s, including both nodes this bead names. tests/contract_manifest.txt now lists tests/test_probe_core_floor_tool.py and holds exactly 41 entries against _MANIFEST_ENTRY_BUDGET = 41; the manifest was refreshed at 90912ad7d and deliberately re-curated at 050264c7c with the budget reasoning recorded. NOTE on the yj +1 that reopened this: that evidence is the flake-baseline gate naming the node, not a live test failure. The gate draws on durable full-run records after its 2026-08-10T23:36:35Z cutoff, so a node whose root cause has since been fixed keeps being named until those records age out -- record bookkeeping, the same shape sase-j5 tracked, not stale manifest content. Worth noting: this node fails on collection in any workspace whose sase_core_rs build is stale, which is a plausible source of some post-fix records. Reopen with a +1 only on an actual manifest/marker mismatch reproduced on a properly installed tree.
>
> Reopened 2026-08-20T23:43:35Z by a +1 from @sase-rn.land

> ↺ Closed 2026-08-12T11:56:15Z · done
>
> Already fixed on master; verified at 62951abcb
>
> Reopened 2026-08-12T15:41:02Z by a +1 from @yj

## Description

Discovered while verifying retire_coder_alias_bucket on 2026-08-10. Serial pytest reports tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection failing because collect_contract_files() currently selects tests/test_probe_core_floor_tool.py but tests/contract_manifest.txt does not list it. The companion tests/test_contract_manifest.py::test_contract_set_manifest_entry_budget_has_no_hidden_headroom also fails because the committed manifest has 38 entries while _MANIFEST_ENTRY_BUDGET remains 36, so this needs deliberate contract-set re-curation or an updated measured budget, not just an incidental refresh in an unrelated model-alias patch.

## Notes

[2026-08-12T11:56:15Z · yb] Backlog triage (owner-requested seven-bead cut, 2026-08-12): verified fixed at HEAD 62951abcb. tests/contract_manifest.txt now lists tests/test_probe_core_floor_tool.py (line 14) and _MANIFEST_ENTRY_BUDGET is 41 against 41 committed entries. '.venv/bin/python -m pytest tests/test_contract_manifest.py -q' -> 3 passed in 21.93s, including test_contract_manifest_matches_marker_selection and test_contract_set_manifest_entry_budget_has_no_hidden_headroom.

[2026-08-21T23:48:34Z · sase-rr.5.land] SUPPLEMENTARY: Independent reproduction while adopting the published sase-core-rs 0.29.9 floor (sase-rr.5 land) at HEAD 47830f9de. just check escalated to the full suite (rules: contract-set-only, core-identity-changed, packaging-config) and failed tests/test_contract_manifest.py::test_contract_set_manifest_entry_budget_has_no_hidden_headroom. Focused rerun failed identically: tests/contract_manifest.txt has 54 entries against _MANIFEST_ENTRY_BUDGET=53, overage tests/test_xprompt_workflow_schema.py. Local diff is only pyproject.toml and uv.lock (sase-core-rs>=0.29.9,<0.30.0). Already +1'd this task; not creating a new bead.

[2026-08-22T11:14:52Z · sase-iu] Fixed the current contract-manifest budget failure on 2026-08-22 at HEAD 3ab0c52dea38. Removed tests/test_xprompt_workflow_schema.py from the always-on contract marker and regenerated tests/contract_manifest.txt to 53 entries, matching _MANIFEST_ENTRY_BUDGET=53. Rationale recorded in tests/test_contract_manifest.py: workflow JSON/YAML changes already fire the src-data-asset full-suite rule, while the workflow schema tests still run in the exhaustive lane. Optimized tests/test_timezone_display_guard.py with a safe candidate-token prefilter before AST parsing; the curated 53-entry contract set then passed under the documented serial command: .venv/bin/python -m pytest -m contract tests/ace/tui/test_visual_fixture_host_paths.py
tests/test_agent_stop_hook_config.py
tests/test_agent_tribe_terminology.py
tests/test_check_sase_core_rs_bindings_tool.py
tests/test_ci_bootstrap_sidecars_tool.py
tests/test_commit_type_tag_contract.py
tests/test_config_schema.py
tests/test_config_schema_ace.py
tests/test_config_schema_beads.py
tests/test_config_schema_extensions.py
tests/test_config_schema_keymaps.py
tests/test_config_schema_runtime_limits.py
tests/test_core_finalizer_facade.py
tests/test_demo_media_postprocessor.py
tests/test_gemini_active_surface_guard.py
tests/test_github_actions_ci.py
tests/test_justfile_lint.py
tests/test_justfile_sase_core_dir.py
tests/test_patch_stitch_terminology_audit.py
tests/test_probe_core_floor_tool.py
tests/test_project_display_presentation_audit.py
tests/test_ratchet_core_window_tool.py
tests/test_ruff_config.py
tests/test_run_pytest_command.py
tests/test_run_pytest_contention.py
tests/test_run_pytest_health.py
tests/test_run_pytest_main.py
tests/test_run_pytest_scoped.py
tests/test_run_pytest_tmpdir.py
tests/test_run_pytest_workers.py
tests/test_rust_install_cleanup.py
tests/test_sase_bead_tool.py
tests/test_sase_core_rs_at_reference_file_gate_smoke_tool.py
tests/test_sase_core_rs_bead_resolution_smoke_tool.py
tests/test_sase_core_rs_feature_flag_state_smoke_tool.py
tests/test_sase_core_rs_glossary_line_break_smoke_tool.py
tests/test_sase_core_rs_plan_header_smoke_tool.py
tests/test_sase_core_rs_telemetry_smoke_tool.py
tests/test_sase_migrate_statuses.py
tests/test_sdd_canonical_layout.py
tests/test_setup_required_plugins_tool.py
tests/test_suite_gate.py
tests/test_suite_gate_budget.py
tests/test_suite_gate_lease.py
tests/test_suite_gate_reclaim.py
tests/test_timezone_display_guard.py
tests/test_validate_changelog_tool.py
tests/test_validate_dependency_group_tool.py
tests/test_validate_sase_core_rs_contracts_tool.py
tests/test_validate_sase_core_rs_environment_tool.py
tests/test_validate_sase_core_rs_tool.py
tests/test_validate_sase_core_rs_version_tool.py
tests/test_validate_test_environment_tool.py -p no:randomly --durations=0 -q -> 552 passed in 27.00s (shell elapsed 29.99s). Focused verification passed: .venv/bin/python -m pytest tests/test_contract_manifest.py tests/test_timezone_display_guard.py tests/test_xprompt_workflow_schema.py -q -> 9 passed in 32.35s. Required just check passed fmt, ruff, mypy, feature flags, pyscripts, test waits, changelog, patch/stitch terminology, symvision, toobig, SASE validation, and committed plans, then escalated to the full suite and failed only unrelated current-tree tests; routed those via /sase_new_task: %final/LSP completion on active epic sase-s0, skills-inventory flake as +1 on sase-rv, monitor-supervise flake as +1 on sase-lk, and monitor-start pass-focused recurrence as a note on sase-j7.

## +1 Evidence

> **+1** by `x3` · 2026-08-10 14:43:44 UTC
>
> Independent reproduction during distinct_notification_tab_icons verification on 2026-08-10: full non-visual just test failed tests/test_contract_manifest.py::{test_contract_manifest_matches_marker_selection,test_contract_set_manifest_entry_budget_has_no_hidden_headroom}. The first failure reports tests/contract_manifest.txt is stale and asks to run just refresh-contract-manifest; the companion budget test fails in the same run. This patch touches notification tab icon rendering/resolution, Rust notification tab icon donation, doctor config checks, docs, and notification tests; it does not touch the contract manifest tooling or manifest file.

> **+1** by `wv.f4` · 2026-08-10 16:59:04 UTC
> **Observed since:** 2026-08-10 16:00:29 UTC
>
> Independent reproduction during smarter_model_alias verification on 2026-08-10: just test and a serial isolation rerun both failed tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection. The current marker set includes tests/test_sase_bead_tool.py, but tests/contract_manifest.txt omits it. This alias patch does not touch contract marker selection or the contract manifest.

> **+1** by `toobig-2b.split_file.src.sase.workflows.commit.commit_hooks.0` · 2026-08-10 17:12:10 UTC
> **Observed since:** 2026-08-10 16:53:07 UTC
>
> Independent reproduction during commit-hooks module-split verification on 2026-08-10: just check escalated to the full 28,458-test suite and failed tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection; a serial rerun reproduced that the current marker set includes tests/test_sase_bead_tool.py while tests/contract_manifest.txt omits it. The refactor touches commit hook modules and their tests, not the contract marker or manifest.

> **+1** by `y3` · 2026-08-11 19:02:01 UTC
> **Observed since:** 2026-08-11 18:45:34 UTC
>
> Independent impact recurrence during fix_ci_model_alias_availability verification on 2026-08-11: just check-full passed the full pytest cost lane but failed the final flake-baseline gate, which again named tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection as a baseline-exceeding node. The local patch touches only tests/test_bead/test_work_rendering_models.py, not contract manifest tooling or contract marker selection.

> **+1** by `sase-js.5` · 2026-08-11 21:39:45 UTC
> **Observed since:** 2026-08-11 20:37:19 UTC
>
> Independent impact recurrence during file_ref_and_object_store (sase-js.5) verification on 2026-08-11: just check-full passed lint, SASE validation, committed-plan validation, and the full pytest cost lane, then failed only the flake-baseline selection-health gate. The baseline-exceeding set again named tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection. This diff touches artifact refs/@file/object-store config, capture, archive publication, and Rust artifact-ref/object-store bindings, not contract marker selection or tests/contract_manifest.txt.

> **+1** by `ci_fix.sase.y` · 2026-08-12 02:03:28 UTC
> **Observed since:** 2026-08-12 01:03:57 UTC
>
> Independent impact recurrence on 2026-08-12 during default-branch CI repair at pinned master 62951abcb4a20d3c7ad5c01190433ee91f837f9c: just check-full passed every lint/validation gate and all 29,012 tests, then failed only selection-health --fail-on-new-flake, again naming tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection. This patch does not touch contract marker selection or tests/contract_manifest.txt.

> **+1** by `yj` · 2026-08-12 15:41:02 UTC
> **Observed since:** 2026-08-12 14:49:00 UTC
>
> Post-close impact recurrence during bead_list_summary_line verification on 2026-08-12: just check-full passed formatting, all lint gates, SASE validation, committed-plan validation, and the full pytest cost lane, then failed only the flake-baseline selection-health gate. The gate again named tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection. This diff touches bead list summary presentation/CLI/docs/tests and does not touch contract marker selection or tests/contract_manifest.txt; recording against the existing filed contract-manifest task cited by the current flake-baseline reports.

> **+1** by `sase-rn.land` · 2026-08-20 23:43:35 UTC
> **Observed since:** 2026-08-20 23:43:35 UTC
>
> Post-close recurrence proposed by phase sase-rn.3 while landing epic sase-rn at HEAD 4afec203b after just install: tests/test_core_finalizer_facade.py is selected by the contract marker but absent from tests/contract_manifest.txt; adding it would make 53 entries against _MANIFEST_ENTRY_BUDGET=52. This is an actual current manifest/marker mismatch plus deterministic budget overflow, not selection-health history, and requires the documented contract-set curation procedure.

> **+1** by `09u.f0` · 2026-08-21 19:24:23 UTC
> **Observed since:** 2026-08-21 18:59:28 UTC
>
> Independent reproduction during compact_bead_wait_status_tokens verification on 2026-08-21 after just install and formatting: just check escalated to the full scoped lane and failed tests/test_contract_manifest.py::test_contract_set_manifest_entry_budget_has_no_hidden_headroom. Focused rerun reproduced the same deterministic failure: tests/contract_manifest.txt has 54 entries against _MANIFEST_ENTRY_BUDGET=53, with tests/test_xprompt_workflow_schema.py over budget. This diff only touches ACE wait-status presentation/docs/tests and one PNG golden, not contract marker selection or tests/contract_manifest.txt.

> **+1** by `sase-rs.land` · 2026-08-21 19:50:47 UTC
> **Observed since:** 2026-08-21 19:28:04 UTC
>
> Proposed by sase-rs.4 and sase-rs.6 during epic sase-rs. Current-tree just check at HEAD 28009002d deterministically failed test_contract_set_manifest_entry_budget_has_no_hidden_headroom: 54 entries vs budget 53, overage tests/test_xprompt_workflow_schema.py. Immediate isolated rerun failed identically. The feature-flag epic did not add that workflow-schema contract entry; this corroborates the reopened task's current defect.

> **+1** by `0a2.f1` · 2026-08-21 20:41:51 UTC
> **Observed since:** 2026-08-21 20:07:35 UTC
>
> Independent reproduction during Statistics description-rail implementation on 2026-08-21 at HEAD f1c355563 after just install. just check escalated to the full suite and failed tests/test_contract_manifest.py::test_contract_set_manifest_entry_budget_has_no_hidden_headroom. Isolated rerun failed identically: tests/contract_manifest.txt has 54 entries against _MANIFEST_ENTRY_BUDGET=53, overage tests/test_xprompt_workflow_schema.py. This diff does not touch contract marker selection or tests/contract_manifest.txt.

> **+1** by `sase-s0.land` · 2026-08-21 22:24:31 UTC
> **Observed since:** 2026-08-21 22:15:57 UTC
>
> Proposed by phase sase-s0.2 while implementing epic sase-s0. Its full-suite escalation on current master found tests/contract_manifest.txt at 54 entries against _MANIFEST_ENTRY_BUDGET=53, with tests/test_xprompt_workflow_schema.py as the over-budget entry. The %final completion diff does not touch the contract-set manifest or budget. Current landing audit independently confirms the committed file still has 54 nonblank entries and the guard remains 53; this is the same deterministic recurrence already tracked here.

> **+1** by `sase-rr.5.land` · 2026-08-21 23:15:36 UTC
> **Observed since:** 2026-08-21 23:11:34 UTC
>
> Proposed independently by phases sase-rr.5.1, sase-rr.5.3, sase-rr.5.4, and sase-rr.5.5: after just install, the deterministic contract budget test reports tests/contract_manifest.txt at 54 entries against budget 53, with tests/test_xprompt_workflow_schema.py as the overage. Finalizer-integrity changes did not introduce that entry.

> **+1** by `toobig-3d.split_file.src.sase.ace.tui.actions.agent_workflow._prompt_bar_save_xprompt.0` · 2026-08-22 00:09:45 UTC
> **Observed since:** 2026-08-21 23:40:38 UTC
>
> Independent deterministic reproduction on 2026-08-21 during prompt-bar xprompt module splitting after just install. just check's 14-worker full suite failed tests/test_contract_manifest.py::test_contract_set_manifest_entry_budget_has_no_hidden_headroom, and an immediate serial rerun on the unchanged tree failed identically: tests/contract_manifest.txt contains 54 entries against budget 53, with tests/test_xprompt_workflow_schema.py over budget. Current diff does not touch the contract manifest or its budget.

> **+1** by `toobig-3d.split_file.src.sase.finalizers.declaration.0` · 2026-08-22 01:44:27 UTC
> **Observed since:** 2026-08-22 01:19:10 UTC
>
> Independent deterministic reproduction during declaration.py module-split verification at HEAD 2ce7483f2581011148f3d9717a492e55dcec2a31 after just install. just check escalated to the full suite and failed tests/test_contract_manifest.py::test_contract_set_manifest_entry_budget_has_no_hidden_headroom; an immediate serial rerun failed identically because tests/contract_manifest.txt has 54 entries against _MANIFEST_ENTRY_BUDGET=53, with tests/test_xprompt_workflow_schema.py over budget. The local diff only splits src/sase/finalizers/declaration.py and does not touch the contract manifest or budget.

> **+1** by `0aa` · 2026-08-22 11:13:13 UTC
> **Observed since:** 2026-08-22 10:43:26 UTC
>
> Independent reproduction during restore_final_directive_visibility verification on 2026-08-22 at HEAD 3ab0c52dea382d76c76321ba6510ab0833f1a88a after rebuilding sase_core_rs and installing the local LSP. just check escalated to the full suite (core-identity-changed) and failed tests/test_contract_manifest.py::test_contract_set_manifest_entry_budget_has_no_hidden_headroom. Focused xdist rerun and serial no-xdist rerun failed identically: tests/contract_manifest.txt contains 54 entries against _MANIFEST_ENTRY_BUDGET=53, with tests/test_xprompt_workflow_schema.py over budget. The local diff touches only final directive completion tests/policy.

## Lineage

```mermaid
flowchart TD
    n0["sase-iu: Fix stale contract manifest and contract-set budget failure [closed]"]
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-iu](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-iu/README.md) | [sase-iu](README.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8c1acbf`](https://github.com/sase-org/sase/commit/8c1acbfa505626d3e83414018db37349914c885c) | fix(tests): recurate contract manifest budget | [sase-iu](README.md) | 2026-08-22 11:16:23 UTC |
