# Bead: sase-1qk.3 — Reclaim dead-owner reservations and admit monitors before spawning

[Bead Pages](../README.md) / [sase-1qk](README.md) / sase-1qk.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.16r](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.16r.md) · **Assignee:** `sase-1qk.3` · **Size:** medium
**Created:** 2026-11-01 12:02:55 EST · **Closed:** 2026-11-01 12:18:03 EST
**Plan:** [202611/16p\_stall\_handoff\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202611/16p_stall_handoff_recovery.md)

## Description

handoff-slot: reclaim staging reservations whose owner died; run handoff admission before legacy monitor start spawns.

## Notes

[2026-11-01T17:18:03Z · sase-1qk.3] Dead-pid and identity-mismatch staging reservations are reclaimed to timestamped .sase_handoff_staging.stale-*.json evidence; live, malformed, and no-pid reservations keep occupying, with owner pid and liveness in the refusal. Legacy sase monitor start runs handoff_guard before start_monitor when SASE_AGENT is set and stops a spawned monitor if the post-spawn handoff still fails. Tests cover reclaim, fail-closed occupying, pre-spawn refusal with no start_monitor call, and the race stop path.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1qk.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qk.3.md) | [sase-1qk.3](sase-1qk.3.md) | 0 |
