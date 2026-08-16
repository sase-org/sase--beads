# Bead: sase-ns.4 — File-panel assertions against the scroll-anchor seam

[Bead Pages](../README.md) / [sase-ns](README.md) / sase-ns.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04c.md) · **Assignee:** `sase-ns.4` · **Size:** small
**Created:** 2026-08-16 17:13:05 EDT · **Closed:** 2026-08-16 17:42:37 EDT
**Plan:** [202608/top\_task\_bead\_sweep.md](https://github.com/sase-org/sase--plans/blob/main/202608/top_task_bead_sweep.md)

## Description

'File-panel assertions against the scroll-anchor seam' section: repoint six deterministically failing tests/test_file_panel.py assertions at the _update_body seam without weakening what they guard, closing task bead sase-nk.

## Notes

[2026-08-16T21:41:52Z · sase-ns.4] PROPOSED FOLLOW-UP: just _lint-mypy fails on clean master — HistoryWordCompletionMetadata was renamed to _HistoryWordCompletionMetadata but src/sase/ace/tui/widgets/_history_word_rows.py and _prompt_input_bar_completion_panel_labels.py still import the public name. Unrelated to this phase; blocks just check after ruff.

[2026-08-16T21:42:37Z · sase-ns.4] Repointed the six sase-nk assertions at _update_body without weakening content checks. tests/test_file_panel.py 17 passed; just test-scoped 468 passed. Closed sase-nk. just check otherwise green; mypy is a pre-existing HistoryWordCompletionMetadata rename drift noted as PROPOSED FOLLOW-UP.

[2026-08-16T21:46:13Z · sase-ns.4] Repointed six file-panel assertions at _update_body; tests/test_file_panel.py 17 passed. Content checks unchanged (static-file header/syntax, linked-diff banner, live-diff line-count, cached-body identity, pathological-cap editor hint).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ns.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ns.4/README.md) | [sase-ns.4](sase-ns.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c8b5e96`](https://github.com/sase-org/sase/commit/c8b5e962e4962f0819008136168d5532cbee9094) | test(file-panel): assert body renders at the \_update\_body seam | [sase-ns.4](sase-ns.4.md) | 2026-08-16 17:48:31 EDT |
