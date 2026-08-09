# Bead: sase-il.3 — Required tale size in sase-core

[Bead Pages](../README.md) / [sase-il](README.md) / sase-il.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wt](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wt/README.md) · **Assignee:** `sase-il.3` · **Size:** medium
**Created:** 2026-08-09 16:43:53 EDT · **Closed:** 2026-08-09 17:37:48 EDT
**Plan:** [202608/sase\_sizes\_memory.md](https://github.com/sase-org/sase--plans/blob/main/202608/sase_sizes_memory.md)

## Description

core-tale-size: require and validate a tale plan's `size` frontmatter in the sase-core plan validator, expose it on the wire, and release it.

## Notes

[2026-08-09T21:35:21Z · sase-il.3] PROPOSED FOLLOW-UP: Restore missing sase_sizes_memory design file — bead sase-il references plans:202608/sase_sizes_memory.md, but the opened plans sidecar lacks that file and has no history for it, so future phase workers cannot read the design context.

[2026-08-09T21:35:42Z · sase-il.3] PROPOSED FOLLOW-UP: Fix unrelated ACE artifacts navigation and commits timeline failures — focused rerun fails tests/ace/tui/test_artifacts_list_navigation.py::test_bugs_fast_navigation_restores_issue_focus_and_ignores_links, tests/ace/tui/test_artifacts_list_navigation.py::test_plans_fast_navigation_skips_document_section_headings, and tests/ace/tui/test_commits_pane_rendering.py::test_commits_timeline_mounted_rows_stay_one_line_with_jump_hints; these block broad just check after the plan-size changes are otherwise green.

[2026-08-09T21:37:48Z · sase-il.3] Verified cargo fmt --all; cargo test -p sase_core tale_size_is_required_strict_and_normalized; cargo test -p sase_core --test plan_validate_parity; cargo test -p sase_core_py plan_validation_bindings_round_trip_json_shapes; cargo test -p sase_core --lib plan::validate::tests; focused Python plan/approval/archive validation tests; just lint; and just validate-committed-plans. just check was attempted and reached broad pytest, but unrelated ACE artifacts/commits tests still fail and were recorded as PROPOSED FOLLOW-UP on this bead.

[2026-08-09T21:39:15Z · sase-il.3] Verified tale size enforcement with focused Rust/core binding tests, focused Python plan approval/archive/validation tests, just lint, and committed-plan validation; just check broad pytest lane was blocked by unrelated ACE failures recorded as follow-up.

## Dependencies

- **Blocks:** [sase-il.4](sase-il.4.md) ◐ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-il.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-il.3/README.md) | [sase-il.3](sase-il.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@3c10a0c`](https://github.com/sase-org/sase-core/commit/3c10a0cb7b8a222503440760f946b2cdfef15beb) | feat!: require tale size in core plan validation | [sase-il.3](sase-il.3.md) | 2026-08-09 17:41:09 EDT |
| sase--plans | [`sase--plans@97845e6`](https://github.com/sase-org/sase--plans/commit/97845e6e0c04dc551b67e2cf275da9a5bfb4f330) | chore(plans): backfill tale sizes for committed plans | [sase-il.3](sase-il.3.md) | 2026-08-09 17:42:23 EDT |
