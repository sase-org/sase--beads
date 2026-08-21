# Bead: sase-rs.4 — Persistent flag enable and disable commands

[Bead Pages](../README.md) / [sase-rs](README.md) / sase-rs.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.09g](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.09g.md) · **Assignee:** `sase-rs.4` · **Size:** medium
**Created:** 2026-08-21 13:58:42 UTC · **Closed:** 2026-08-21 17:32:37 UTC
**Plan:** [202608/feature\_flag\_control\_center.md](https://github.com/sase-org/sase--plans/blob/main/202608/feature_flag_control_center.md)

## Description

cli: add sorted sase flag disable and enable commands with rich and JSON results, completion, idempotent shared mutations, and the existing AXE restart machinery, including clear partial-success reporting.

## Notes

[2026-08-21T17:31:28Z · sase-rs.4] PROPOSED FOLLOW-UP: just check lint (feature flags) fails on live orphan flag beads sase-rc (key artifact_links) and sase-ro (key pluggable_finalizers) with no registry definition — sase-rc is past the 24h in-flight grace; this CLI phase did not create those beads.

[2026-08-21T17:31:46Z · sase-rs.4] PROPOSED FOLLOW-UP: just test-scoped escalated to the full suite (stale coverage baseline + serial budget) and failed unrelated nodes: tests/ace/tui/test_logs_pane.py scroll, tests/test_contract_manifest.py budget, tests/main/test_artifact_cli_list_doctor.py, tests/test_xprompt_directive_completion_parity.py, tests/test_finalizers_protocol_harness.py override_flags NameError, tests/main/test_skills_handler.py, tests/fakey/test_retry_pipeline_e2e.py. Not caused by flag enable/disable.

[2026-08-21T17:32:02Z · sase-rs.4] PROPOSED FOLLOW-UP: just check lint (symvision) currently errors on private imports in src/sase/finalizers/declaration.py (_load_latest_context and siblings). Unrelated to this CLI phase.

[2026-08-21T17:32:37Z · sase-rs.4] Added sorted sase flag enable/disable on set_saved_feature_flag with rich+JSON (mutation/restart), AXE restart_after_update source attribution, skipped-not-running, partial success on restart failure, unknown-flag exit 2, and reused flag_key completion. Regenerated cli_spec.json. Verified pytest tests/feature_flags/test_cli_set.py, test_cli.py, test_state.py, tests/completion/test_snapshot.py and flag_key kinds, parser default/help tests, ruff+mypy, check_feature_flags --static, and sase flag {enable,disable} --help. epic-symbols sase-rs.4: no leftovers. just check did not finish green (orphan flag beads sase-rc/sase-ro; unrelated full-suite failures) — recorded as PROPOSED FOLLOW-UP.

[2026-08-21T17:34:17Z · sase-rs.4] Added sorted sase flag enable/disable on set_saved_feature_flag with rich+JSON (mutation/restart), AXE restart_after_update source attribution, skipped-not-running, partial success on restart failure, unknown-flag exit 2, and reused flag_key completion. Regenerated cli_spec.json. Verified pytest tests/feature_flags/test_cli_set.py, test_cli.py, test_state.py, tests/completion/test_snapshot.py and flag_key kinds, parser default/help tests, ruff+mypy, check_feature_flags --static, and sase flag {enable,disable} --help. epic-symbols sase-rs.4: no leftovers.

## Dependencies

- **Depends on:** [sase-rs.3](sase-rs.3.md) ✓ · ⧖ 2026-08-21
- **Blocks:** [sase-rs.6](sase-rs.6.md) ✓ · ⧖ 2026-08-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rs.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rs.4/README.md) | [sase-rs.4](sase-rs.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c3679dc`](https://github.com/sase-org/sase/commit/c3679dcf1e8118e8c2d5c5f4723b34c9469f76ce) | feat(flags): add persistent sase flag enable and disable commands | [sase-rs.4](sase-rs.4.md) | 2026-08-21 17:35:03 UTC |
