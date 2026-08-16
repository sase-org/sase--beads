# Bead: sase-ns.5 — Models-panel jump PNG snapshot seam

[Bead Pages](../README.md) / [sase-ns](README.md) / sase-ns.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04c.md) · **Assignee:** `sase-ns.5` · **Size:** small
**Created:** 2026-08-16 17:13:27 EDT · **Closed:** 2026-08-16 17:55:53 EDT
**Plan:** [202608/top\_task\_bead\_sweep.md](https://github.com/sase-org/sase--plans/blob/main/202608/top_task_bead_sweep.md)

## Description

'Models-panel jump PNG snapshot seam' section: repoint the stale build_alias_views monkeypatch at its owning module so the three Models-panel jump PNG snapshots render again, closing task bead sase-mw.

## Notes

[2026-08-16T21:54:05Z · sase-ns.5] PROPOSED FOLLOW-UP: pre-existing repo-wide test/lint breakage unrelated to this phase — src/sase/ace/tui/widgets/history_word_completion.py is missing HistoryWordCompletionMetadata (referenced by _history_word_rows.py and _prompt_input_bar_completion_panel_labels.py), which mypy flags directly and which cascades into ImportError collection failures across ~60+ prompt/completion/xprompt test files under tests/ace/tui/widgets/ and 14 PNG-snapshot visual test modules. Confirmed via git stash comparison that this predates my change and is unrelated to the models_panel/alias-view seam. just check and just check-full will both fail on this until it's fixed.

[2026-08-16T21:54:34Z · sase-ns.5] PROPOSED FOLLOW-UP: tests/ace/tui/visual/test_ace_png_snapshots_models_panel.py, test_ace_png_snapshots_models_panel_alias_history.py, test_ace_png_snapshots_models_panel_edit.py, test_ace_png_snapshots_models_panel_modals.py, and test_ace_png_snapshots_models_panel_navigation.py have 41 failing PNG snapshot assertions (small pixel-count mismatches) on clean master, same root cause pattern as the jump-snapshot goldens I just fixed: commit 981106799 renamed the deterministic AliasView fixture names (large_worker/medium_worker -> xsmall/small/etc.) without regenerating these goldens. Confirmed pre-existing via git stash; out of scope for sase-mw, which only covered the three jump snapshots.

[2026-08-16T21:55:17Z · sase-ns.5] Checked the adjacent bead sase-mw's 'in scope if trivial' note about sase-mw (Artifacts Files PNG detail seam, currently failing on files_options.local_now). Repointing is NOT mechanical: local_now/date-based Today/Yesterday grouping was fully removed from the Files pane by commit f5dda81f3 (shared fold-registry grouping now buckets by source/kind/project only), so the fix requires deciding what the test should assert instead of a date-grouping feature that no longer exists in the panel, not just retargeting a monkeypatch. Left sase-my untouched per the epic plan's instruction to not expand phase scope on non-mechanical fixes.

[2026-08-16T21:55:53Z · sase-ns.5] Task bead sase-mw closed: repointed the stale _patch_alias_views monkeypatch in tests/ace/tui/visual/test_ace_png_snapshots_models_panel_jump.py from models_panel_providers.build_alias_views to models_panel_provider_state.build_alias_views (the module de83c802d actually moved provider-routing state into), and regenerated the three stale PNG goldens that predated a later fixture-name migration (981106799). Verified: .venv/bin/python -m pytest tests/ace/tui/visual/test_ace_png_snapshots_models_panel_jump.py -q -p no:randomly -m visual -> 3 passed, stable on repeat runs. Checked the adjacent sase-my bead per the epic plan's 'in scope if trivial' note and found it is NOT a mechanical repeat (the Files pane's date-based Today/Yesterday grouping was removed entirely by f5dda81f3, so the test needs a real content decision, not just a monkeypatch retarget); left it untouched as instructed. just check's mypy gate and the full test-scoped lane both still fail, but only due to a pre-existing, unrelated HistoryWordCompletionMetadata breakage confirmed via git-stash comparison against clean master (see PROPOSED FOLLOW-UP notes on this bead); recorded two follow-ups (the HistoryWordCompletionMetadata cascade, and 41 other stale Models-panel PNG goldens from the same fixture-rename commit) for the land agent to triage.

[2026-08-16T21:56:25Z · sase-ns.5] Repointed stale _patch_alias_views monkeypatch from models_panel_providers.build_alias_views to models_panel_provider_state.build_alias_views; regenerated 3 stale PNG goldens (models_panel_jump_mixed_bucket_120x40, models_panel_jump_top_level_120x40, models_panel_jump_top_level_70x32). All 3 snapshot tests pass and stable on repeat runs. Pre-existing HistoryWordCompletionMetadata breakage and 41 other stale PNG goldens outside scope recorded as follow-ups.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ns.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ns.5/README.md) | [sase-ns.5](sase-ns.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8a76901`](https://github.com/sase-org/sase/commit/8a769012fde7d70ccfcfdc19dbda53e98fb05292) | fix(tui): repoint stale alias-views monkeypatch in models panel jump tests | [sase-ns.5](sase-ns.5.md) | 2026-08-16 17:57:12 EDT |
