# Bead: sase-n8.6 — The Launch Control agent-history panel and its \`H\` keymap

[Bead Pages](../README.md) / [sase-n8](README.md) / sase-n8.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03t](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03t.md) · **Assignee:** `sase-n8.6` · **Size:** large
**Created:** 2026-08-16 11:32:41 EDT · **Closed:** 2026-08-16 15:28:03 EDT
**Plan:** [202608/launch\_control\_alias\_history.md](https://github.com/sase-org/sase--plans/blob/main/202608/launch_control_alias_history.md)

## Description

panel: add the `H` binding and its context-aware footer entries to Launch Control, build the pop-up panel (title summary, grouped rows, two-line detail strip, footer) on the panel's existing worker/navigation/jump machinery, add full-prompt view, copy, load-more, refresh, and hidden-toggle actions, style it alongside the other Launch Control panels, and document it in the ACE reference.

## Notes

[2026-08-16T19:28:03Z · sase-n8.6] Implemented models_panel_history.py (H binding + row resolution), alias_history_state.py, alias_history_rendering.py, alias_history_modal.py, styles.tcss + docs/ace.md updates. Verified: 63 focused alias-history tests pass, 336 passed/1 skipped in full models_panel suite (no regressions), ruff check+format clean, mypy clean on all touched/new files, git diff --check clean, no trailing whitespace. just symvision confirmed my sase-n8 epic-symbol entries (AliasHistoryGroup/AliasHistoryRun/AliasHistoryView/load_alias_history) are no longer stale; remaining sase-n9/sase-na.2 symvision failures are pre-existing on HEAD (unmodified by this diff) and unrelated to this work.

## Dependencies

- **Depends on:** [sase-n8.5](sase-n8.5.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-n8.7](sase-n8.7.md) ◐ · ⧖ 2026-08-16
- **Blocks:** [sase-n8.8](sase-n8.8.md) ◐ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n8.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-n8.6.md) | [sase-n8.6](sase-n8.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bc529f1`](https://github.com/sase-org/sase/commit/bc529f11f5f2c8c910f3e2ba08650350b68eb1e9) | feat(ace): add alias agent-history panel to Launch Control | [sase-n8.6](sase-n8.6.md) | 2026-08-16 15:29:09 EDT |
