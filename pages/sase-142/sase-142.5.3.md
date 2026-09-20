# Bead: sase-142.5.3 — Stop applies that change no rendered row from repainting

[Bead Pages](../README.md) / [sase-142.5](sase-142.5.md) / sase-142.5.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-142.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-142.land.md) · **Assignee:** `sase-142.5.3` · **Size:** medium
**Created:** 2026-09-20 17:09:30 EDT
**Plan:** [202609/reachable\_row\_insert.md](https://github.com/sase-org/sase--plans/blob/main/202609/reachable_row_insert.md)

## Description

quiet-applies: scope each panel's paint key to its own rows so a fold-count change in one panel stops repainting the others, settle the agent-list column in-frame when a removal collapses a panel, and re-measure the residual same-occupancy rebuilds by reason.

## Notes

[2026-09-20T23:21:01Z · sase-142.5.3] Same-occupancy rebuild re-measurement over a fresh local capture (frame harness, 11 windows post-change): display_panel_rebuild by reason = status_membership_change x3 (2x sibling bucket reorder with unchanged occupancy, both necessary; 1x @default emptied, occupancy changed), workflow_tree_change x1 (second clan container, occupancy changed), width_growth x1 (wide arrival, occupancy changed); display_full_rebuild x0; cross-panel same-occupancy rebuilds 0; unchanged-apply repaints 0 (noop/starting/starting_narrow record no update_list/render_collapsed). Prediction for reverify-arrivals-on-athena: the sase-142.4 residue class (21/50 rebuilds where one panel change rebuilt siblings) should read ~0; remaining same-occupancy rebuilds should be only bucket moves inside the concerned panel plus insert declines (width_growth, clan/workflow shapes, sase-142.5.2 domain) plus rare full-rebuild fallbacks (search/stale-mode).

[2026-09-20T23:21:26Z · sase-142.5.3] PROPOSED FOLLOW-UP: try_remove_rows leaves _content_requested_width stale - removing the widest row in place never shrinks the column until the next full update_list (observed: @epic still requesting 180 after its wide row left, column pinned at the 130 clamp); quiet-applies settled only the collapse branch, so in-place removals that shrink a panel need their own width re-measure

[2026-09-20T23:21:58Z · sase-142.5.3] PROPOSED FOLLOW-UP: marked/unread sets are still global entries in _panel_paint_key, so marking or reading an agent in one panel repaints every sibling panel; quiet-applies scoped only the fold inputs (fold_counts, visible/fully-expanded parent keys), and the mark sets want the same per-panel treatment

## Dependencies

- **Depends on:** [sase-142.5.1](sase-142.5.1.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-142.5.4](sase-142.5.4.md) ◐ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-142.5.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-142.5.3/README.md) | [sase-142.5.3](sase-142.5.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8464f4b`](https://github.com/sase-org/sase/commit/8464f4bcb011a7976094fa25dd72c42fa0c323d3) | fix(tui): scope panel paint keys per panel and settle removal collapses in-frame | [sase-142.5.3](sase-142.5.3.md) | 2026-09-20 19:26:43 EDT |
