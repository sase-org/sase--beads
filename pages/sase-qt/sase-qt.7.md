# Bead: sase-qt.7 — Prompt gm and Ctrl+G m entry point

[Bead Pages](../README.md) / [sase-qt](README.md) / sase-qt.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07j](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07j.md) · **Assignee:** `sase-qt.7` · **Size:** small
**Created:** 2026-08-19 08:16:39 EDT · **Closed:** 2026-08-19 11:49:57 EDT
**Plan:** [202608/ace\_memory\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_memory_panel.md)

## Description

prompt-entry: claim the prompt g-prefix m continuation, post the request message, open the panel seeded from the memory reference under the cursor, and restore focus.

## Notes

[2026-08-19T15:49:13Z · sase-qt.7] PROPOSED FOLLOW-UP: just check escalated to the full suite after Justfile epic-symbol edits and failed with 819 errors, mostly ProviderDisableStateError unsupported provider-disable snapshot version 2; targeted gm/Ctrl+G m tests passed 47/47 and lint including mypy/ruff/symvision passed.

[2026-08-19T15:49:57Z · sase-qt.7] gm in NORMAL and Ctrl+G m in INSERT/NORMAL post MemoryPanelRequested, seed #memory/<stem> under the cursor to sase/memory/<stem>.md, pass the prompt launch workspace, and restore pane/vim-mode/cursor on Esc. Hint fixtures advertise memory…; help lists gm / Ctrl+G m. Targeted tests 47/47; lint (ruff/mypy/symvision) passed. sase bead epic-symbols sase-qt.7 is empty after consuming MemoryPanel. just check escalated on Justfile epic-symbol re-keys and the full suite failed with pre-existing provider-disable snapshot v2 errors.

[2026-08-19T15:51:37Z · sase-qt.7] gm in NORMAL and Ctrl+G m in INSERT/NORMAL post MemoryPanelRequested, seed #memory/<stem> under the cursor to sase/memory/<stem>.md, pass the prompt launch workspace, and restore pane/vim-mode/cursor on Esc. Hint fixtures advertise memory…; help lists gm / Ctrl+G m. Targeted tests 47/47; lint (ruff/mypy/symvision) passed. sase bead epic-symbols sase-qt.7 is empty after consuming MemoryPanel.

## Dependencies

- **Depends on:** [sase-qt.4](sase-qt.4.md) ✓ · ⧖ 2026-08-19
- **Blocks:** [sase-qt.8](sase-qt.8.md) ◐ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qt.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qt.7/README.md) | [sase-qt.7](sase-qt.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b419802`](https://github.com/sase-org/sase/commit/b419802f30c3c6a42eadc033fa540a80035797e9) | feat(tui): open Memory panel from prompt gm / Ctrl+G m | [sase-qt.7](sase-qt.7.md) | 2026-08-19 12:00:04 EDT |
