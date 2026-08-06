# Bead: sase-gi.4 — INSERT-mode Tab and Shift+Tab nesting for ordered items

[Bead Pages](../README.md) / [sase-gi](README.md) / sase-gi.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ub](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ub/README.md) · **Assignee:** `sase-gi.4` · **Size:** medium
**Created:** 2026-08-06 15:23:10 EDT · **Closed:** 2026-08-06 16:35:01 EDT
**Plan:** [202608/prompt\_ordered\_lists.md](https://github.com/sase-org/sase--plans/blob/main/202608/prompt_ordered_lists.md)

## Description

shift: make Tab nest an ordered item under its parent at that parent's content column (starting a nested list at 1) and Shift+Tab unnest it into the enclosing run, renumbering both the source and destination runs and moving the item's owned block with it.

## Notes

[2026-08-06T20:34:27Z · sase-gi.4] PROPOSED FOLLOW-UP: tests/ace/tui/util/test_stall_watchdog.py::test_watchdog_keeps_hitch_and_stall_state_machines_independent is load-flaky — it failed under the parallel just check run and passed in isolation; unrelated to ordered-list work.

[2026-08-06T20:35:01Z · sase-gi.4] Added plan_prompt_ordered_shift (nest to parent content column starting nested runs at 1, unnest into enclosing run taking the next number), moving the item's owned block and renumbering both source and destination runs as one TextEdit undo checkpoint; wired it ahead of plan_prompt_bullet_shift in INSERT-mode Tab/Shift+Tab and fixed dot-capture remap for range-replacing plans. Verified: 32 new tests in tests/ace/tui/widgets/test_prompt_ordered_shift_editing.py pass (markers, delimiters, owned blocks, formatter fixed-point, single-undo, snippet-tabstop precedence, no-op cases); just check lint gates all green after dropping the now-satisfied sase-gi.2(plan_ordered_list_edit) and sase-gi.4(find_ordered_run) symvision epic-symbol entries; scoped suite 26226 passed with one unrelated load-flaky stall-watchdog test that passes in isolation (noted as follow-up).

## Dependencies

- **Depends on:** [sase-gi.1](sase-gi.1.md) ✓ · ⧖ 2026-08-06
- **Blocks:** [sase-gi.7](sase-gi.7.md) ✓ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gi.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gi.4/README.md) | [sase-gi.4](sase-gi.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`686bd5f`](https://github.com/sase-org/sase/commit/686bd5f5165734e719f7809fdc0f0f0b15444102) | feat(ace-tui): nest and unnest ordered prompt items with Tab and Shift+Tab | [sase-gi.4](sase-gi.4.md) | 2026-08-06 16:36:00 EDT |
