# Bead: sase-1eq.5.1.1 — Keymap, resume ids, and stats request contracts

[Bead Pages](../README.md) / [sase-1eq.5.1](sase-1eq.5.1.md) / sase-1eq.5.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.5.md) · **Assignee:** `sase-1eq.5.1.1` · **Size:** medium
**Created:** 2026-10-03 13:29:43 EDT · **Closed:** 2026-10-03 14:57:15 EDT
**Plan:** [202610/tui\_macro\_surfaces.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_macro_surfaces.md)

## Description

tui-contracts: make focus_macro, clear_macro_focus, and start_last_vcs_macro_in_editor the keymap actions, with flag-gated aliases in legacy_xprompt_syntax.py. Resume Admin Center sub-tab and Statistics view id xprompts as macros, and send macro stats request keys.

## Notes

[2026-10-03T18:28:49Z · sase-1eq.5.1.1] PROPOSED FOLLOW-UP: tests/ace/tui/test_xprompt_browser_load_keymap.py::test_enter_loads_raw_definition_and_binds_source and ::test_enter_returns_while_xprompt_file_read_is_blocked fail identically on the clean base tree (verified via stash); triage into a task bead, likely owned by tui-browser

[2026-10-03T18:56:49Z · sase-1eq.5.1.1--1] PROPOSED FOLLOW-UP: 5 more just-check NEW failures reproduce identically on clean base tree (verified via stash): test_parser_root_help compact help, prompt_tab_focus_steal background-refresh suite, export_save home-macros/project-writes, gate_turn followup disabled-region; triage into task beads, likely owned outside tui-contracts

[2026-10-03T18:57:00Z · sase-1eq.5.1.1--1] PROPOSED FOLLOW-UP: 2 just-check lint errors pre-existing on clean base in files tui-contracts did not touch: mypy EntryPoints.get in doctor/checks_config_retired.py:322 and symvision unused discover_macro_plugin_entry_points in main/plugin_discovery.py; triage into task beads

[2026-10-03T18:57:15Z · sase-1eq.5.1.1--1] tui-contracts done: focus_macro/clear_macro_focus/start_last_vcs_macro_in_editor canonical with flag-gated legacy aliases (both-spellings error), config sub-tab and statistics view ids macros with unconditional xprompts readers, macro stats request keys sent. Verified: 153 phase-owned tests pass (legacy syntax both flag states, stats query, keymap defaults/registry/validation, admin-center resume, config hub catalog, terminology, schema); epic-symbols clean; just-check NEW failures (6 tests) and 2 lint errors all reproduce identically on clean base via stash, recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-1eq.5.1.2](sase-1eq.5.1.2.md) ✓ · ⧖ 2026-10-03
