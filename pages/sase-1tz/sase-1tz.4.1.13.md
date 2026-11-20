# Bead: sase-1tz.4.1.13 — Fix the proc log-lock and registry temp-file leaks and reap their backlog

[Bead Pages](../README.md) / [sase-1tz.4.1](sase-1tz.4.1.md) / sase-1tz.4.1.13

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.4.md) · **Assignee:** `sase-1tz.4.1.13` · **Size:** medium
**Created:** 2026-11-20 14:00:25 EST
**Plan:** [202611/hygiene\_gateway\_notifications\_retention.md](https://github.com/sase-org/sase--plans/blob/main/202611/hygiene_gateway_notifications_retention.md)

## Description

clutter_reapers: deleting proc logs also removes their lock files. The name-registry writer sweeps its own stale temp files under its lock. Owner steps reap both backlogs from the log_horizons chop. Index backups follow the index_backups decision.

## Dependencies

- **Depends on:** [sase-1tz.4.1.12](sase-1tz.4.1.12.md) ✓ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.4.1.13](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.13/README.md) | [sase-1tz.4.1.13](sase-1tz.4.1.13.md) | 0 |
