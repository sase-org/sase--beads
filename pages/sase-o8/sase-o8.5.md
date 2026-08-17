# Bead: sase-o8.5 — Ranking signals in the placeholder panel

[Bead Pages](../README.md) / [sase-o8](README.md) / sase-o8.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04e](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04e.md) · **Assignee:** `sase-o8.5` · **Size:** medium
**Created:** 2026-08-17 06:01:53 EDT · **Closed:** 2026-08-17 09:07:44 EDT
**Plan:** [202608/placeholder\_completion\_ranking.md](https://github.com/sase-org/sase--plans/blob/main/202608/placeholder_completion_ranking.md)

## Description

signals: render the score meter and dominant-reason chip on saved placeholder rows, align both source groups on one label column, add the combined border-subtitle legend with an explicit width ladder, and refresh the docs and PNG goldens.

## Notes

[2026-08-17T13:07:15Z · sase-o8.5] PROPOSED FOLLOW-UP: tests/fakey/test_usage_limit_e2e.py::test_usage_limit_failure_disables_only_fakey_and_preserves_error failed once under the full `just test-scoped` parallel run (483s, 31985 passed/1 failed/11 skipped) but passes cleanly in isolation; the file is unrelated to this phase (fakey/llm-provider usage-limit disabling, not placeholder completion) and untouched by it. Looks like a contention-sensitive flake worth adding to the known-flake tracking mentioned in Justfile test-contention notes.

[2026-08-17T13:07:44Z · sase-o8.5] Implemented: saved placeholder rows render the shared score meter and dominant-reason chip (append_placeholder_completion_row now takes label_width/inner_width/signals_enabled, degrading chip-then-meter); placeholder_label_width() joins _RowLayout, measured across both prompt and saved groups with badge cells included so they share one column; placeholder_completion_subtitle() adds the 4-rung width ladder (source+signal legend -> signal legend -> today's subtitle -> delete alone), wired into show_file_completions via a new placeholder_ranking_signals param threaded from _file_completion_base.py; docs/ace.md Placeholder-completion bullet documents the three signals, meter/chip, legend, and settings; removed the now-consumed sase-o8.4(PlaceholderRankingMetadata) symvision epic-symbol whitelist entry per sase/memory/symvision.md. Added tests/ace/tui/widgets/test_placeholder_rows.py (19 new tests: row rendering/degradation, label-width/cap, all 4 subtitle ladder rungs, cross-group alignment, panel integration) plus extended the PNG snapshot fixtures with ranking metadata and regenerated goldens (placeholder_common_completion_panel_120x40.png changed as expected; placeholder_completion_panel_120x40.png verified byte-identical since it has no saved rows). Verified: just install; full placeholder/history-word/ranking-signal test files green; both PNG snapshot tests green and stable on rerun; just check green (all lint gates incl. mypy and symvision, plus the full test-scoped run: 31985 passed, 11 skipped, 1 unrelated pre-existing flake in tests/fakey/test_usage_limit_e2e.py that passes in isolation, noted as a PROPOSED FOLLOW-UP on this bead).

[2026-08-17T13:08:23Z · sase-o8.5] Implemented placeholder ranking evidence rendering in the completion panel: score meter + reason chip on saved rows via append_placeholder_completion_row(), shared label column width via placeholder_label_width(), 4-rung subtitle legend ladder via placeholder_completion_subtitle() wired through new placeholder_ranking_signals setting, docs/ace.md updated, and removed the satisfied sase-o8.4(PlaceholderRankingMetadata) symvision whitelist entry. Verified with 19 new unit/integration tests (tests/ace/tui/widgets/test_placeholder_rows.py), both PNG snapshot goldens regenerated and confirmed correct, and a full just check run (all lint gates + scoped test suite, 31985 tests passing). One unrelated pre-existing flaky test (tests/fakey/test_usage_limit_e2e.py) noted as proposed follow-up.

## Dependencies

- **Depends on:** [sase-o8.1](sase-o8.1.md) ✓ · ⧖ 2026-08-17
- **Depends on:** [sase-o8.4](sase-o8.4.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-o8.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-o8.5/README.md) | [sase-o8.5](sase-o8.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5abf9eb`](https://github.com/sase-org/sase/commit/5abf9eb64e3cc85b50ccf5d91d77f78c4a83a767) | feat(ace-tui): render ranking evidence on placeholder completion rows | [sase-o8.5](sase-o8.5.md) | 2026-08-17 09:09:12 EDT |
