# Bead: sase-na.4 — Ranking signals in the completion panel

[Bead Pages](../README.md) / [sase-na](README.md) / sase-na.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03s.w0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03s.w0.md) · **Assignee:** `sase-na.4` · **Size:** medium
**Created:** 2026-08-16 12:15:47 EDT · **Closed:** 2026-08-16 16:10:55 EDT
**Plan:** [202608/word\_completion\_ranking.md](https://github.com/sase-org/sase--plans/blob/main/202608/word_completion_ranking.md)

## Description

signals: render the stacked score meter, dominant-reason chip, and colored panel legend for history-word rows, degrade cleanly on narrow panels, and refresh the docs and PNG goldens.

## Notes

[2026-08-16T20:03:19Z · sase-na.4] PROPOSED FOLLOW-UP: `just _lint-symvision` fails on unmodified master with three stale --epic-symbol entries for closed bead sase-n9 (agent_family_plan_preview_detail, agent_family_plan_preview_documentation, family_plan_preview_cache_key) in the Justfile, blocking the mandatory `just check` gate for every agent in every workspace regardless of diff. All three symbols already have real non-test consumers in their own files (src/sase/agent_family_plan_preview.py, src/sase/integrations/_editor_helper_agents.py, src/sase/ace/tui/models/agent_family_preview_cache.py), so the fix is a mechanical removal of the three stale Justfile lines per sase/memory/symvision.md. Unrelated to sase-na; verified via git stash against 101af7242.

[2026-08-16T20:04:55Z · sase-na.4] PROPOSED FOLLOW-UP: `just test-scoped` fails 10 pre-existing, unrelated tests on unmodified master (101af7242), verified via git stash: tests/test_file_panel.py (6 nodes, e.g. test_render_static_file_result_renders_content asserting `panel.update.called` is False, and test_display_linked_diff_renders_banner_and_raw_content raising TypeError on `panel.update.call_args[0][0]` being None) fail deterministically in isolation too; tests/ace/tui/test_logs_pane.py::test_logs_tab_g_and_shift_g_scroll_detail_extremes and tests/main/test_config_init_handler.py (3 nodes) only fail inside the full scoped run, passing in isolation, indicating cross-test state leakage/order-dependent flakiness. None touch prompt completion or history-word code. Not caused by sase-na.

[2026-08-16T20:06:53Z · sase-na.4] PROPOSED FOLLOW-UP: `tests/ace/tui/visual/test_ace_png_snapshots_prompt_word_completion.py::test_prompt_word_completion_panel_png_snapshot` PNG golden is stale on unmodified master (101af7242), verified via git stash. The diff is entirely in the search bar ("/SearchQuery » ...") and a top-right badge, not the prompt-word completion panel itself, so it is unrelated to any word-ranking work; some other recent unrelated change to the shared visual-suite app scaffold drifted without regenerating this golden. Left untouched since sase-na.4 has no legitimate reason to regenerate it (the plan only calls for refreshing it "if local reordering changes its rows", and this test hardcodes its candidate list rather than exercising the sort).

[2026-08-16T20:09:12Z · sase-na.4] PROPOSED FOLLOW-UP: `just test-visual` fails far more broadly than initially scoped: the full suite shows 278/692 failing on unmodified master (101af7242, verified via git stash before this note plus a from-scratch `just install` in this workspace), not just the one prompt_word_completion golden noted above. Every failure diffs only a small top-right badge/counter region of the shared AcePage top bar (identical pixel-diff shape confirmed across test_ace_png_snapshots_prompt_word_completion.py and test_ace_png_snapshots_config_center_home.py) -- one shared rendering regression, not 278 independent ones. This workspaces `just install` fast-forwarded the linked sase-core checkout 0.27.14 -> 0.27.15, and a recent commit (e38d7b80f, "feat(bead): add flag issue type to the Python bead layer") plausibly touches the flag-count badge in that same region, but the root cause is unconfirmed. This blocks `just check-full` (via `test-cost`, which depends on `_setup-visual`) for every agent, independent of diff. Unrelated to sase-na; my own regenerated `history_word_completion_panel_120x40` golden passed cleanly in the full run. Recommend a dedicated investigation task, since 278 goldens likely need a single coordinated regeneration once the badge regression (or intentional change) is identified, not a per-test fix.

[2026-08-16T20:10:55Z · sase-na.4] Implemented the ranking-signals UI for smart-ranked history-word rows: new src/sase/ace/tui/widgets/_history_word_rows.py renders the 5-cell stacked score meter (largest-remainder color distribution, fixed relation->recency->frequency order), the dominant-reason chip (⇄/◷/✦), and wires both into the completion panel via _prompt_input_bar_completion_panel_content.py/_panel.py/_panel_labels.py, threaded through a new word_ranking_signals param on show_file_completions() sourced from PromptCompletionSettings in _file_completion_base.py. Rows/legend degrade cleanly on narrow panels (chip dropped first, then meter, verified with direct width-boundary unit tests and mounted-widget wide/narrow tests) and fall back to plain rows/hint when word_ranking_signals is off or a row carries no metadata (recent mode, loading placeholder). Removed the now-stale --epic-symbol "sase-na.4(HistoryWordCompletionMetadata)" Justfile exemption since the type now has real consumers. Updated docs/ace.md's History-word and Prompt-local completion bullets for the ranking model, settings, and instant Ctrl+D. Regenerated tests/ace/tui/visual/snapshots/png/history_word_completion_panel_120x40.png against a fixture extended with real ranking metadata (three rows, one per dominant reason) and visually confirmed it matches the plan's mockup. Verified: 21 new unit/widget tests in tests/ace/tui/widgets/test_history_word_rows.py plus all 442 existing tests across history/prompt-word/history-word/model-completion-row suites pass; ruff, mypy, and the targeted PNG snapshot all green. just check is blocked only by pre-existing, unrelated issues confirmed via git stash against unmodified master and recorded as PROPOSED FOLLOW-UP notes: (1) three stale sase-n9 symvision --epic-symbol entries, (2) 10 pre-existing/order-dependent test-scoped failures in file_panel/logs_pane/config_init_handler, (3) a systemic top-bar-badge PNG drift affecting 278/692 just test-visual nodes repo-wide (my own regenerated golden passed cleanly in that same full run).

[2026-08-16T20:11:48Z · sase-na.4] Implemented ranking-signals UI for smart-ranked history-word completion rows: 5-cell stacked score meter, dominant-reason chip, and border-subtitle legend, with graceful degradation on narrow panels and when word_ranking_signals is off. Updated docs/ace.md and regenerated PNG golden. Verified: 21 new tests + 442 existing related tests pass; ruff/mypy clean on changed files.

## Dependencies

- **Depends on:** [sase-na.3](sase-na.3.md) ✓ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-na.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-na.4/README.md) | [sase-na.4](sase-na.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e7b2a30`](https://github.com/sase-org/sase/commit/e7b2a30fb39858cd00cd1fb3d26e6791a7587ba3) | feat(history): render ranking signals in history-word completion rows | [sase-na.4](sase-na.4.md) | 2026-08-16 16:12:44 EDT |
