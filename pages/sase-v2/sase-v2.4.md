# Bead: sase-v2.4 — Take per-project disk I/O off the prompt completion keystroke path

[Bead Pages](../README.md) / [sase-v2](README.md) / sase-v2.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0fe](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0fe.md) · **Assignee:** `sase-v2.4` · **Size:** medium
**Created:** 2026-08-28 09:01:21 EDT · **Closed:** 2026-08-28 10:02:04 EDT
**Plan:** [202608/tui\_freeze\_regression.md](https://github.com/sase-org/sase--plans/blob/main/202608/tui_freeze_regression.md)

## Description

prompt_completion: cache project workflow-type and changespec-name lookups across calls and keep the debounced soft-completion timer callback free of synchronous per-project file reads.

## Notes

[2026-08-28T14:01:20Z · sase-v2.4] PROPOSED FOLLOW-UP: Investigate intermittent full-suite failure in tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_confirm_executes_and_refreshes — just check full-suite lane failed once, but the exact test passed immediately when rerun in isolation.

[2026-08-28T14:02:04Z · sase-v2.4] Verified prompt-completion project lookup caching and pump-free timer work with focused pytest (90 passed), ruff check/format check, just _lint-symvision, and the required epic-symbol audit. just check ran and reached the governed full-suite lane; it failed once only in unrelated tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_confirm_executes_and_refreshes, which passed immediately when rerun in isolation, and that intermittent failure was recorded as a PROPOSED FOLLOW-UP note.

## Dependencies

- **Blocks:** [sase-v2.6](sase-v2.6.md) ✓ · ⧖ 2026-08-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-v2.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-v2.4/README.md) | [sase-v2.4](sase-v2.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cff6988`](https://github.com/sase-org/sase/commit/cff6988dadfc2a49fc55e34c9a0621afcc7e63f1) | fix(tui): move prompt completion lookups off pump | [sase-v2.4](sase-v2.4.md) | 2026-08-28 10:03:29 EDT |
