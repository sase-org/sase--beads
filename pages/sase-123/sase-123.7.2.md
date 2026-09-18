# Bead: sase-123.7.2 — Make local capture ownership, deadlines, and settling reliable

[Bead Pages](../README.md) / [sase-123.7](sase-123.7.md) / sase-123.7.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-123.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-123.land.md) · **Assignee:** `sase-123.7.2` · **Size:** medium
**Created:** 2026-09-17 21:13:51 EDT · **Closed:** 2026-09-17 22:12:54 EDT
**Plan:** [202609/complete\_tui\_screenshots.md](https://github.com/sase-org/sase--plans/blob/main/202609/complete_tui_screenshots.md)

## Description

capture-lifecycle: correct tmux window ownership and failure cleanup, propagate the capture deadline through launch, and wait for a settled live frame without blocking Textual.

## Notes

[2026-09-18T02:12:54Z · sase-123.7.2] Implemented local screenshot capture lifecycle fixes: tmux windows are claimed with local reservations, created under unique temporary names, driven/cleaned by tmux window id, request dirs are recoverable from tmux metadata, launch subprocesses share the capture deadline, failure cleanup covers metadata/resize paths, startup/export preserve last pane text, and live SVG export waits for finite settled visual frames. Verified no phase epic-symbol leftovers with 'sase bead epic-symbols sase-123.7.2'; 'uv run pytest -q tests/main/test_ace_tmux.py tests/main/test_screenshot_command.py tests/ace/tui/test_screenshot_export.py' passed; 'just fix' passed; 'just _lint-symvision' passed; 'just check' passed after rerunning transient full-suite failures that passed directly.

## Dependencies

- **Blocks:** [sase-123.7.3](sase-123.7.3.md) ◐ · ⧖ 2026-09-17
- **Blocks:** [sase-123.7.5](sase-123.7.5.md) ◐ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-123.7.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-123.7.2/README.md) | [sase-123.7.2](sase-123.7.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c320b2b`](https://github.com/sase-org/sase/commit/c320b2b6caadd74222fc5327f65bcd4272817f40) | fix(screenshot): harden local tmux capture lifecycle | [sase-123.7.2](sase-123.7.2.md) | 2026-09-17 22:14:38 EDT |
