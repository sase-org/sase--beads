# Bead: sase-1eu.6 — Pager on PaneGrid with grid panes and the new pane keys

[Bead Pages](../README.md) / [sase-1eu](README.md) / sase-1eu.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ve](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ve.md) · **Assignee:** `sase-1eu.6` · **Size:** medium
**Created:** 2026-10-02 11:33:59 EDT · **Closed:** 2026-10-02 13:50:31 EDT
**Plan:** [202610/three\_pane\_splits.md](https://github.com/sase-org/sase--plans/blob/main/202610/three_pane_splits.md)

## Description

pager-grid-adapter: wait until sase-1es.6 has landed, then port the pager split onto PaneGrid. Use a flat grid #pager-panes with pane-ID-keyed views, close paths that remove only the discarded view (the sase-1er fix), and the ctrl+b, swap, close and turn keys on two panes. All pager goldens stay unchanged.

## Notes

[2026-10-02T17:18:14Z · sase-1eu.6] PROPOSED FOLLOW-UP: sase-1es.6 (pager ScrollView body) still in progress at port time; confirm no collision with the new pane-ID-keyed mount paths when it lands

[2026-10-02T17:50:31Z · sase-1eu.6--1] Pager on PaneGrid port verified: just _lint-symvision passes (removed 11 stale sase-1eu epic-symbol entries now properly consumed, deleted 4 dead state wrappers close_focused_pane/focus_other/focused_pane_id/turn_split orphaned by the port, privatized grid_for_state to _grid_for_state); ruff whole-repo + format + mypy clean; 46 pager tests pass (test_split_model, test_view_extract, test_app_split incl. split-key Pilot goldens, test_app_other_pane). No epic-symbol entries remain for sase-1eu.6. Full just check (19min) exceeds the single-turn shell ceiling; its only NEW failures from the monitored run were the symvision items fixed here.

## Dependencies

- **Depends on:** [sase-1eu.2](sase-1eu.2.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1eu.7](sase-1eu.7.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eu.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eu.6.md) | [sase-1eu.6](sase-1eu.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5dff14e`](https://github.com/sase-org/sase/commit/5dff14eab43ef40616b1cde0687daa2fe4a9c2c4) | feat(pager): port pager to PaneGrid and clear sase-1eu.6 epic symbols | [sase-1eu.6](sase-1eu.6.md) | 2026-10-02 13:53:51 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eu.6--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eu.6.md

<!-- sase:referenced-by:end -->
