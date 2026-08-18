# Bead: sase-pq.7 — Prove it end to end and document it

[Bead Pages](../README.md) / [sase-pq](README.md) / sase-pq.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.060](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.060.md) · **Assignee:** `sase-pq.7` · **Size:** medium
**Created:** 2026-08-18 09:38:06 EDT
**Plan:** [202608/task\_type\_gate\_presentation.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_type_gate_presentation.md)

## Description

prove: add the one end-to-end test that drives a real typed gate through every surface, refresh and extend the PNG snapshots, and document the chip field and the typed gate surfaces.

## Notes

[2026-08-18T15:19:52Z · 06a] COORDINATION (heads-up from a separate, not-yet-approved epic that migrates sase feature-flag beads onto a 'flag' TASK type; full context is on the parent epic bead sase-pq):

When you write the end-to-end test and the documentation for typed gate surfaces, please leave room for a THIRD task-bead gate kind. FlagTriage (kind 'flag_triage') is about to become a task-bead gate: its subject will be an ordinary task bead whose task_type is 'flag', rendered with a '⚑ flag' chip on exactly the surfaces this epic covers.

Concretely: if the end-to-end test or the docs enumerate 'TaskTriage and BeadSnooze' as the complete set of gates that carry a type chip, phrase it as 'every gate whose subject is a typed task bead' instead, so the flag epic adds a case rather than rewriting your assertions and prose.

Docs both epics touch: docs/notifications.md and docs/axe.md. This epic lands first; the flag epic rebases onto whatever you land.

## Dependencies

- **Depends on:** [sase-pq.3](sase-pq.3.md) ✓ · ⧖ 2026-08-18
- **Depends on:** [sase-pq.4](sase-pq.4.md) ✓ · ⧖ 2026-08-18
- **Depends on:** [sase-pq.5](sase-pq.5.md) ✓ · ⧖ 2026-08-18
- **Depends on:** [sase-pq.6](sase-pq.6.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pq.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pq.7/README.md) | [sase-pq.7](sase-pq.7.md) | 0 |
