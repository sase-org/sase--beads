# Bead: sase-j2.1 — Move panel isolation onto a new \`=\` keymap

[Bead Pages](../README.md) / [sase-j2](README.md) / sase-j2.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xh/README.md) · **Assignee:** `sase-j2.1` · **Size:** medium
**Created:** 2026-08-10 14:08:02 EDT · **Closed:** 2026-08-10 14:47:34 EDT
**Plan:** [202608/tribe\_zoom\_and\_panel\_isolation\_keymap.md](https://github.com/sase-org/sase--plans/blob/main/202608/tribe_zoom_and_panel_isolation_keymap.md)

## Description

isolate: add the configurable `isolate_panels` action bound to `=`, stop `action_zoom_panel` from owning whole-panel isolation, broaden isolate and restore so they work from an in-panel row selection, and resync the footer, help modal, command palette, and docs.

## Notes

[2026-08-10T18:47:34Z · sase-j2.1] Implemented the isolate phase: added configurable isolate_panels action bound to =, removed isolation from action_zoom_panel, broadened isolate/restore to work from row/banner selection as well as whole-panel focus, resynced footer/help modal/command palette/docs, and updated/added tests (new tests/ace/tui/test_agent_panel_isolation_row_focus.py plus updates across keymap/command/footer test suites). just install && just check pass clean (28481 passed, 10 skipped; one prior run's 2 failures in test_prompt_bar_xprompt_selector_requests.py were confirmed pre-existing parallel-run flakiness unrelated to this change, not present on rerun).

[2026-08-10T18:48:36Z · sase-j2.1] isolate phase implemented: configurable isolate_panels action bound to =, action_zoom_panel no longer owns whole-panel isolation, isolate/restore broadened to row/banner selection, footer/help modal/command palette/docs resynced, tests updated and added (test_agent_panel_isolation_row_focus.py). just install && just check pass clean.

## Dependencies

- **Blocks:** [sase-j2.2](sase-j2.2.md) ◐ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-j2.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j2.1/README.md) | [sase-j2.1](sase-j2.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5f6d8ea`](https://github.com/sase-org/sase/commit/5f6d8ea64f6e6aaabf562c68af84b5ecdcdae222) | feat(ace): move panel isolation onto a new = keymap | [sase-j2.1](sase-j2.1.md) | 2026-08-10 14:49:38 EDT |
