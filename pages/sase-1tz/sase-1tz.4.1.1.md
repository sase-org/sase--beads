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

[2026-11-21T12:37:28Z · sase-1tz.4.1.land] MEASURE wal_busy (recorded by the sase-1tz.4.1 land agent, read-only, 2026-11-21 ~07:30 EST; the phase itself recorded none). The pre-fix gateway logs 'out of range integral type conversion attempted' / 'fleet index WAL checkpoint failed' only when a TRUNCATE checkpoint hits -1 counts. apollo ~/.sase/service/procs/gateway/output.log (2 MiB size-capped, single segment, 2026-11-14T22:42Z..2026-11-21T12:29Z, ~6.5 days, 6,482 'fleet snapshot build finished' lines): out_of_range=0, checkpoint_failed=0, checkpointed=0; ~/.sase/agent_artifact_index.sqlite-wal absent (index 122,433,536 B). athena: gateway runs (pid restarted 2026-11-21 06:10) but output.log is 0 bytes with mtime 2026-09-20, so it has no fleet traffic to measure; agent_artifact_index.sqlite-wal 0 B. So the F11 error string did not recur in the retained window; the fix's value is the busy outcome plus PASSIVE-after-wake ordering. AFTER-INSTALL (each host; apollo via ssh): L=~/.sase/service/procs/gateway/output.log; for p in 'out of range integral type conversion attempted' 'fleet index WAL checkpoint failed' 'fleet index WAL checkpointed' 'checkpoint_busy=true'; do printf '%s=%s\n' "$p" "$(grep -c "$p" $L)"; done; ls -l ~/.sase/agent_artifact_index.sqlite-wal. Expect out_of_range=0 and checkpoint_failed=0; busy outcomes log at info as 'fleet index WAL checkpointed' with checkpoint_busy=true.

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
| read-by | [agent:sase-1tz.4.1.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.land/README.md

<!-- sase:referenced-by:end -->
