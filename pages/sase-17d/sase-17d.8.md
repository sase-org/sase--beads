# Bead: sase-17d.8 — Spread versus paged rendering

[Bead Pages](../README.md) / [sase-17d](README.md) / sase-17d.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qd](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qd.md) · **Assignee:** `sase-17d.8` · **Size:** large
**Created:** 2026-09-23 19:16:54 EDT · **Closed:** 2026-09-24 10:00:05 EDT
**Plan:** [202609/agents\_tab\_decks\_and\_cards.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_decks_and_cards.md)

## Description

deck-spread-mode: adds the ace.agent_decks.spread_max_screens config and a pure decide_render_mode with hysteresis. Measures cheap lower bounds first, renders Main and Files spread with titled separators and card anchors, and keeps the reading position stable across transitions.

## Notes

[2026-09-24T13:41:13Z · sase-17d.8] PROPOSED FOLLOW-UP: Panel.py is 972 lines (warning, under 1000 hard limit); split remaining Files probe orchestration from panel.py into panel_spread.py to get under ~500.

[2026-09-24T13:41:47Z · sase-17d.8] PROPOSED FOLLOW-UP: Add PNG goldens for spread Main, spread Files, and paged-after-threshold via targeted just fix-tui-screenshots and inspect every image.

[2026-09-24T13:42:18Z · sase-17d.8] PROPOSED FOLLOW-UP: Live TUI screenshots with SASE_FEATURE_FLAGS agent_decks (single spread Main, split spread/paged, spread Files) were not captured this turn; inspect separator styling and title-pill tracking.

[2026-09-24T13:43:02Z · sase-17d.8] IMPLEMENTATION NOTE: metadata_identity already includes the attempt pin (agent, identity, attempt_number), so _on_main_document needs no subject change; hint toggles and refreshes keep the same subject. No deck search corpus builder exists yet (legacy search disabled when decks on), so Main active_card_id stays scroll-derived in spread and Files spread shows all pages for future search.

[2026-09-24T13:43:33Z · sase-17d.8] VERIFICATION: ruff+ mypy pass; 131 decks+schema tests pass; 79 file_panel tests pass; 17 section-navigation tests pass. just lint symvision fails on pre-existing unrelated private imports (no deck/spread symbols flagged). bench_tui_jk has 6 pre-existing failures in this env; before/after p95 not recorded.

## Dependencies

- **Blocks:** [sase-17d.10](sase-17d.10.md) ✓ · ⧖ 2026-09-23
- **Depends on:** [sase-17d.6](sase-17d.6.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17d.8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17d.8.md) | [sase-17d.8](sase-17d.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`329d404`](https://github.com/sase-org/sase/commit/329d4049b6f61467f5a97006346f0b487b994ee8) | feat(ace): implement deck spread versus paged rendering (sase-17d.8) | [sase-17d.8](sase-17d.8.md) | 2026-09-24 09:53:14 EDT |
