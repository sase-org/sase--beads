# Bead: sase-1se.2 — Healer ledger keys derive the project from the canonical artifact path parser

[Bead Pages](../README.md) / [sase-1se](README.md) / sase-1se.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1bq](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1bq.md) · **Assignee:** `sase-1se.2` · **Size:** small
**Created:** 2026-11-12 06:15:58 EST · **Closed:** 2026-11-12 07:06:02 EST
**Plan:** [202611/auto\_restart\_update\_skew\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/auto_restart_update_skew_fixes.md)

## Description

ledger-project-key: `_target_for_artifacts_dir` derives the ledger project via `parse_agent_artifact_path` instead of `parents[1].name`, so day-sharded ace-run rows key as `<project>__<lineage>` and the at-most-once guarantee holds across both healer enumeration sources.

## Notes

[2026-11-12T12:05:39Z · sase-1se.2] PROPOSED FOLLOW-UP: just check test-scoped lane has 1 pre-existing failure in tests/test_preprocessing_code_blocks.py::TestPreprocessPromptCodeBlockProtection::test_text_outside_code_blocks_still_processed, reproduced identically on the clean base tree with this phase stashed (unrelated to ledger-project-key; preprocessing prompt code blocks, not auto-restart).

[2026-11-12T12:06:02Z · sase-1se.2] ledger-project-key done: _target_for_artifacts_dir (healer_targets.py, new _project_for_artifacts_dir helper) and _project_for_done (history.py) now resolve the ledger project via parse_agent_artifact_path, keeping the parents[1].name/parent.name chain only as fallback when parsing returns None; stale-record decision honored (no migration). New test_day_sharded_target_keys_match_scan_project proves a day-sharded row keys <project>__<stamp> on both doorbell and scan passes (same ledger record, no double-claim) plus legacy-layout green. Verified: focused healer/scan/layout suites 52 passed; sase tool run check b493ad6b lint gates all green, 60863 passed with 1 failure in test_preprocessing_code_blocks (proven pre-existing on clean base, recorded as PROPOSED FOLLOW-UP). No epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-1se.3](sase-1se.3.md) ◐ · ⧖ 2026-11-12
- **Blocks:** [sase-1se.4](sase-1se.4.md) ◐ · ⧖ 2026-11-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1se.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1se.2/README.md) | [sase-1se.2](sase-1se.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f613149`](https://github.com/sase-org/sase/commit/f613149ecce25f785f4539e023d7db9bcbfc01ed) | fix(auto\_restart): derive healer ledger project from canonical artifact path | [sase-1se.2](sase-1se.2.md) | 2026-11-12 07:08:22 EST |
