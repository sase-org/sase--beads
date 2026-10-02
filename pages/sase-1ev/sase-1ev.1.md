# Bead: sase-1ev.1 — Repair the H and C front door

[Bead Pages](../README.md) / [sase-1ev](README.md) / sase-1ev.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vj.md) · **Assignee:** `sase-1ev.1` · **Size:** small
**Created:** 2026-10-02 14:43:03 EDT · **Closed:** 2026-10-02 15:10:13 EDT
**Plan:** [202610/memory\_history\_tui.md](https://github.com/sase-org/sase--plans/blob/main/202610/memory_history_tui.md)

## Description

front-door: make H and C actually open the pager from the Admin Center-hosted Memory pane by removing the call_from_thread misuse inside their async workers. Add failure toasts and stale-open guards, an AST guard test against call_from_thread inside async def under src/sase/ace/tui, and headless key-press tests that fail on the old code.

## Notes

[2026-10-02T19:10:13Z · sase-1ev.1] Removed call_from_thread misuse in action_open_history/action_open_changes async workers (src/sase/ace/tui/modals/memory_pane_history.py): H/C now push PagerScreen directly on the app thread, build misses toast severity=error, stale-selection and closed/unmounted guards drop late opens. Added AST guard test (direct call_from_thread in async def under ace/tui, exempting nested closures) plus headless H/C key-press tests (open, failure toast, stale drop); all 4 fail on pre-fix code. Verified: 19/19 in test_memory_panel_history.py, 30/30 in test_memory_panel.py+test_memory_panel_actions.py, ruff check+format clean, mypy clean. No epic-symbol entries.

## Dependencies

- **Blocks:** [sase-1ev.2](sase-1ev.2.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ev.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ev.1/README.md) | [sase-1ev.1](sase-1ev.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3691b88`](https://github.com/sase-org/sase/commit/3691b88ae7fe33bdae10dc5c6aeb5bba4217a759) | fix(ace-tui): open memory history pagers directly from app thread | [sase-1ev.1](sase-1ev.1.md) | 2026-10-02 15:12:30 EDT |
