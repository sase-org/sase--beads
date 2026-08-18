# Bead: sase-pq.7 — Prove it end to end and document it

[Bead Pages](../README.md) / [sase-pq](README.md) / sase-pq.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.060](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.060.md) · **Assignee:** `sase-pq.7` · **Size:** medium
**Created:** 2026-08-18 09:38:06 EDT · **Closed:** 2026-08-18 12:44:33 EDT
**Plan:** [202608/task\_type\_gate\_presentation.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_type_gate_presentation.md)

## Description

prove: add the one end-to-end test that drives a real typed gate through every surface, refresh and extend the PNG snapshots, and document the chip field and the typed gate surfaces.

## Notes

[2026-08-18T15:19:52Z · 06a] COORDINATION (heads-up from a separate, not-yet-approved epic that migrates sase feature-flag beads onto a 'flag' TASK type; full context is on the parent epic bead sase-pq):

When you write the end-to-end test and the documentation for typed gate surfaces, please leave room for a THIRD task-bead gate kind. FlagTriage (kind 'flag_triage') is about to become a task-bead gate: its subject will be an ordinary task bead whose task_type is 'flag', rendered with a '⚑ flag' chip on exactly the surfaces this epic covers.

Concretely: if the end-to-end test or the docs enumerate 'TaskTriage and BeadSnooze' as the complete set of gates that carry a type chip, phrase it as 'every gate whose subject is a typed task bead' instead, so the flag epic adds a case rather than rewriting your assertions and prose.

Docs both epics touch: docs/notifications.md and docs/axe.md. This epic lands first; the flag epic rebases onto whatever you land.

[2026-08-18T16:40:15Z · sase-pq.7] PROPOSED FOLLOW-UP: just check mypy is red on src/sase/glossary/render.py:74 (Console.color_system typed str | None vs Literal) from 88fa6e949 — this prove phase did not touch that file

[2026-08-18T16:40:27Z · sase-pq.7] PROPOSED FOLLOW-UP: just check symvision reports unused public symbols monitor_row_is_settled (agent_family_members.py), project_accent and project_accent_map (project_styles.py) — not introduced by sase-pq.7

[2026-08-18T16:44:33Z · sase-pq.7--1] Prove work is in the tree and verified: tests/test_task_type_gate_surfaces.py (2 passed) drives one real typed flake TaskTriage through create_gate onto toast, notification row, gate pane, review-modal loader, mobile bridge, and the on-disk **Task type:** preview fact; render surfaces must not import the task-type registry. PNG goldens refreshed/added in tests/ace/tui/visual/ (custom_gate_task_triage, notification_beads_tab, notification_filed_by, new notification_beads_typed_gates). Chip/typed-surface docs in docs/notifications.md, docs/beads.md, and src/sase/xprompts/skills/sase_gate.md (phrased as every gate whose subject is a typed task bead). sase bead epic-symbols sase-pq.7 reported no leftovers. just check-full failed only on the pre-existing mypy color_system error in src/sase/glossary/render.py:74 (already proposed as follow-up; this phase did not touch that file). Did not close parent epic sase-pq.

[2026-08-18T16:46:00Z · sase-pq.7--1] just check-full died in 16s on the pre-existing mypy color_system error in src/sase/glossary/render.py:74 (outside this phase). tests/test_task_type_gate_surfaces.py: 2 passed (one typed flake TaskTriage through create_gate onto toast, row, pane, modal loader, mobile bridge, and on-disk **Task type:** preview; render surfaces must not import the task-type registry). PNG goldens refreshed/added under tests/ace/tui/visual/. Chip/typed-surface docs in docs/notifications.md, docs/beads.md, and src/sase/xprompts/skills/sase_gate.md. sase bead epic-symbols sase-pq.7: no leftovers.

## Dependencies

- **Depends on:** [sase-pq.3](sase-pq.3.md) ✓ · ⧖ 2026-08-18
- **Depends on:** [sase-pq.4](sase-pq.4.md) ✓ · ⧖ 2026-08-18
- **Depends on:** [sase-pq.5](sase-pq.5.md) ✓ · ⧖ 2026-08-18
- **Depends on:** [sase-pq.6](sase-pq.6.md) ✓ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pq.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-pq.7.md) | [sase-pq.7](sase-pq.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`50d837a`](https://github.com/sase-org/sase/commit/50d837afa887139b745b9758d8ebe66e5f311111) | test: prove typed task-bead gate chips on every surface | [sase-pq.7](sase-pq.7.md) | 2026-08-18 12:46:45 EDT |
