# Bead: sase-p3.8 — Task-type chips on every bead surface

[Bead Pages](../README.md) / [sase-p3](README.md) / sase-p3.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05c.md) · **Assignee:** `sase-p3.8` · **Size:** medium
**Created:** 2026-08-17 18:50:06 EDT · **Closed:** 2026-08-18 02:15:02 EDT
**Plan:** [202608/task\_bead\_types.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_bead_types.md)

## Description

presentation: add the shared task-type presentation module with a distinct accent per type and route every CLI, ACE, bead-page, gate-preview, and helper surface through it.

## Notes

[2026-08-18T06:15:02Z · sase-p3.8] Added src/sase/task_type_presentation.py (shared per-type accent/glyph presentation module) and routed every CLI, ACE, bead-page, gate-preview, and mobile-helper surface through it. Verified: ruff format/check and mypy clean; 2128 targeted tests pass (tests/test_bead/, test_task_type_presentation.py, test_mobile_helper_beads.py, test_notification_tab_style.py, test_agent_display_bead_section.py); full ACE PNG visual suite (just test-visual) shows zero regressions vs the pre-existing master baseline (86 failing before and after, all unrelated to this phase) after regenerating the 8 PNG goldens affected by the new task-type chip (4 beads-surface snapshots plus 4 artifacts_split snapshots). epic-symbols check for sase-p3.8 returned no --epic-symbol entries.

## Dependencies

- **Blocks:** [sase-p3.13](sase-p3.13.md) ◐ · ⧖ 2026-08-17
- **Depends on:** [sase-p3.7](sase-p3.7.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p3.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p3.8/README.md) | [sase-p3.8](sase-p3.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1dc393a`](https://github.com/sase-org/sase/commit/1dc393a64647013fd936d31e8bfb9032be2780fa) | feat(task-types): add task-type chips across every bead surface | [sase-p3.8](sase-p3.8.md) | 2026-08-18 02:15:46 EDT |
