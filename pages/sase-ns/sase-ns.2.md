# Bead: sase-ns.2 — The config-cache full-parallel-lane flake

[Bead Pages](../README.md) / [sase-ns](README.md) / sase-ns.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04c.md) · **Assignee:** `sase-ns.2` · **Size:** large
**Created:** 2026-08-16 17:12:14 EDT
**Plan:** [202608/top\_task\_bead\_sweep.md](https://github.com/sase-org/sase--plans/blob/main/202608/top_task_bead_sweep.md)

## Description

'The config-cache full-parallel-lane flake' section: find the process-global config-state leak that reds test_owner_snapshot_reuses_parsed_overlay_until_token_changes only under the whole-suite parallel lane, closing task bead sase-mv.

## Notes

[2026-08-16T21:52:59Z · sase-ns.2] Implemented the config-cache isolation fix: bind current_config_token() to the CONFIG_DIR object it was computed against (so a successor patch cold-reads), make _clear_config_caches a yield fixture that depends on _isolate_sase_home and drains sase-config-token-refresh before monkeypatch restore, and extend the leak detector to treat leftover refresh workers as poisoning. Minimized reproduction: leftover host-root populate then successor CONFIG_DIR patch (test_rebound_config_dir_cold_reads_successor_paths) plus poisoner-then-victim pytester order (test_blocked_refresh_worker_does_not_poison_a_later_config_read). Focused evidence so far: 77 serial (config + cache + isolation + leak detector), reverse-order 58 passed, SASE_CONTENTION_REPEAT=3 contention 58 passed x3 / 0 failures, ruff+symvision green. just check stopped on pre-existing mypy (HistoryWordCompletionMetadata), not this change.

[2026-08-16T21:54:25Z · sase-ns.2] PROPOSED FOLLOW-UP: mypy HistoryWordCompletionMetadata — just check/_lint-mypy fails on this tree (HEAD 83e2ceea6) because src/sase/ace/tui/widgets/history_word_completion.py defines _HistoryWordCompletionMetadata while _history_word_rows.py and _prompt_input_bar_completion_panel_labels.py still import HistoryWordCompletionMetadata. Introduced when fc1ad39e7 made the class private without updating importers. Unrelated to config-cache isolation; blocks just check-full before the suite runs.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ns.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.2.md) | [sase-ns.2](sase-ns.2.md) | 0 |
