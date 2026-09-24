# Bead: sase-18f.1 — Restore every lint gate except toobig on master

[Bead Pages](../README.md) / [sase-18f](README.md) / sase-18f.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0rh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0rh.md) · **Assignee:** `sase-18f.1` · **Size:** medium
**Created:** 2026-09-24 17:18:51 EDT · **Closed:** 2026-09-24 18:41:27 EDT
**Plan:** [202609/green\_just\_check.md](https://github.com/sase-org/sase--plans/blob/main/202609/green_just_check.md)

## Description

lint-green: re-derive master's lint failures stage by stage, including symvision's masked categories. Fix the mypy errors in the agent-detail mixins, launch-prompt inputs, and command-line input/screen. Replace the fixed sleep in the command-line completion test. Resolve the ~41 unused public symbols using the symvision decision hierarchy.

## Notes

[2026-09-24T22:40:38Z · sase-18f.1] FIXES FOR OWNING EPICS (lint-green): every lint stage except toobig is green after this phase (mypy, ruff, flags, pyscripts, test waits, symvision incl. probe with no hidden category, fmt, validate). sase-17x DISCOVERED ISSUE notes #2 and #3 are fixed for mypy (input.py TextAreaTheme None; LineContext retyped through screen.py, submit.py, policies.py, signature.py with no casts), test waits (test_completion_popup.py fixed sleep replaced by an injectable ProviderCache clock and a fake clock in the test) and symvision (grammar wire TypedDicts privatized except CommandLineGrammar, which now annotates grammar._load_command_line_grammar_sync; signature/popup/exits/restore/extras/sources/transcript helpers privatized with tests updated; dead role_style, command_line_grammar_error, build_command_line_bindings deleted; test-only set_command_line_history_file removed, tests patch _history_file_override). Still open for 17x: system-clock guard (block_render), config schema, visual fixture host path, screen.py toobig split. sase-17d: agent-detail mixin mypy errors fixed with class-level TYPE_CHECKING host declarations (query_one overloads, _sync_header_visibility, update_display), not by inheriting Static; _FileSourceLabel, _offset_for_row, _invert_search_direction, _wrap_feedback_message and _status_text privatized as deck_cutover_landing_repairs.md describes. sase-185.3: _launch_prompt_inputs mypy item and dead _dispatch_preview_source_summary were already fixed upstream by a21985b88 / 10422bd05.

[2026-09-24T22:40:49Z · sase-18f.1] PROPOSED FOLLOW-UP: ace.keymaps.command_line config is inert — CommandLineScreen.BINDINGS hard-codes its keys and build_command_line_bindings (no caller, no test since db9949344) was deleted for symvision; if the panel keys are meant to be configurable (command_line_panel.md Keys section), wire CommandLineKeymaps into the screen, which also needs action_ methods for hop_to_palette/history_* that today live in input.py on_key.

[2026-09-24T22:41:01Z · sase-18f.1] PROPOSED FOLLOW-UP: environment-dependent test failures seen on a clean rebased tree in a long-tmp-path workspace (not in the sase-18f plan lists) — tests/main/test_snippet_cli_add.py::test_add_rich_format_states_created_action and tests/main/test_snippet_cli_delete.py::test_delete_rich_format_prints_restore_and_removed_path assert the full tmp path appears in Rich output that wraps it at console width, and tests/completion/test_candidates_project_providers.py::test_bead_candidates_without_a_store_returns_empty_list finds the host bead store from tmp_path; verify on another workspace before treating as real master failures.

[2026-09-24T22:41:27Z · sase-18f.1] Verified on a tree rebased onto origin/master fdc3e3caf: sase tool run check passes fmt and every lint stage (ruff, mypy, feature flags, pyscripts, test waits, changelog, patch/stitch terminology, symvision) and fails only lint (toobig) on screen.py and decks/panel.py, which phase sase-18f.2 owns; the symvision probe shows no hidden category. Also green: just validate, validate-committed-plans, keep-sorted. Targeted pytest over tests/ace/tui/command_line, tests/main, history, completion, dispatch, keymaps, ace widgets and modals passed except failures already listed for the tests-core and tests-ace-ui phases plus three environment-dependent ones recorded as a PROPOSED FOLLOW-UP note.

## Dependencies

- **Blocks:** [sase-18f.2](sase-18f.2.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-18f.3](sase-18f.3.md) ◐ · ⧖ 2026-09-24
- **Blocks:** [sase-18f.4](sase-18f.4.md) ◐ · ⧖ 2026-09-24
- **Blocks:** [sase-18f.9](sase-18f.9.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18f.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.1/README.md) | [sase-18f.1](sase-18f.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`114fbca`](https://github.com/sase-org/sase/commit/114fbca89a9430704d877982b4180a0425763e94) | fix(lint): restore every lint gate except toobig (sase-18f.1) | [sase-18f.1](sase-18f.1.md) | 2026-09-24 18:42:42 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-18f.1][1] | Verify notes recorded before closing | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.1/README.md

<!-- sase:referenced-by:end -->
