# Bead: sase-123.7.5 — Complete screenshot guidance and verify the integrated workflow

[Bead Pages](../README.md) / [sase-123.7](sase-123.7.md) / sase-123.7.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-123.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-123.land.md) · **Assignee:** `sase-123.7.5` · **Size:** medium
**Created:** 2026-09-17 21:13:54 EDT · **Closed:** 2026-09-17 23:39:43 EDT
**Plan:** [202609/complete\_tui\_screenshots.md](https://github.com/sase-org/sase--plans/blob/main/202609/complete_tui_screenshots.md)

## Description

workflow-acceptance: complete the originally approved screenshot memory content and verify real local capture, retained-window iteration, remote shell behavior, and memory read integration against the newer TUI changes.

## Notes

[2026-09-18T03:38:58Z · sase-123.7.5] PROPOSED FOLLOW-UP: Visual PNG lane still has broad Agents golden drift - just test-visual failed with 106 mismatches; representative agents_list_120x40 actual adds the newer [view: file (p)] hint versus the committed golden, while the screenshot-export change is off the visual snapshot render path. Triage against existing sase-x5 before regenerating goldens.

[2026-09-18T03:39:43Z · sase-123.7.5] Updated tui_screenshot memory and live screenshot settling; verified uv run pytest tests/ace/tui/test_screenshot_export.py, tests/main/test_screenshot_command.py, sudo/dispatch targets, real local and retained tmux captures, memory init/check/read, and just check. just test-visual was run and failed with 106 broad Agents PNG golden mismatches; recorded PROPOSED FOLLOW-UP for land triage.

## Dependencies

- **Depends on:** [sase-123.7.1](sase-123.7.1.md) ✓ · ⧖ 2026-09-17
- **Depends on:** [sase-123.7.2](sase-123.7.2.md) ✓ · ⧖ 2026-09-17
- **Depends on:** [sase-123.7.3](sase-123.7.3.md) ✓ · ⧖ 2026-09-17
- **Depends on:** [sase-123.7.4](sase-123.7.4.md) ✓ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-123.7.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-123.7.5/README.md) | [sase-123.7.5](sase-123.7.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8033609`](https://github.com/sase-org/sase/commit/80336097ad93770b2f45b37ba69160a9bb805eba) | fix(tui): settle live screenshots with background workers | [sase-123.7.5](sase-123.7.5.md) | 2026-09-17 23:41:39 EDT |
