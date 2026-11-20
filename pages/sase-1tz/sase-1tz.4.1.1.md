# Bead: sase-1tz.4.1.1 — Treat SQLite's busy -1 checkpoint result as busy and checkpoint passively on read paths

[Bead Pages](../README.md) / [sase-1tz.4.1](sase-1tz.4.1.md) / sase-1tz.4.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.4.md) · **Assignee:** `sase-1tz.4.1.1` · **Size:** small
**Created:** 2026-11-20 14:00:21 EST · **Closed:** 2026-11-20 14:24:04 EST
**Plan:** [202611/hygiene\_gateway\_notifications\_retention.md](https://github.com/sase-org/sase--plans/blob/main/202611/hygiene_gateway_notifications_retention.md)

## Description

wal_busy: in sase-core, a busy wal_checkpoint that returns -1 counts reports checkpoint_busy instead of failing u64 conversion. The gateway's post-build hook uses PASSIVE and runs after waiters are woken. Maintenance keeps TRUNCATE. Move the pin.

## Notes

[2026-11-20T19:24:04Z · sase-1tz.4.1.1] sase-core: wal_checkpoint busy/-1 frame counts no longer fail u64 conversion (busy outcome); new PASSIVE|TRUNCATE mode fn, maintenance keeps TRUNCATE; gateway checkpoint hook now PASSIVE and runs after waiters are woken (still under index permit). sase tool run check passed in sase-core. Pin move is done by host commit of the pinned sibling.

## Dependencies

- **Blocks:** [sase-1tz.4.1.2](sase-1tz.4.1.2.md) ✓ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.4.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.1/README.md) | [sase-1tz.4.1.1](sase-1tz.4.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@553387d`](https://github.com/sase-org/sase-core/commit/553387d39df464c4989e0deba2725f71cf32c60e) | fix(agent-index): treat busy -1 WAL checkpoint as busy and checkpoint passively in the gateway | [sase-1tz.4.1.1](sase-1tz.4.1.1.md) | 2026-11-20 14:24:35 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.4.1.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.1/README.md

<!-- sase:referenced-by:end -->
