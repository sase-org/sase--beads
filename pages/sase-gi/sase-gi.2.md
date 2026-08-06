# Bead: sase-gi.2 — INSERT-mode Ctrl+J for ordered items

[Bead Pages](../README.md) / [sase-gi](README.md) / sase-gi.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ub](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ub/README.md) · **Assignee:** `sase-gi.2` · **Size:** medium
**Created:** 2026-08-06 15:22:49 EDT · **Closed:** 2026-08-06 16:41:47 EDT
**Plan:** [202608/prompt\_ordered\_lists.md](https://github.com/sase-org/sase--plans/blob/main/202608/prompt_ordered_lists.md)

## Description

newline: route Ctrl+J through the list-edit planner so ordered items continue, split, grow a first sibling, exit from an empty marker, and de-list at the content column, each as one undo checkpoint with the run renumbered.

## Notes

[2026-08-06T20:40:38Z · sase-gi.2] PROPOSED FOLLOW-UP: tests/ace/tui/util/test_stall_watchdog.py::test_watchdog_keeps_hitch_and_stall_state_machines_independent and tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_commit_repeat_q_and_passthrough failed under a concurrent multi-workspace test load during sase-gi.2 verification and both pass in isolation — investigate and harden these two timing-sensitive tests.

## Dependencies

- **Depends on:** [sase-gi.1](sase-gi.1.md) ✓ · ⧖ 2026-08-06
- **Blocks:** [sase-gi.3](sase-gi.3.md) ◐ · ⧖ 2026-08-06
- **Blocks:** [sase-gi.7](sase-gi.7.md) ◐ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gi.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gi.2/README.md) | [sase-gi.2](sase-gi.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`af0555b`](https://github.com/sase-org/sase/commit/af0555bd60926526bc9087458647f9a935e30a5f) | feat(ace-tui): grow and renumber ordered lists on INSERT-mode Ctrl+J | [sase-gi.2](sase-gi.2.md) | 2026-08-06 16:45:58 EDT |
