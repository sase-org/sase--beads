# Bead: sase-1eu.5 — Agents deck three panels behind the three\_pane\_splits beta flag

[Bead Pages](../README.md) / [sase-1eu](README.md) / sase-1eu.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ve](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ve.md) · **Assignee:** `sase-1eu.5` · **Size:** medium
**Created:** 2026-10-02 11:33:57 EDT · **Closed:** 2026-10-02 18:44:40 EDT
**Plan:** [202610/three\_pane\_splits.md](https://github.com/sase-org/sase--plans/blob/main/202610/three_pane_splits.md)

## Description

deck-three-panels: create the three_pane_splits beta flag and, behind it, enable the third deck panel: nest, turn and erase, fit refusal toasts, MRU picker target with position glyphs, 3-of-3 zoom chrome, additive persistence, a three-panel footer, a j/k perf check and T-shape goldens.

## Notes

[2026-10-02T20:20:37Z · sase-1eu.5] deck-three-panels implemented behind three_pane_splits beta (flag bead sase-1ey): nest/erase/turn via press_split nest=True in decks/layout.toggle_split; DeckPanel(2) composed hidden with widget identity kept and 3-to-2 closes hiding without unmount; MIN 8x40 fit guard with ctrl+s-collapse hint toasts (split keys and ctrl+t); MRU picker hint with position glyph; 3-of-3 zoom chip; ^F/^B panel three-panel footer; additive v1 pair persistence with old-reader truncation and flag-off load truncation. Tests: new test_deck_three_panels (25 pass), picker/persistence/footer suites green (198 pass), symvision clean (consumed fits+Pair, Justfile entries removed), 6 new T-shape/zoom/picker goldens created and check-clean with zero drift in 13 existing deck goldens. Perf probe (pilot.press j round-trip, harness-dominated): two-panel p50 45.2ms/p95 45.6ms vs three-panel p50 43.3ms/p95 44.0ms — parity, no regression. PROPOSED FOLLOW-UP: proper SASE_TUI_PERF deck-panel j/k bench scenario (2 vs 3 visible panels) asserting the 16ms p95 budget; current suites have no deck-panel key-to-paint scenario.

[2026-10-02T22:44:22Z · sase-1eu.5--1] PROPOSED FOLLOW-UP: full just check (run 40273fef0363a073f4b6a66931adee00) showed 5 unrelated NEW failures that all pass in isolation on this tree — test_global_state_leak_detector/report_only, tool/test_demand_runs/foreground_run_records, test_alias_history_modal/modal_bucket, pager/test_link_scan/stays_fast, plugins_browser_pane_loading/manual_update — likely load/order flakes under 56m full-check load, needs clean-base comparison by land agent

[2026-10-02T22:44:40Z · sase-1eu.5--1] deck-three-panels behind three_pane_splits verified: 3 deck failures from full check were mine and fixed (compose-tree now expects 3 hidden-composed panels; 2 picker hints updated for position glyphs ◧/⬓); 43 related tests pass plus full picker+panels files 29 pass; 5 unrelated NEW failures pass solo (recorded as PROPOSED FOLLOW-UP); epic-symbols clean

## Dependencies

- **Depends on:** [sase-1eu.4](sase-1eu.4.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1eu.7](sase-1eu.7.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1eu.8](sase-1eu.8.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eu.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eu.5.md) | [sase-1eu.5](sase-1eu.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`eb0440c`](https://github.com/sase-org/sase/commit/eb0440c7e8e99e8417a73c2153c668e8913fcb74) | feat(agents-deck): three panels behind three\_pane\_splits beta flag (sase-1eu.5) | [sase-1eu.5](sase-1eu.5.md) | 2026-10-02 18:46:28 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eu.5--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eu.5.md

<!-- sase:referenced-by:end -->
