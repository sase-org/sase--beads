# Bead: sase-xy.5.5.3 — Ratchet the binding floor and prove the combined clean-install contract

[Bead Pages](../README.md) / [sase-xy.5.5](sase-xy.5.5.md) / sase-xy.5.5.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-xy.5.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xy.5.land.md) · **Assignee:** `sase-xy.5.5.3` · **Size:** medium
**Created:** 2026-09-07 20:23:12 EDT · **Closed:** 2026-09-07 22:57:00 EDT
**Plan:** [202609/pager\_target\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/pager_target_landing_repairs.md)

## Description

clean-install-contract: publish or consume the completed core contract, ratchet packaging and capability validation, and exercise the full rendered-link corpus from a clean environment.

## Notes

[2026-09-08T02:57:00Z · sase-xy.5.5.3--1] Ratcheted sase-core-rs floor 0.32.34→0.32.41 (pyproject.toml/uv.lock) and moved sase-core-revision.txt to a47171d (tag v0.32.41, verified as sase-core origin/master HEAD and as actually published on PyPI, not a local-only build), which carries the phase-1 repository-target-contract Rust work (0ec3050) and the repository-owned document-source-resolution fix (885a61b). Extended tools/validate_sase_core_rs REQUIRED_BINDINGS with artifact_ref_scan_document, artifact_ref_document_scan_wire_schema_version, artifact_ref_resolve_document_source_target, artifact_ref_target_resolution_wire_schema_version, plus both new wire-schema-version=1 expectations in _validate_artifact_ref_schemas, with tests/test_validate_sase_core_rs_contracts_tool.py updated to match; `.venv/bin/python tools/validate_sase_core_rs` exits 0. Verified suites green: validate_sase_core_rs tool/contracts/version/environment tests + ratchet_core_window/ratchet_core_revision tests (89 passed); artifact_refs, pager (incl. rendered-link contract/navigation/failure + screenshot-path), main/test_pager_command, bead-show pager (cli+tui), core/test_artifact_ref_files_index, doctor artifact-ref checks, ACE artifact_ref_repair/view_files_pager(_contract)/artifact_ref_syntax (529 passed); main/test_artifact_cli_read + full ACE link-index suite (link_index/link_follow/link_rail(+mount)/link_subject_mixin/link_trail/artifact_links_ref_kind/artifact_links_panel_modal) (99 passed); test-visual for pager/visual + prompt_highlighting + link_rail PNG snapshots (26+22+16 passed). Excluded test-visual failures for test_artifact_links_panel_needs_reveal_row_png_snapshots (2, both size variants) as a known, unrelated, pre-existing missing-golden gap already logged on bead sase-xy.5.5.5.4.2 and tracked broadly by sase-x5 — no new golden generated/committed. Ran `just check` inline (escalated to full lane via core-identity-changed/packaging-config rules) green. Closed the loop with the monitored `just check-full` landing gate required by lint_and_test.md: exit 0, all fmt/lint/SASE-validation/committed-plans/test-cost/flake-baseline gates green (only non-blocking test-cost budget advisories for ace_page_enter/ace_settle_pilot/pilot_pause_delay/textual_app_run_test_enter/yaml_load, flagged as host-contention wall-clock overages, not cpu-cost regressions). check-full's _setup step runs validate_test_environment --check-core, which cross-validates the installed sase_core_rs module's version and bindings against the pinned sase-core checkout (a47171d) — this is the clean-install contract proof: the installed module matches the tracked, released revision, not an untracked local build. No Rust source changed in this phase, so the sase-core repo's own ./scripts/check.sh was not independently re-run; a47171d is an already-released, already-CI-verified upstream commit. sase bead epic-symbols sase-xy.5.5.3 reports no leftover --epic-symbol entries.

## Dependencies

- **Depends on:** [sase-xy.5.5.1](sase-xy.5.5.1.md) ✓ · ⧖ 2026-09-07
- **Depends on:** [sase-xy.5.5.2](sase-xy.5.5.2.md) ✓ · ⧖ 2026-09-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xy.5.5.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xy.5.5.3.md) | [sase-xy.5.5.3](sase-xy.5.5.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b67c74c`](https://github.com/sase-org/sase/commit/b67c74ce7ecf2268a3abba0d61e0fdbabf7f56e1) | feat(artifact-ref): ratchet sase-core-rs floor to 0.32.41 and extend contract validation | [sase-xy.5.5.3](sase-xy.5.5.3.md) | 2026-09-07 22:58:04 EDT |
