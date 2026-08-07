# Bead: sase-gn.10.1 — Stop a close from bricking a snoozed bead's store

[Bead Pages](../README.md) / [sase-gn.10](sase-gn.10.md) / sase-gn.10.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-gn.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gn.land/README.md) · **Assignee:** `sase-gn.10.1` · **Size:** medium
**Created:** 2026-08-07 00:13:41 EDT · **Closed:** 2026-08-07 00:27:27 EDT
**Plan:** [202608/snooze\_close\_corruption.md](https://github.com/sase-org/sase--plans/blob/main/202608/snooze_close_corruption.md)

## Description

snooze-close-core: clear the snooze record on every transition out of snoozed in both the mutation and the reducer, validate derived issues before the event log is written, and delete the orphaned wake-due-snooze selector.

## Dependencies

- **Blocks:** [sase-gn.10.2](sase-gn.10.2.md) ◐ · ⧖ 2026-08-07
- **Blocks:** [sase-gn.10.5](sase-gn.10.5.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gn.10.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gn.10.1/README.md) | [sase-gn.10.1](sase-gn.10.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@0c3e287`](https://github.com/sase-org/sase-core/commit/0c3e287f41842e68727b0bfc9e3001a1b2963b09) | fix(bead): stop a close from bricking a snoozed bead's store | [sase-gn.10.1](sase-gn.10.1.md) | 2026-08-07 00:28:14 EDT |
