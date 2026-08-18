# Bead: sase-pq.5 — Task bead gates declare their type

[Bead Pages](../README.md) / [sase-pq](README.md) / sase-pq.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.060](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.060.md) · **Assignee:** `sase-pq.5` · **Size:** medium
**Created:** 2026-08-18 09:38:06 EDT · **Closed:** 2026-08-18 11:39:36 EDT
**Plan:** [202608/task\_type\_gate\_presentation.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_type_gate_presentation.md)

## Description

gates: freeze the task-type display block into the TaskTriage and BeadSnooze payloads, declare the chip, the typed note line, and the type tag, add the `**Task type:**` preview fact, and rebuild the whole presentation in kind validation instead of hand-checking its fields.

## Notes

[2026-08-18T15:19:36Z · 06a] COORDINATION (heads-up from a separate, not-yet-approved epic that migrates sase feature-flag beads onto a 'flag' TASK type; full context is on the parent epic bead sase-pq):

When you freeze the task-type display block into gate payloads, please do not enumerate the task-bead gate kinds as exactly {task_triage, bead_snooze}. The FlagTriage gate (src/sase/bead/flag_gate.py, kind 'flag_triage') is about to become a task-bead gate too — its subject bead will be an ordinary task bead whose task_type is 'flag' — and it will need the identical frozen presentation.chip, typed note line, type tag, and '**Task type:**' preview fact.

Keying the freezing path off 'the subject bead is a task bead that has a task_type' rather than off a kind allowlist makes that a no-op for you and for the flag epic. Same request for the rebuild-in-kind-validation half: src/sase/notification_gates/kind_validation/flag_triage.py should be able to adopt the same rebuild-and-compare shape you give task_triage rather than keep hand-checking its fields.

Files this phase and the flag epic both touch: src/sase/scripts/_bead_task_triage_gates.py, src/sase/notification_gates/kind_validation/flag_triage.py. This epic lands first; the flag epic rebases onto whatever you land.

[2026-08-18T15:39:36Z · sase-pq.5] Verified typed TaskTriage and BeadSnooze gates freeze task_type_display and declare chip, notes[1], type tag, and the **Task type:** preview fact from the frozen block; untyped gates stay byte-identical (no chip, no display key, tags=['bead','task']); unresolved slugs degrade to '?' + raw field names; forged chip/tag/second note and mutated or invalid task_type_display fail with the kind-specific presentation or payload code; display without task_type is rejected; preview description/notes recovery still works with the new metadata line and blank notes. just check passed (scoped escalated to the full suite because the Justfile dropped the now-consumed sase-pq.5 epic-symbols).

[2026-08-18T15:40:59Z · sase-pq.5] Verified typed TaskTriage and BeadSnooze gates freeze task_type_display and declare chip, notes[1], type tag, and the **Task type:** preview fact from the frozen block; untyped gates stay byte-identical (no chip, no display key, tags=['bead','task']); unresolved slugs degrade to '?' + raw field names; forged chip/tag/second note and mutated or invalid task_type_display fail with the kind-specific presentation or payload code; display without task_type is rejected; preview description/notes recovery still works with the new metadata line and blank notes. just check passed (scoped escalated to the full suite because the Justfile dropped the now-consumed sase-pq.5 epic-symbols).

## Dependencies

- **Depends on:** [sase-pq.1](sase-pq.1.md) ✓ · ⧖ 2026-08-18
- **Depends on:** [sase-pq.2](sase-pq.2.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pq.6](sase-pq.6.md) ◐ · ⧖ 2026-08-18
- **Blocks:** [sase-pq.7](sase-pq.7.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pq.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pq.5/README.md) | [sase-pq.5](sase-pq.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`832e3b7`](https://github.com/sase-org/sase/commit/832e3b7e8ffaee0df0999f46949ff04846b44117) | feat(bead): freeze task-type display into task and snooze gates | [sase-pq.5](sase-pq.5.md) | 2026-08-18 11:42:07 EDT |
