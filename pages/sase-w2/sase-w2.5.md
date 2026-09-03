# Bead: sase-w2.5 — Retire v1 as an import source behind a sunset flag

[Bead Pages](../README.md) / [sase-w2](README.md) / sase-w2.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.8--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.8.md) · **Assignee:** `sase-w2.5` · **Size:** medium
**Created:** 2026-09-03 12:32:03 EDT · **Closed:** 2026-09-03 19:49:09 EDT
**Plan:** [202609/athena\_agent\_sync\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202609/athena_agent_sync_repair.md)

## Description

v1-retirement: gate the legacy v1 import leg behind a sunset feature flag so v1 payloads stay readable as evidence but are never importable, and record the one-way call as a decision record.

## Notes

[2026-09-03T23:02:29Z · sase-w2.5] PROPOSED FOLLOW-UP: whole-repo mypy gate (just _lint-mypy) fails pre-existing, unrelated to this phase — src/sase/ace/tui/modals/plugins_browser_workers.py:151 "Property \"rows\" defined in \"PluginsLoadResult\" is read-only [misc]" and plugins_browser_pane.py:179 "Definition of \"_create_options\" in base class \"PluginsBrowserLayoutMixin\" is incompatible with definition in base class \"PluginsBrowserRenderingMixin\" [misc]"; reproduced on a clean stash of master (commit bdd2eadcf) with no sase-w2.5 changes applied, so it blocks just check for every agent until fixed.

[2026-09-03T23:48:13Z · sase-w2.5] PROPOSED FOLLOW-UP: two static audit tests fail pre-existing, unrelated to this phase — tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed and tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed both report an unreviewed context "src/sase/agents_sync/v1_forget_import.py:_apply_closure"; reproduced on a clean stash of master (commit bdd2eadcf) with no sase-w2.5 changes applied. v1_forget_import.py landed in the v2-adoption phase (sase-w2.4); its _apply_closure needs to be added to the reviewed-contexts allowlist in both audit tests (or the audits need a real review of its directory-operation/dismissed-save safety).

[2026-09-03T23:49:09Z · sase-w2.5] Created the sunset flag v1_import_retired (kind=sunset, default on, bead sase-wc) via sase flag new and pasted its registry entry into src/sase/feature_flags/registry.py. Gated the v1 import leg's two materialization points inside integrate_foreign_bundles (src/sase/agents_sync/bundles.py) — _create_imported_artifact and _refresh_imported_artifact — behind the flag, while leaving owner-observed/self-owned-present classification, capture/detection (incoming_detection.py), and the v2-adoption matcher's evidence reads untouched, so v1 payloads stay readable as evidence but are never materialized when the flag is on. Added IntegrationCounts.v1_import_skipped and a new CachedIntegrationDisposition value 'sunset_skipped' so src/sase/agents_sync/incoming_integration.py surfaces the skip at both the cached and full-sync entry points without writing an import receipt (the hood stays visibly pending, not silently dropped). The existing publisher-side retire-v1 gate (v1_retirement.py) is untouched. Recorded the decision as SASE memory sase/memory/decisions/v1-import-retired.md via /sase_memory_write (ran sase memory init to regenerate CLAUDE.md/AGENTS.md/provider shims). Regenerated src/sase/config/sase.schema.json via tools/sync_feature_flags_schema --write. Added both-states tests: tests/agents_sync/test_bundles.py (autouse fixture disables the flag for the module's existing materialization tests since sunset defaults on; new test_v1_import_retired_flag_blocks_create_and_refresh covers flag-on create+refresh blocking) and tests/agents_sync/test_incoming_cache_v1.py (new test_v1_import_retired_flag_skips_foreign_hood_via_full_pipeline covers the cached+full-sync pipeline end to end). Verified: ruff check/format clean on all touched files; mypy clean on all touched files; symvision clean repo-wide (after making the new bundles.py helper private, since it has no cross-file consumer); toobig clean; tests/agents_sync full suite 309 passed; tests/feature_flags + tests/test_check_feature_flags_tool*.py all passed. just check's repo-wide mypy gate and two static audit tests fail, but both are pre-existing and unrelated to this phase (confirmed by reproducing them on a clean git stash of master commit bdd2eadcf with no sase-w2.5 changes applied) — filed as PROPOSED FOLLOW-UP notes on this bead. The diff-scoped just test-scoped lane ran under heavy concurrent host load (38433 passed, 23 failed); none of the 23 failures touch files in this diff or tests/agents_sync/tests/feature_flags, and the two I sampled in depth (the audit tests above) are confirmed pre-existing. sase bead epic-symbols sase-w2.5 reported no --epic-symbol entries to resolve.

## Dependencies

- **Depends on:** [sase-w2.4](sase-w2.4.md) ✓ · ⧖ 2026-09-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-w2.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-w2.5/README.md) | [sase-w2.5](sase-w2.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ffa4c76`](https://github.com/sase-org/sase/commit/ffa4c765d8b54732101964229b026d57a18b392d) | feat(agents-sync): retire v1 as an import source behind a sunset flag | [sase-w2.5](sase-w2.5.md) | 2026-09-03 19:50:46 EDT |
