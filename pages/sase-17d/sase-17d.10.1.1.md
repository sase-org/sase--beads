# Bead: sase-17d.10.1.1 — Remove the agent\_decks flag and its Off branches

[Bead Pages](../README.md) / [sase-17d.10.1](sase-17d.10.1.md) / sase-17d.10.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17d.10](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17d.10.md) · **Assignee:** `sase-17d.10.1.1` · **Size:** large
**Created:** 2026-09-24 10:13:45 EDT · **Closed:** 2026-09-24 11:41:58 EDT
**Plan:** [202609/deck\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/deck_cutover.md)

## Description

deck-flag-removal: delete the agent_decks beta flag, make every deck On branch unconditional, delete each Off-branch body and the legacy compose branch, close flag bead sase-17k, remove the flag override wrappers in tests, and migrate or delete non-visual tests that exercised the flag-off UI. Legacy modules left unreachable stay in place for legacy-ui-deletion.

## Notes

[2026-09-24T15:41:43Z · sase-17d.10.1.1] deck-flag-removal done. Flag: deleted FeatureFlag.agent_decks + registry definition, widgets/decks/flag.py, schema block via sync_feature_flags_schema --write. Source: all On branches unconditional across agent_detail, _agent_detail_{state,panels,display,jump,decks,deck_targets}, prompt_panel/_agent_slow_tools, commands/{types,context,_availability_agents}, actions/{_panel_detail,_folding,_metadata_search,_display_detail_info,_display_detail_footer,_deck_layout_actions,_deck_persistence,_deck_search_host,_agent_view_picker}, navigation/{_basic,_fold}, hints/_files, clipboard/{_agents,_palette_helpers}, _app_action_availability, bindings + keymaps comments. Deleted _decks_active/_decks_persistence_active/_decks_layout_active wrappers and zoom modal helpers. Deleted tests: test_flag_off_compose_tree, test_flag_off_suite_unchanged, 9 view_picker p-blocked tests, test_zoom_seed_uses_textual_content_and_paints_file_panel, 12 legacy bottom-pin cases, 3 section-nav mounted tests, test_slow_tool_overflow_hint_decks_off_with_key + Off kwargs, CommandContext off assertions, override_flags(agent_decks=*) wrappers, flag monkeypatches, decks_enabled asserts, agent_decks_active kwargs. Migrated tests: artifacts Ctrl+J to next_deck_card (2 tests), clan fold to deck zoom (dropped section-identity assertion), metadata_search 3 to deck overlay (dropped help-during-commit + ctrl+f scroll assertions), tribe to deck Main scroll, workflow to Files-deck-empty, header/jump 4 to Main|Files split, 2 new deck Main pin tests. Epic-symbols: none for 10.1.1; none added for 10.1.2 (symvision reports only pre-existing unrelated private-import errors, zero hits in changed files; ZoomPanelModal still has non-test consumers). Legacy left for legacy-ui-deletion (10.1.2): picker mixin/modal, zoom_panel_* modules, DetailPanelMode/DetailLayoutMode + cycle, section-stop actions, redirect handlers, #agent-deck-source-host + legacy ids, view chip plumbing, view_picker hint mapping. Stale goldens: visual PNGs not regenerated (cutover-goldens phase owns); visual collect passes (990). Pre-existing failures confirmed via git stash: test_parallel_step_does_not_show_agent_prompt. PROPOSED FOLLOW-UP: none. --note

[2026-09-24T15:41:58Z · sase-17d.10.1.1] Closed per plan 202609/deck_flag_removal.md section 6.7: flag + Off branches removed, tests deleted/migrated as noted, epic-symbols clean, legacy left for 10.1.2, goldens stale window recorded. Do not close 17d.10.1/17d.10/17d.

[2026-09-24T16:16:12Z · sase-17d.10.1.1--1] Monitor follow-up (post-close repair): just check failed only at _lint-symvision on the pre-existing private-import backlog (usage/doctor/plugins-browser, zero hits in touched files); verified byte-identical failure on a clean git-stash tree, left untouched per plan 4. That blocker is already tracked by sase-17c.

The phase's test migration missed 16 decks-caused failures (all 3 files pass on the clean tree, so all caused by this change). Repaired: deleted 13 modal-path-only tests in test_agents_zoom_panel_action.py (9x initial-target params, warns-without-agent, provider-resolves, seed-carries) and 2 in test_agents_zoom_panel_tribe.py (tribe-modal routing, agent-mode row selection) since Z no longer opens ZoomPanelModal; migrated test_metadata_sections test to assert next/prev_agent_metadata_section are now unavailable on Agents (renamed ..._unavailable_now_that_decks_are_unconditional); migrated deck-persistence install test off the deleted _decks_persistence_active wrapper to assert the snapshot applies and merged is set (renamed test_install_applies_snapshot_and_marks_merged). 3 test files newly modified (56 paths total).

Verification now: targeted batches green (195 + 290 + 70 + 17 passed; only failure anywhere is pre-existing test_parallel_step_does_not_show_agent_prompt, confirmed failing on clean tree), sync_feature_flags_schema --check and check_feature_flags pass, visual collect 990, epic-symbols none, ruff + format clean on edited files, direct-mypy errors identical on clean tree. Greps from plan 3/6.1 return zero (excl. pycache/config field).

PROPOSED FOLLOW-UP: none beyond sase-17c (the symvision backlog keeps just check red for every agent on this tree).

## Dependencies

- **Blocks:** [sase-17d.10.1.2](sase-17d.10.1.2.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17d.10.1.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17d.10.1.1.md) | [sase-17d.10.1.1](sase-17d.10.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bda8308`](https://github.com/sase-org/sase/commit/bda83083bfec4fa0cc0d8ddbebc7f764f56ac1c8) | test(ace): drop zoom-modal routing tests and migrate persistence/metadata tests after deck flag removal | [sase-17d.10.1.1](sase-17d.10.1.1.md) | 2026-09-24 13:23:32 EDT |
