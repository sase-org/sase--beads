# Bead: sase-ij.3 — Enforce the published floor on the release branch and at publish time

[Bead Pages](../README.md) / [sase-ij](README.md) / sase-ij.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wq](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wq/README.md) · **Assignee:** `sase-ij.3` · **Size:** medium
**Created:** 2026-08-09 15:18:38 EDT · **Closed:** 2026-08-09 15:39:29 EDT
**Plan:** [202608/core\_window\_ratchet.md](https://github.com/sase-org/sase--plans/blob/main/202608/core_window_ratchet.md)

## Description

release-lane: add a CI job that runs only on the release-please branch and validates the exact declared PyPI core floor against bindings, wire-schema probes, smokes and the contract set, and pin the floor exactly in publish.yml's install-smoke so an incompatible floor mechanically blocks the PyPI upload.

## Notes

[2026-08-09T19:39:03Z · sase-ij.3] PROPOSED FOLLOW-UP: Fix Markdown formatting drift in memory note -- just check fails at fmt-md-check because committed sase/memory/build_and_run.md is not Prettier-formatted, and phase workers cannot edit memory files without explicit user permission.

[2026-08-09T19:39:29Z · sase-ij.3] Implemented release-branch floor CI and floor-exact publish smoke. Verified .venv/bin/python -m pytest tests/test_github_actions_ci.py -q; .venv/bin/python -m pytest -m contract \tests/ace/tui/test_visual_fixture_host_paths.py
tests/test_agent_stop_hook_config.py
tests/test_agent_tribe_terminology.py
tests/test_check_sase_core_rs_bindings_tool.py
tests/test_ci_bootstrap_sidecars_tool.py
tests/test_config_schema.py
tests/test_demo_media_postprocessor.py
tests/test_gemini_active_surface_guard.py
tests/test_github_actions_ci.py
tests/test_justfile_lint.py
tests/test_justfile_sase_core_dir.py
tests/test_patch_stitch_terminology_audit.py
tests/test_project_display_presentation_audit.py
tests/test_ruff_config.py
tests/test_run_pytest_command.py
tests/test_run_pytest_contention.py
tests/test_run_pytest_health.py
tests/test_run_pytest_main.py
tests/test_run_pytest_scoped.py
tests/test_run_pytest_tmpdir.py
tests/test_run_pytest_workers.py
tests/test_rust_install_cleanup.py
tests/test_sase_core_rs_at_reference_file_gate_smoke_tool.py
tests/test_sase_core_rs_bead_resolution_smoke_tool.py
tests/test_sase_core_rs_plan_header_smoke_tool.py
tests/test_sase_core_rs_telemetry_smoke_tool.py
tests/test_sase_migrate_statuses.py
tests/test_sdd_canonical_layout.py
tests/test_suite_gate.py
tests/test_timezone_display_guard.py
tests/test_validate_changelog_tool.py
tests/test_validate_dependency_group_tool.py
tests/test_validate_sase_core_rs_tool.py
tests/test_validate_sase_core_rs_version_tool.py
tests/test_validate_test_environment_tool.py
tests/test_xprompt_workflow_schema.py -q; just lint; just validate; just validate-committed-plans; git diff --check. just check is blocked by unmodified committed sase/memory/build_and_run.md failing fmt-md-check; test-scoped escalated to full suite and stayed queued behind external worker-token holders before being stopped.

[2026-08-09T19:39:59Z · sase-ij.3] Verification note correction: the contract-set command was `.venv/bin/python -m pytest -m contract $(cat tests/contract_manifest.txt) -q`, which passed 400 tests in 31.9s locally; the close note expanded the manifest file list in the shell.

[2026-08-09T19:41:24Z · sase-ij.3] Verified release branch floor CI and publish exact-floor smoke with: just install; workflow contract pytest; contract manifest pytest; just lint; just validate; just validate-committed-plans; git diff --check. just check remains blocked by committed Markdown formatting in sase/memory/build_and_run.md and scoped tests queued behind external worker tokens.

## Dependencies

- **Blocks:** [sase-ij.5](sase-ij.5.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ij.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.3/README.md) | [sase-ij.3](sase-ij.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`48d5bcd`](https://github.com/sase-org/sase/commit/48d5bcdf1e9c59a9a6dea498e3eb7a08b1c1a7d8) | ci: enforce published core floor in release workflows | [sase-ij.3](sase-ij.3.md) | 2026-08-09 15:42:12 EDT |
