# Bead: sase-gz.4 — Render icons in the tab strip and indicator

[Bead Pages](../README.md) / [sase-gz](README.md) / sase-gz.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ui.w1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ui.w1/README.md) · **Assignee:** `sase-gz.4` · **Size:** medium
**Created:** 2026-08-07 10:28:58 EDT · **Closed:** 2026-08-07 11:58:17 EDT
**Plan:** [202608/notification\_tab\_icons.md](https://github.com/sase-org/sase--plans/blob/main/202608/notification_tab_icons.md)

## Description

render: draw the icon in the modal tab strip and in every indicator chip, replace the snoozed `z` suffix with its glyph, and make every width measurement cell-aware so a two-cell icon cannot desync tab click ranges or tooltip alignment.

## Notes

[2026-08-07T15:47:34Z · sase-gz.4] PROPOSED FOLLOW-UP: give the visual-snapshot rasterizer a symbol fallback font — tests/ace/tui/visual/fonts holds only Fira Code 6.2 with skip_system_fonts=True, and that font lacks ⚑ ✖ ◈ ✉ ☾ ⊘ (and every listed alternate but ◆ ▪ # •), so the notification tab-icon goldens rasterize those glyphs as replacement boxes and the plan_s "glyph audit" cannot actually detect tofu. The indicator_s ✉ has rendered as a box in committed goldens since long before this epic.

[2026-08-07T15:47:52Z · sase-gz.4] PROPOSED FOLLOW-UP: the notification modal_s tag strip clips at the widget width (43 cells in the 120x40 fixture) with no overflow affordance — adding a per-tab icon pushed the fourth tab ("Done") off screen in notification_beads_tab_120x40. Consider a +N overflow marker, horizontal scroll, or label shortening so hidden tabs are at least discoverable.

[2026-08-07T15:48:34Z · sase-gz.4] PROPOSED FOLLOW-UP: six bead-snooze tests fail on master independently of this epic — test_cli_snooze.py (4), test_snooze_gate.py::test_bead_snooze_gate_preview_carries_the_real_snooze_note, and test_snooze_lifecycle.py::test_snooze_round_trips_through_every_persistence_surface. Verified failing at HEAD 34928a454 with this phase_s tree stashed; likely fallout from 8865cf54d "test(bead): pin the snooze note contract".

[2026-08-07T15:55:48Z · sase-gz.4] PROPOSED FOLLOW-UP: three Config Center edit goldens (config_center_edit_enum/modal/normal_mode_120x40) were stale on master before this epic — commit 02758f8f1 changed the field-tree footer hints without regenerating them, so just test-visual failed on them at HEAD 34928a454. This phase regenerated the whole PNG suite for the reshaped top-bar badge and picked those three up incidentally; the drift itself was not caused here.

[2026-08-07T15:58:17Z · sase-gz.4] Rendered tab icons in the indicator and the modal tab strip. Indicator chips are now <icon><count> joined by single spaces, with the leading ✉ anchor and the dim · separators dropped from every populated branch; ✉ 0 is unchanged for the empty state; the snoozed-only badge is ☾<N> in dim tab color instead of <N>z; +K overflow keeps its dim style. The tooltip prefixes each line with its icon and pads both the icon and label columns with rich.cells.cell_len. The tag strip renders "<icon> <Label> <count>" with the icon in the tab color (dim when inactive) and accumulates click ranges in terminal cells instead of characters — a two-cell icon no longer desyncs on_click from event.x. Verified: just lint exit 0; just test-scoped 26984 passed with 6 pre-existing bead-snooze failures reproduced at HEAD with this tree stashed (noted); just test-visual 419 passed, 1 skipped. Regenerated goldens: 382 modified, of which 377 differ only inside the top-bar badge band and 2 also inside the notification tab strip; the remaining 3 (config_center_edit_*) were already stale on master from 02758f8f1 and are noted. Added 3 new goldens covering built-in chips, kind-default chips, and the snoozed badge, plus a NotificationTagStrip regression test that clicks past a two-cell icon. Glyph audit finding: the snapshot rasterizer sees only the bundled Fira Code with system fonts skipped, and that font carries none of ⚑ ✖ ◈ ✉ ☾ ⊘ (nor any listed alternate but ◆ ▪ # •), so those rasterize as replacement boxes in goldens while rendering fine in a real terminal — the plan predates this and its claim that ✉ was proven against the fixture font is wrong (✉ has been a box in committed goldens all along). Glyph set kept as landed; noted as follow-up. Also dropped the now-unnecessary sase-gz.4 symvision --epic-symbol whitelist entry. SASE validation still reports the two pre-existing failures this phase does not own (memory README drift and the deliberately deferred sase_gate skill deploy).

[2026-08-07T15:59:06Z · sase-gz.4] Verified: just lint clean; just test-scoped passed (6 pre-existing bead-snooze failures reproduced at HEAD); just test-visual 419 passed, 1 skipped.

## Dependencies

- **Depends on:** [sase-gz.2](sase-gz.2.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-gz.6](sase-gz.6.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gz.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gz.4/README.md) | [sase-gz.4](sase-gz.4.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3867fe3`](https://github.com/sase-org/sase/commit/3867fe37c8419c5e46af869a0cb7ec5d4a9b9670) | feat(ace): render notification icons in the tab strip and indicator chips | [sase-gz.4](sase-gz.4.md) | 2026-08-07 12:00:14 EDT |
| sase | [`72a3ab9`](https://github.com/sase-org/sase/commit/72a3ab92c448eeb95131e2b0308e82df78aa5f5e) | test(ace): refresh Admin Center goldens for the notification badge | [sase-gz.4](sase-gz.4.md) | 2026-08-07 12:04:28 EDT |
