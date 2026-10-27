# Bead: sase-1om.6 — Feed the TUI from the authoritative report

[Bead Pages](../README.md) / [sase-1om](README.md) / sase-1om.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5e.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5e.linker.w0.md) · **Assignee:** `sase-1om.6` · **Size:** medium
**Created:** 2026-10-26 20:19:45 EDT · **Closed:** 2026-10-27 02:48:32 EDT
**Plan:** [202610/machine\_capacity\_transparency.md](https://github.com/sase-org/sase--plans/blob/main/202610/machine_capacity_transparency.md)

## Description

tui-report-feed: compute the machine report off the event loop on token change plus a 10 s poll, drive the chip values and row queue context from it, keep the roster projection only as a pre-first-report estimate and drift witness, and log capacity_gauge/capacity_drift telemetry.

## Notes

[2026-10-27T06:46:38Z · sase-1om.6--2] PROPOSED FOLLOW-UP: The 17 remaining failures in ToolRun e05787c546f9b1887d31060e2543a361 match the clean-base targeted reproduction on HEAD 260b9caa3f:
- tests/test_final_status_command.py::test_status_pretty_renders_e2e_fixture
- tests/main/test_repo_log.py::test_repo_log_summary_renders_external_kind
- tests/test_bead/test_clan_summary_epic_bead_script.py::test_markdown_helper_renders_semantic_styles_and_safe_markup
- tests/ace/tui/test_plan_decision_ace_render_cards.py::test_decision_cards_never_clip_with_stylesheet
- tests/test_bead/test_cli_show_style_units.py::test_resolve_detail_style_gate_matrix[auto-auto-True-rich]
- tests/test_vcs_log_progress.py::test_interactive_fetch_progress_uses_transient_spinner
- tests/ace/tui/modals/test_preview_search.py::test_wrapped_row_offsets_agree_with_rich_syntax_render[short\naveryveryverylongunbrokentoken\nend-12]
- tests/ace/tui/modals/test_preview_search.py::test_wrapped_row_offsets_agree_with_rich_syntax_render[short\naveryveryverylongunbrokentoken\nend-20]
- tests/ace/tui/modals/test_preview_search.py::test_wrapped_row_offsets_agree_with_rich_syntax_render[wide \u6f22\u5b57\U0001f642\U0001f642\U0001f642 text\nplain\nmore \u6f22\u5b57-12]
- tests/ace/tui/modals/test_preview_search.py::test_wrapped_row_offsets_agree_with_rich_syntax_render[wide \u6f22\u5b57\U0001f642\U0001f642\U0001f642 text\nplain\nmore \u6f22\u5b57-20]
- tests/ace/tui/modals/test_preview_search.py::test_wrapped_row_offsets_agree_with_rich_syntax_render[tabs\talign\there\n\tindented\nlast-12]
- tests/ace/tui/modals/test_preview_search.py::test_wrapped_row_offsets_agree_with_rich_syntax_render[tabs\talign\there\n\tindented\nlast-20]
- tests/test_plan_pending_selector.py::test_color_contract_force_color
- tests/update_progress/test_log_sink_fanout_session.py::test_select_renderer_modes
- tests/update_progress/test_render_live.py::test_narrow_width_ellipsizes
- tests/update_progress/test_timeline_renderer_fixes.py::test_live_print_final_leaves_later_stdout_intact
- tests/stats/test_render_project.py::test_render_context_from_console_is_injectable
The 16 terminal-dependent rendering failures are already tracked by sase-1ll. The stats render-context signature is outside that bead; exact CI-task and all-task searches found no matching bead, and the recent-task sweep found no duplicate. The two additional failures in ToolRun e057 (test_contract_manifest_matches_marker_selection and test_files_ctrl_j_scrolls_page_anchor_to_top) passed together in isolated ToolRun 5fa07354f92cd1a7ca39eddf43095439. The phase feed test import error was fixed; tests/ace/tui/test_machine_capacity_report_feed.py passed in ToolRun ed2ffb69eed4aa8dd8b1f96fd409fc60.

[2026-10-27T06:48:32Z · sase-1om.6--2] Capacity feed unit tests passed in ToolRun ed2ffb69eed4aa8dd8b1f96fd409fc60; the two extra full-suite test failures passed together in isolated ToolRun 5fa07354f92cd1a7ca39eddf43095439. Targeted PNG maintenance passed 18 tests and reported 20 unchanged snapshots with no image diffs. just fix passed, Symvision passed, git diff --check is clean, and epic-symbols reports none. Full check ToolRun e05787c546f9b1887d31060e2543a361 passed lint and validation but reported 19 test failures plus one feed-test import error; that import was corrected and its focused tests pass. The 17 clean-base signatures and task ownership evidence are recorded in note #1.

## Dependencies

- **Depends on:** [sase-1om.1](sase-1om.1.md) ✓ · ⧖ 2026-10-26
- **Depends on:** [sase-1om.3](sase-1om.3.md) ✓ · ⧖ 2026-10-26
- **Blocks:** [sase-1om.7](sase-1om.7.md) ✓ · ⧖ 2026-10-26
- **Blocks:** [sase-1om.8](sase-1om.8.md) ○ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1om.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1om.6.md) | [sase-1om.6](sase-1om.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f843bd8`](https://github.com/sase-org/sase/commit/f843bd810031b35431803b02dc315bdcf345d84f) | feat(ace): feed capacity header from machine report | [sase-1om.6](sase-1om.6.md) | 2026-10-27 02:49:50 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1om.6--2][1] | Need phase scope, design file, decisions, and prior remaining work | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1om.6.md

<!-- sase:referenced-by:end -->
