# Bead: sase-gn.7 — One pending gate per task bead

[Bead Pages](../README.md) / [sase-gn](README.md) / sase-gn.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.uh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.uh/README.md) · **Assignee:** `sase-gn.7` · **Size:** medium
**Created:** 2026-08-06 19:28:04 EDT · **Closed:** 2026-08-06 21:41:27 EDT
**Plan:** [202608/bead\_snooze\_and\_notification\_indicator.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_snooze_and_notification_indicator.md)

## Description

snooze-gate-reconciler: extend the bead task-gate chop to own triage and wake gates together, keep each snoozed bead's notification snoozed to its wake time, and add triage-time snoozing to the TaskTriage gate.

## Notes

[2026-08-07T01:41:08Z · sase-gn.7] PROPOSED FOLLOW-UP: bead_mutation_facade.wake_due_snoozes and its Rust wake_due_task_snoozes are dead — D2 (a snoozed bead gate is born snoozed, resurfaced by the notification snooze expiry) means the reconciler never needs a due-wake selector; delete both or justify keeping them.

[2026-08-07T01:41:27Z · sase-gn.7] Extended the bead task-gate chop to own TaskTriage and BeadSnooze together (state schema v3 with a per-bead kinds map, version-2 tolerance, one READY+SNOOZED store pass, wrong-kind cancel as bead_status_changed, snooze-aware presentation fingerprint, and mark_snoozed self-healing of a drifted wake notification), added the triage-time snooze option to the TaskTriage gate with shared '<duration> [+<N>]' parsing that leaves the gate pending on a typo, and updated the chop's default_config.yml description. Verified: just check green (fmt, ruff, mypy, symvision, toobig, full 26.7k-test suite after scoped escalation); 28 chop tests and 31 task-gate tests including kind swap both ways, the no-double-gate invariant, v2 state migration, re-snooze notification healing, and past-wake no-op; plus a real no-mock end-to-end run confirming a snoozed bead gets one BeadSnooze notification born muted at its wake time and, on going ready, exactly one TaskTriage gate replaces it.

[2026-08-07T01:42:05Z · sase-gn.7] Reconciler owns both task-bead gate kinds (v3 state with per-bead kinds map, wrong-kind cancel+replace, snooze-aware fingerprint, notification re-snooze self-heal); TaskTriage gained a validated snooze option; just check green (all lint gates + full suite) plus a no-mock end-to-end chop run for both kinds.

## Dependencies

- **Depends on:** [sase-gn.6](sase-gn.6.md) ✓ · ⧖ 2026-08-06
- **Blocks:** [sase-gn.8](sase-gn.8.md) ✓ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gn.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gn.7/README.md) | [sase-gn.7](sase-gn.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b0e10d1`](https://github.com/sase-org/sase/commit/b0e10d1284e0a364db8ccfae462ab3ab1e2d4a08) | feat(bead): keep exactly one pending gate per task bead | [sase-gn.7](sase-gn.7.md) | 2026-08-06 21:42:58 EDT |
