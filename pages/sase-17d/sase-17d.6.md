# Bead: sase-17d.6 — Retarget detail actions to the focused deck panel

[Bead Pages](../README.md) / [sase-17d](README.md) / sase-17d.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qd](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qd.md) · **Assignee:** `sase-17d.6` · **Size:** large
**Created:** 2026-09-23 19:16:52 EDT · **Closed:** 2026-09-24 08:49:28 EDT
**Plan:** [202609/agents\_tab\_decks\_and\_cards.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_decks_and_cards.md)

## Description

deck-action-retarget: inventory every consumer of the legacy panel ids and visibility helpers, then give each one a deck-mode path. Covers folds, hints, search, E, LLM detail levels, clipboard, footer, palette context and auto-refresh, and makes the SLOW TOOL CALLS hint accurate.

## Notes

[2026-09-24T12:49:28Z · sase-17d.6] deck-action-retarget implemented. Consumer inventory (DONE=pre-existing deck path, THIS=fixed here, CUTOVER=flag-off-only): _agent_detail_panels DONE/CUTOVER; _agent_view_picker+modal DONE/CUTOVER; is_file/llm/metadata_visible+effective_scroll DONE; refresh_current_file THIS (refreshes every FILES panel); get_editor_file_info THIS (+Main active-card branch via DeckPanel.active_main_card); get_current_image_path THIS (via focused_file_view); _llm_calls_panel_or_none THIS (focused Tools only); _agent_detail_display DONE; agent_detail compose/on_mount/toggle_header (toggle uses reapply_main_view_pins) DONE; _agent_detail_jump sink DONE; toggle_jump_panel_expanded THIS (reapply_main_view_pins); _deck_source_panel DONE; nav scroll/top/bottom DONE; scroll_prompt/section-stop DONE/CUTOVER; fold _current_agent_metadata_section_id THIS (main_view_for_actions; notify when no Main); _selected_lane_has_* DONE; metadata search THIS (per-panel overlay: DeckPanel search scroll/panel/command + show/hide + accessors, decks/search_corpus.py, _deck_search_host.py panel capture + structural exit keys from live keymap); panel_detail zoom DONE/CUTOVER (Z untouched); action_edit_panel THIS (via get_editor_file_info); folding _route_llm_calls_detail_level THIS (focused_tools_view gate; h collapse-first and L max-first in deck mode); clipboard _copy_file_path + warm_agent_file_path THIS (focused_file_view); clipboard core footer DONE; display_detail_footer file DONE, llm THIS (focused_tools_view); commands/context DONE; auto_refresh gate DONE + refresh_current_file THIS; file/llm app-wide scroll fallback CUTOVER; slow_tools overflow THIS (slow_tool_overflow_hint + resolve_slow_tool_overflow_keys threaded via overflow_hint_keys, flag read at render time); prompt_document DONE; styles legacy ids CUTOVER + new .deck-search-* CSS. Deviation: legacy #agent-search-* widgets kept in deck compose branch ( helpers _clear/_show/_hide_metadata_scrolls still query them), recorded as CUTOVER. Verified: 23 new tests pass (test_deck_action_targets, test_deck_search_overlay, updated test_agent_slow_tools incl. per-branch helper tests); flag-off regression suites pass (test_agent_metadata_search, test_agents_zoom_panel_search, test_agent_fold_transitions_llm_calls, all decks tests: 108 passed); just fix clean; epic-symbols clean; no golden contains the old overflow string. NOT run: flag-on search-overlay PNG golden, live sase screenshot with agent_decks=true, visual snapshot suite. PROPOSED FOLLOW-UP: add LEFT_RIGHT split committed-search overlay golden + live screenshot inspection.

## Dependencies

- **Depends on:** [sase-17d.5](sase-17d.5.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-17d.8](sase-17d.8.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17d.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17d.6.md) | [sase-17d.6](sase-17d.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7d22725`](https://github.com/sase-org/sase/commit/7d2272588839582b01bcdeb789a26708ed0f1b8d) | feat(ace): retarget agents detail actions to focused deck panel | [sase-17d.6](sase-17d.6.md) | 2026-09-24 09:17:42 EDT |
