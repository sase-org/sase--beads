# Bead: sase-gn.4 — Snoozed task bead status in the Rust core

[Bead Pages](../README.md) / [sase-gn](README.md) / sase-gn.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.uh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.uh/README.md) · **Assignee:** `sase-gn.4` · **Size:** medium
**Created:** 2026-08-06 19:27:42 EDT · **Closed:** 2026-08-06 20:23:37 EDT
**Plan:** [202608/bead\_snooze\_and\_notification\_indicator.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_snooze_and_notification_indicator.md)

## Description

bead-snooze-core: add the snoozed status, its embedded snooze record, snooze/cancel mutations, +1 target wake, and time-based wake selection to the bead store, then mirror the model and presentation in Python.

## Notes

[2026-08-07T00:23:37Z · sase-gn.4] Added the snoozed task-bead status end to end. Rust core (sase-core): StatusWire::Snoozed, BeadSnoozeWire + IssueWire.snooze with full validate() rules (task-only, record-iff-status, RFC-3339 until, plus_one_target > baseline, non-blank snoozed_at/by); snooze_task / cancel_task_snooze / wake_due_task_snoozes mutations; the add_task_plus_one snoozed branch (below target stays snoozed, at target wakes to Ready with the preset attributed note and suppresses the Open|Closed->Ready promotion); TaskSnoozed / TaskSnoozeCanceled / TaskSnoozeWoken events with reducer replay; snooze carried through jsonl/read/search projections and status filters; snoozed-status SQLite migration in schema.rs; pyo3 bindings. Python mirror: Status.SNOOZED, frozen SnoozeRecord with matching validate(), Issue.snooze + Issue.validate() constraints, shared snooze_codec, the grey diamond presentation entry between ready and in_progress, and the db/jsonl/wire/facade/BeadProject plumbing plus the status-list consumers (cli_query stats, cli_dep_render, beads_data, doctor, artifacts filter bar) and the status cycle. Verified: cargo test (all sase_core suites) + cargo clippy --all-targets + cargo fmt --check clean in sase-core; 'just check' green in the sase repo, where the Justfile change escalated the scoped lane to the full suite (26533 passed). Also fixed two pre-existing tests my migration invalidated: the db-migration column-order helper (the snoozed rebuild now restores declared column order) and the claimed-status stats ordering assertion (now includes the Snoozed row).

## Dependencies

- **Blocks:** [sase-gn.5](sase-gn.5.md) ✓ · ⧖ 2026-08-06
- **Blocks:** [sase-gn.6](sase-gn.6.md) ✓ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gn.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gn.4/README.md) | [sase-gn.4](sase-gn.4.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@d5a08da`](https://github.com/sase-org/sase-core/commit/d5a08da01b170a8b832c996cb14d92991e3b7522) | feat(bead): add the snoozed task-bead status with two wake conditions | [sase-gn.4](sase-gn.4.md) | 2026-08-06 20:24:21 EDT |
| sase | [`1f0d1a2`](https://github.com/sase-org/sase/commit/1f0d1a2ae39b68634be1e1176454f694fefba5ee) | feat(bead): mirror the snoozed task-bead status in Python | [sase-gn.4](sase-gn.4.md) | 2026-08-06 20:27:55 EDT |
