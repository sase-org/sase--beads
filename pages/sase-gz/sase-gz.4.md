# Bead: sase-gz.4 — Render icons in the tab strip and indicator

[Bead Pages](../README.md) / [sase-gz](README.md) / sase-gz.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ui.w1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ui.w1/README.md) · **Assignee:** `sase-gz.4` · **Size:** medium
**Created:** 2026-08-07 10:28:58 EDT
**Plan:** [202608/notification\_tab\_icons.md](https://github.com/sase-org/sase--plans/blob/main/202608/notification_tab_icons.md)

## Description

render: draw the icon in the modal tab strip and in every indicator chip, replace the snoozed `z` suffix with its glyph, and make every width measurement cell-aware so a two-cell icon cannot desync tab click ranges or tooltip alignment.

## Notes

[2026-08-07T15:47:34Z · sase-gz.4] PROPOSED FOLLOW-UP: give the visual-snapshot rasterizer a symbol fallback font — tests/ace/tui/visual/fonts holds only Fira Code 6.2 with skip_system_fonts=True, and that font lacks ⚑ ✖ ◈ ✉ ☾ ⊘ (and every listed alternate but ◆ ▪ # •), so the notification tab-icon goldens rasterize those glyphs as replacement boxes and the plan_s "glyph audit" cannot actually detect tofu. The indicator_s ✉ has rendered as a box in committed goldens since long before this epic.

[2026-08-07T15:47:52Z · sase-gz.4] PROPOSED FOLLOW-UP: the notification modal_s tag strip clips at the widget width (43 cells in the 120x40 fixture) with no overflow affordance — adding a per-tab icon pushed the fourth tab ("Done") off screen in notification_beads_tab_120x40. Consider a +N overflow marker, horizontal scroll, or label shortening so hidden tabs are at least discoverable.

[2026-08-07T15:48:34Z · sase-gz.4] PROPOSED FOLLOW-UP: six bead-snooze tests fail on master independently of this epic — test_cli_snooze.py (4), test_snooze_gate.py::test_bead_snooze_gate_preview_carries_the_real_snooze_note, and test_snooze_lifecycle.py::test_snooze_round_trips_through_every_persistence_surface. Verified failing at HEAD 34928a454 with this phase_s tree stashed; likely fallout from 8865cf54d "test(bead): pin the snooze note contract".

## Dependencies

- **Depends on:** [sase-gz.2](sase-gz.2.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-gz.6](sase-gz.6.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gz.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gz.4/README.md) | [sase-gz.4](sase-gz.4.md) | 0 |
