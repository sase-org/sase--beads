# Bead: sase-pq.4 — The gate detail pane and the gate review modal

[Bead Pages](../README.md) / [sase-pq](README.md) / sase-pq.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.060](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.060.md) · **Assignee:** `sase-pq.4` · **Size:** medium
**Created:** 2026-08-18 09:38:05 EDT · **Closed:** 2026-08-18 11:25:47 EDT
**Plan:** [202608/task\_type\_gate\_presentation.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_type_gate_presentation.md)

## Description

detail: render the declared chip as its own row in the notification modal's gate pane and in the custom gate review modal's header, from `action_data` only.

## Notes

[2026-08-18T15:25:29Z · sase-pq.4--1] PROPOSED FOLLOW-UP: check-full flake on test_on_alias_edited_offers_commit_when_in_repo — ConfirmActionModal on_mount missed #confirm-btn under the full suite; isolated rerun passed. Already tracked as sase-oh.

[2026-08-18T15:25:47Z · sase-pq.4--1] Gate pane renders a declared chip as its own row after _meta_row via gate_chip_from_action_data; chipless gates omit the row entirely. CustomGateModalData.chip is optional, loaded from action_data, and rendered between headline and kind title with rich.markup.escape. Junk color degrades to bold; no surface imports sase.task_types or sase.task_type_presentation. Removed Justfile --epic-symbol sase-pq.3(gate_chip_from_action_data); epic-symbols now empty. just check-full: 33232 passed, 13 skipped; one known flake (sase-oh) on test_on_alias_edited_offers_commit_when_in_repo which passed isolated. Chip-focused suites: 57 passed.

[2026-08-18T15:27:51Z · sase-pq.4--1] just check-full: 33232 passed, 13 skipped. Isolated flake tests/test_models_panel_edit_outcomes.py::test_on_alias_edited_offers_commit_when_in_repo (#confirm-btn miss, already sase-oh) reran green. Chip suites 57 passed (gate pane, custom modal, custom-gate loader). Epic-symbols empty after dropping Justfile --epic-symbol sase-pq.3(gate_chip_from_action_data). Chipless gates omit the row; junk color degrades to bold; no task_types imports.

## Dependencies

- **Depends on:** [sase-pq.1](sase-pq.1.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pq.7](sase-pq.7.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pq.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-pq.4.md) | [sase-pq.4](sase-pq.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8786a35`](https://github.com/sase-org/sase/commit/8786a35717f7e9b67641e6234bf495418885b2d9) | feat(tui): show declared gate chips on pane and review modal | [sase-pq.4](sase-pq.4.md) | 2026-08-18 11:30:05 EDT |
