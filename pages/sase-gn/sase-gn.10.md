# Bead: sase-gn.10 — Repair the snooze close path and finish landing epic sase-gn

[Bead Pages](../README.md) / [sase-gn](README.md) / sase-gn.10

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-gn.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gn.land/README.md) · **Assignee:** `sase-gn.10.land`
**Created:** 2026-08-07 00:13:34 EDT
**Plan:** [202608/snooze\_close\_corruption.md](https://github.com/sase-org/sase--plans/blob/main/202608/snooze_close_corruption.md)

## Description

Closing a snoozed task bead succeeds, drops the snooze record, and leaves the store readable, including stores already bricked by the defect; the bead event log can no longer be persisted ahead of the state it derives; the dead wake-due-snooze selector is gone from the Rust core; the two rival snooze parsers are one; `sase bead list` shows snoozed beads by default like `sase bead search` already does; and epic sase-gn is closed with its plan file marked done.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gn.10.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gn.10.land/README.md) | [sase-gn.10](sase-gn.10.md) | 0 |
