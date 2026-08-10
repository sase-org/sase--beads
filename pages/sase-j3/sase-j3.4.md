# Bead: sase-j3.4 — The gt keymap, pane lifecycle, and exact cursor restoration

[Bead Pages](../README.md) / [sase-j3](README.md) / sase-j3.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xl](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xl/README.md) · **Assignee:** `sase-j3.4` · **Size:** medium
**Created:** 2026-08-10 14:51:03 EDT · **Closed:** 2026-08-10 16:58:50 EDT
**Plan:** [202608/snippet\_target\_mode.md](https://github.com/sase-org/sase--plans/blob/main/202608/snippet_target_mode.md)

## Description

pane: add the `gt` / `Ctrl+G t` keymap and its hint, open the named snippet pane at the bottom of the stack, keep cursor and vim mode per pane so closing the snippet pane returns to the exact prior position, and enforce the discard-confirmation and last-agent-pane guard rails.

## Notes

[2026-08-10T20:58:50Z · sase-j3.4] Implemented gt/Ctrl+G t snippet pane lifecycle, exact focus restore, retargeting, save handoff, and dirty-discard guards; verified focused widget/model tests and just check, which escalated to the full scoped suite and passed.

[2026-08-10T21:00:31Z · sase-j3.4] Implemented snippet target pane lifecycle; verified focused widget/model suite (114 passed), just _lint-symvision, and just check.

## Dependencies

- **Depends on:** [sase-j3.2](sase-j3.2.md) ✓ · ⧖ 2026-08-10
- **Depends on:** [sase-j3.3](sase-j3.3.md) ✓ · ⧖ 2026-08-10
- **Blocks:** [sase-j3.5](sase-j3.5.md) ✓ · ⧖ 2026-08-10
- **Blocks:** [sase-j3.6](sase-j3.6.md) ◐ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-j3.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j3.4/README.md) | [sase-j3.4](sase-j3.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ba77762`](https://github.com/sase-org/sase/commit/ba77762e68fd045df73b8106dd589d91787e9ca1) | feat(ace): add snippet target pane lifecycle | [sase-j3.4](sase-j3.4.md) | 2026-08-10 17:01:58 EDT |
