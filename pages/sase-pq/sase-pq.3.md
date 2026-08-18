# Bead: sase-pq.3 — The toast and the notification row

[Bead Pages](../README.md) / [sase-pq](README.md) / sase-pq.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.060](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.060.md) · **Assignee:** `sase-pq.3` · **Size:** medium
**Created:** 2026-08-18 09:38:05 EDT · **Closed:** 2026-08-18 10:40:41 EDT
**Plan:** [202608/task\_type\_gate\_presentation.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_type_gate_presentation.md)

## Description

dense: give TaskTriage and BeadSnooze their own toast branch with the chip, the typed detail line, and warning severity, and render the chip glyph on notification rows.

## Notes

[2026-08-18T14:40:41Z · sase-pq.3] Verified TaskTriage and BeadSnooze toasts render the action_data chip plus notes[0], dim notes[1] (truncated to _MAX_NOTE_LEN), and use warning severity; untyped/chipless gates keep today's message text; junk chip color and a '[' glyph do not raise; 4+ bead-gate batches land in the warnings bucket. Notification rows append the chip glyph (bold {color}, or bold when color is junk) immediately after the action icon and omit the chip label and facts; chipless rows stay byte-identical. Render paths use only gate_chip_from_action_data. just check passed (scoped escalated to the full suite because the Justfile dropped the sase-pq.3 epic-symbol). sase bead epic-symbols sase-pq.3 reported no leftovers.

[2026-08-18T14:41:56Z · sase-pq.3] Verified TaskTriage and BeadSnooze toasts render the action_data chip plus notes[0], dim notes[1] (truncated to _MAX_NOTE_LEN), and use warning severity; untyped/chipless gates keep today's message text; junk chip color and a '[' glyph do not raise; 4+ bead-gate batches land in the warnings bucket. Notification rows append the chip glyph (bold {color}, or bold when color is junk) immediately after the action icon and omit the chip label and facts; chipless rows stay byte-identical. Render paths use only gate_chip_from_action_data. just check passed (scoped escalated to the full suite because the Justfile dropped the sase-pq.3 epic-symbol). sase bead epic-symbols sase-pq.3 reported no leftovers.

## Dependencies

- **Depends on:** [sase-pq.1](sase-pq.1.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pq.7](sase-pq.7.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pq.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pq.3/README.md) | [sase-pq.3](sase-pq.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5df9ed7`](https://github.com/sase-org/sase/commit/5df9ed7600535b957e4826c1797b5c9d0dc57114) | feat(tui): show task-type chips on bead-gate toasts and rows | [sase-pq.3](sase-pq.3.md) | 2026-08-18 10:42:39 EDT |
