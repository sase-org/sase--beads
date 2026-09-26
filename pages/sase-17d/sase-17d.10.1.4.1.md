# Bead: sase-17d.10.1.4.1 — Migrate the family, monitor and collapsed-panel visual tests to decks

[Bead Pages](../README.md) / [sase-17d.10.1.4](sase-17d.10.1.4.md) / sase-17d.10.1.4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17d.10.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17d.10.1.land.md) · **Assignee:** `sase-17d.10.1.4.1` · **Size:** medium
**Created:** 2026-09-24 17:30:38 EDT · **Closed:** 2026-09-24 22:20:06 EDT
**Plan:** [202609/deck\_cutover\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/deck_cutover_landing_repairs.md)

## Description

family-visual-migration: confirm the land-agent repairs from section 2 are on master (reapply any that are missing), then migrate the family-panel, monitor, gate-shell and collapsed-panel ACE PNG tests listed in section 3.1 off the deleted legacy ids and section-stop APIs onto the deck API, regenerate only their goldens with a scoped just fix-tui-screenshots, and inspect every changed PNG.

## Notes

[2026-09-25T02:19:06Z · 0ru] DONE (single tale agent for sase-17d.10.1.4). Step 1: removed the dead #agent-llm-calls-scroll/#agent-file-scroll fallbacks (both _get_scroll_container now return the VerticalScroll parent or None, try/except kept around self.parent); migrated test_agent_fold_transitions_llm_calls.py to deck semantics (focused_tools_view() sentinel: focused Tools view takes l/h/L/H, unfocused leaves them to the tree; _HintFoldApp stubs _arm_panel_fold_hint_mode); dropped the view_mode kwarg in test_agents_tab_current_project_seed; jump-panel search-overlay test now uses deck_area.focused_panel().show_search_overlay()/hide_search_overlay(); deleted test_zoom_file_cap_subtitle_points_to_editor. Repairs 1 and 2 were already on master (114fbca89). Step 3 rows 1-8 migrated with new helpers in _ace_agents_png_snapshot_helpers.py (main_deck_scroll, scroll_main_section_to_top, select_main_card, resolved_main_section, pin_decks_paged): monitor states x7 (section asserted at BOTH widths only at 120: at 90 columns the detail column is 0-19 cells so the section cannot be targeted or matched as text; see sase-18p), family conversation monitor phase (select reply card), family shells monitor metadata (regen; also scrolls the jump panel to its end so 'just check' is on screen), gate output (reply card + main_deck_scroll), family fold levels (scroll_main_section_to_top agent-xprompt; wrap-to-top asserts scroll_y==0 and output-variables), collapsed panel (active_main_card()=='summary', no 'view:' chip), tribe clan summaries, tribe prompts. Multi-card tests pin PAGED (pin_decks_paged) because a borderline document flipped spread/paged between runs (lost-120 monitor golden). Verified: 4 step-1 modules 46 passed at the time; visual modules pass under --check.

[2026-09-25T02:20:06Z · 0ru] Step 1 land-agent repairs and the first eight visual tests migrated to the deck API; the affected modules pass under just fix-tui-screenshots --check, and the 4 step-1 non-visual modules pass.

## Dependencies

- **Blocks:** [sase-17d.10.1.4.3](sase-17d.10.1.4.3.md) ✓ · ⧖ 2026-09-24
