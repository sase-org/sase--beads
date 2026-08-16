# Bead: sase-na.3 — Warm cache, menu, and settings wiring

[Bead Pages](../README.md) / [sase-na](README.md) / sase-na.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03s.w0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03s.w0.md) · **Assignee:** `sase-na.3` · **Size:** medium
**Created:** 2026-08-16 12:14:58 EDT · **Closed:** 2026-08-16 15:16:54 EDT
**Plan:** [202608/word\_completion\_ranking.md](https://github.com/sase-org/sase--plans/blob/main/202608/word_completion_ranking.md)

## Description

wiring: hold the index in the app-global warm cache, apply deletions at query time, feed ranked candidates into the history-word menu, order prompt-local words nearest-first, and add the two ranking settings.

## Notes

[2026-08-16T19:16:20Z · sase-na.3] PROPOSED FOLLOW-UP: 7 pre-existing test failures unrelated to this phase surfaced during just check: tests/test_file_panel.py::test_render_static_file_result_renders_content, test_display_linked_diff_renders_banner_and_raw_content, test_live_diff_renders_all_lines_and_posts_line_count, test_live_diff_timestamp_refresh_reuses_cached_body, test_file_panel_pathological_cap_posts_explicit_range, test_linked_diff_full_rerender_keeps_banner (all MagicMock/update-call assertion failures) and tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[stats] (golden fixture missing a Flags: line). Reproduced identically on a clean master checkout via git stash, so unrelated to word-ranking wiring work -- file a task to fix.

[2026-08-16T19:16:54Z · sase-na.3] Implemented the wiring phase per plan/202608/word_completion_ranking.md: warm app-global PromptWordIndex + deletion-set cache in _startup_history_words.py (deletions.applied at query time, Ctrl+D no longer rebuilds the index); build_indexed_history_word_completion_result() feeds ranked (smart) or zero-score (recent) candidates from prompt_word_ranking into the history-word menu via HistoryWordCompletionMetadata, wired through _try_history_word_completion_tab/_refresh_history_word_completion/_accept_file_completion/_move_file_completion; prompt-local build_prompt_word_completion_result() now orders nearest-first by latest pre-cursor offset; added word_ranking (smart/recent) and word_ranking_signals settings to PromptCompletionSettings + default_config.yml + sase.schema.json. Deleted src/sase/history/prompt_words.py (fully superseded, zero remaining consumers) and prompt_word_index.clear_prompt_word_index_cache (unused after the query-time-deletions redesign); renamed WordRankingContext to _WordRankingContext and removed the closed sase-na.2 epic-symbol whitelist entries, adding sase-na.4(HistoryWordCompletionMetadata) since the signals phase is its real consumer. Verified: just lint and just check both pass (ruff, mypy, symvision, schema-validity all clean); 94 tests green across the touched history/completion suites plus new smart-ranking, recent-mode-no-metadata, mid-word, and Ctrl+D-no-rebuild tests. just check's scoped suite shows 7 failures (test_file_panel.py x6, test_bead_cli_golden_contract[stats]) that reproduce identically on a clean master checkout (verified via git stash) -- unrelated pre-existing drift, recorded as a PROPOSED FOLLOW-UP note.

[2026-08-16T19:17:53Z · sase-na.3] Re-verifying publication of prior close: warm cache now holds a full PromptWordIndex with deletions applied at query time; history-word menu wired through build_indexed_history_word_completion_result for smart/recent ranking modes; prompt-local words ordered nearest-first; word_ranking and word_ranking_signals settings added to PromptCompletionSettings, default_config.yml, and sase.schema.json; prompt_words.py removed. just lint and just check pass; 94 tests green across touched suites.

## Dependencies

- **Depends on:** [sase-na.2](sase-na.2.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-na.4](sase-na.4.md) ✓ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-na.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-na.3/README.md) | [sase-na.3](sase-na.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`101af72`](https://github.com/sase-org/sase/commit/101af72428a1fc4f3c3c51f8cc25c57900c0adcb) | feat(history): wire ranked word completion into the history-word menu | [sase-na.3](sase-na.3.md) | 2026-08-16 15:20:00 EDT |
