# Bead: sase-1qk.3 — Reclaim dead-owner reservations and admit monitors before spawning

[Bead Pages](../README.md) / [sase-1qk](README.md) / sase-1qk.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.16r](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.16r.md) · **Assignee:** `sase-1qk.3` · **Size:** medium
**Created:** 2026-11-01 12:02:55 EST · **Closed:** 2026-11-01 15:32:52 EST
**Plan:** [202611/16p\_stall\_handoff\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202611/16p_stall_handoff_recovery.md)

## Previously Closed

> ↺ Closed 2026-11-01T17:18:03Z · done
>
> (none)
>
> Reopened 2026-11-01T19:23:49Z by `sase bead open`

## Description

handoff-slot: reclaim staging reservations whose owner died; run handoff admission before legacy monitor start spawns.

## Notes

[2026-11-01T17:18:03Z · sase-1qk.3] Dead-pid and identity-mismatch staging reservations are reclaimed to timestamped .sase_handoff_staging.stale-*.json evidence; live, malformed, and no-pid reservations keep occupying, with owner pid and liveness in the refusal. Legacy sase monitor start runs handoff_guard before start_monitor when SASE_AGENT is set and stops a spawned monitor if the post-spawn handoff still fails. Tests cover reclaim, fail-closed occupying, pre-spawn refusal with no start_monitor call, and the race stop path.

[2026-11-01T19:25:57Z · sase-1qk.3--2] Join-start tests now set SASE_ARTIFACTS_DIR so pre-spawn handoff admission can run; targeted join/admission/reclaim tests passed (62).

[2026-11-01T20:32:33Z · sase-1qk.3--4] PROPOSED FOLLOW-UP: test_visible_paged_restore_still_moves_viewport timed out in wait_for(_ready_spread_panel) under full-lane just check (core-identity-changed; tool run 37eaf76745dc112655d66d76c44e7cab) — passes isolated 1.69s on this tree; same Files-deck load-timeout class as closed sase-1a7 (exact node in its note 3) and ready sase-1qd (sibling node in the same file).

[2026-11-01T20:32:52Z · sase-1qk.3--4] Dead-pid and identity-mismatch staging reservations reclaim to timestamped .sase_handoff_staging.stale-*.json; live, malformed, and no-pid reservations keep occupying, with owner pid and liveness in the refusal. Legacy sase monitor start runs handoff_guard before start_monitor when SASE_AGENT is set and stops a spawned monitor if the post-spawn handoff still fails. Verified 62 targeted reclaim/admission/join tests. Full-lane TUI timeout on test_visible_paged_restore_still_moves_viewport is PROPOSED FOLLOW-UP (isolated pass 1.69s; sase-1a7/sase-1qd).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1qk.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qk.3.md) | [sase-1qk.3](sase-1qk.3.md) | 0 |
