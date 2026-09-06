# Bead: sase-x7.2.1.3 — Build the dry-run, apply, journal, and operation catalog

[Bead Pages](../README.md) / [sase-x7.2.1](sase-x7.2.1.md) / sase-x7.2.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-x7.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-x7.2.md) · **Assignee:** `sase-x7.2.1.3` · **Size:** medium
**Created:** 2026-09-05 19:32:05 EDT · **Closed:** 2026-09-05 23:04:57 EDT
**Plan:** [202609/migration\_kit.md](https://github.com/sase-org/sase--plans/blob/main/202609/migration_kit.md)

## Description

kit-driver: Add `sase migrate list|plan|resume|run|status|verify`, the operation catalog with the four shipped operations, digest-gated apply, idempotent re-apply, durable journal-based resume, conflict refusals, bounded locks, atomic same-filesystem writes, symlink containment, and the startup-isolation guard.

## Notes

[2026-09-06T02:40:11Z · sase-x7.2.1.3] PROPOSED FOLLOW-UP: Stabilize full-suite flakes under xdist - repeated packaging-triggered `just check` full-suite escalations failed on unrelated TUI/cache tests that passed when rerun directly: prompt_panel_section_navigation fold-only anchor, agents_panel_fold_mounted patch isolation, axe_status_read_cache mtime invalidation.

[2026-09-06T03:04:29Z · sase-x7.2.1.3--1] PROPOSED FOLLOW-UP: Fix ACE link-follow global leak detector poisoning - monitored just check-full eg9wdjhm5xty completed pytest with 38779 passed and 14 skipped, then failed only the SASE global leak detector on 26 poisoning entries from tests/ace/tui/test_link_follow*.py and test_link_trail.py mutating sase.ace.tui.actions.link_follow._link_follow_outcomes; direct rerun passed with 'uv run pytest tests/ace/tui/test_link_follow.py tests/ace/tui/test_link_follow_hydration.py tests/ace/tui/test_link_follow_ladder.py tests/ace/tui/test_link_trail.py -q' reporting 52 passed in 1.18s.

[2026-09-06T03:04:57Z · sase-x7.2.1.3--1] Verified migration kit driver implementation with focused lane: uv run pytest tests/migration_kit tests/main/test_migrate_parser.py tests/main/test_parser_command_defaults.py tests/main/test_migrate_startup_isolation.py tests/test_check_sase_core_rs_bindings_tool.py -q. Monitored just check-full eg9wdjhm5xty ran all lint gates successfully and completed pytest with 38779 passed, 14 skipped; it failed only the SASE global leak detector on unrelated ACE link-follow global poisoning, which was recorded as a PROPOSED FOLLOW-UP after direct rerun of the affected modules passed with 52 passed in 1.18s. epic-symbols reported no entries.

## Dependencies

- **Depends on:** [sase-x7.2.1.2](sase-x7.2.1.2.md) ✓ · ⧖ 2026-09-05
- **Blocks:** [sase-x7.2.1.4](sase-x7.2.1.4.md) ◐ · ⧖ 2026-09-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-x7.2.1.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-x7.2.1.3.md) | [sase-x7.2.1.3](sase-x7.2.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bea92ce`](https://github.com/sase-org/sase/commit/bea92ce9287cec7250384a1fe88ba4fdcca4932b) | feat(migration-kit): add driver operation catalog | [sase-x7.2.1.3](sase-x7.2.1.3.md) | 2026-09-05 23:06:11 EDT |
