# Bead: sase-1i5.8 — Get under the TUI import budget and make it a ratchet (sase-13p)

[Bead Pages](../README.md) / [sase-1i5](README.md) / sase-1i5.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0y8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0y8.md) · **Assignee:** `sase-1i5.8` · **Size:** medium
**Created:** 2026-10-08 09:47:21 EDT · **Closed:** 2026-10-08 14:15:44 EDT
**Plan:** [202610/close\_top\_ten\_impact\_task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202610/close_top_ten_impact_task_beads.md)

## Description

import-budget: defer eager TUI startup imports to at least 30 modules under the cap, lower the cap to measured plus 20, add an attribution tool, document the ratchet policy, and close sase-13p.

## Notes

[2026-10-08T17:05:20Z · sase-1i5.8] PROPOSED FOLLOW-UP: tests/ace/tui/models/test_agent_associated_plan_cache.py has 2 pre-existing failures (frontmatter mtime-cache nodes) that reproduce identically on the clean base tree with this phase stashed; unrelated to the import-budget work

[2026-10-08T18:15:25Z · sase-1i5.8--2] Import-budget measurements: before 3582 modules at planning (3585 at HEAD~3 6f930e16 via tools/tui_import_closure --diff HEAD~3), after 3493 modules (2782 sase.*, 1.94-2.17s CPU) via tools/tui_import_closure; delta -89 to -92. Cap lowered 3570 to 3513 (measured plus 20, strict <), 77 below old cap and 47 below the 3540 deferral target. tests/ace/tui/test_app_import_budget.py passes in isolation (1 passed in 5.98s); tools/typecheck_extensionless_tools passes (60 files); mypy clean on src/sase/main/artifact_handler.py.

[2026-10-08T18:15:33Z · sase-1i5.8--2] PROPOSED FOLLOW-UP: just check (monitor 117fm5v95wec, tool run 3160c115b37a885b3b46afdaf2ce2e29) exits 1 with verdict no_new_failures — 57 KNOWN (48 symvision unused-public findings with base witnesses plus 9 test failures: test_finalizers_discard_guard_before_head 1, test_bead_fast_path 3, test_macro_terminology 1, test_agent_associated_plan_cache 2 already noted, test_plan_gates_execution 1, test_notification_plan_gate 1). None is introduced by the import-budget deferrals; triage labels each KNOWN with a base witness. Route to the owning beads or master-CI repair.

[2026-10-08T18:15:44Z · sase-1i5.8--2] import-budget done: TUI closure 3493 modules (was 3582, -89; 77 below old 3570 cap), cap ratcheted to 3513 (measured+20, strict <), tools/tui_import_closure added with -d/--diff and documented in docs/perf_runbook.md, deferred heavy edges probed in test. Verified: test_app_import_budget passes in isolation, typecheck_extensionless_tools clean (60 files), mypy clean, tui_import_closure --diff HEAD~3 shows -92 modules with worktree cleanup. just check verdict no_new_failures (57 KNOWN with base witnesses, recorded as PROPOSED FOLLOW-UP); sase-13p already closed done; epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1i5.5](sase-1i5.5.md) ✓ · ⧖ 2026-10-08
- **Depends on:** [sase-1i5.7](sase-1i5.7.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1i5.9](sase-1i5.9.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1i5.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1i5.8.md) | [sase-1i5.8](sase-1i5.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`af117b5`](https://github.com/sase-org/sase/commit/af117b598e141370da52565a0af89bf6223af843) | feat(tui): enforce app import budget with closure tool and ratcheted cap | [sase-1i5.8](sase-1i5.8.md) | 2026-10-08 14:17:58 EDT |
