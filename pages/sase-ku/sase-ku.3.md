# Bead: sase-ku.3 — Durable process identity for the supervisor and its child

[Bead Pages](../README.md) / [sase-ku](README.md) / sase-ku.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-kp.land.w1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-kp.land.w1.md) · **Assignee:** `sase-ku.3` · **Size:** small
**Created:** 2026-08-13 09:02:42 EDT · **Closed:** 2026-08-13 10:27:45 EDT
**Plan:** 202608/monitor\_hardening.md

## Description

identity: persist the monitored command's pgid and a boot-id/start-ticks identity for the supervisor pid before the command can outlive its recorder, scrub agent identity from the command's environment, and validate identity before signalling.

## Notes

[2026-08-13T14:27:14Z · sase-ku.3] Verified: pgid/boot-id identity persisted before the wait loop (supervise.py), agent-identity env scrubbed for both the supervisor spawn (start.py) and the monitored command (supervise.py), and stop_monitor/reconciliation now use supervisor_is_alive() instead of a bare pid check (store.py). 79/79 monitor tests pass. just check reproduces one pre-existing flaky test (test_start_monitor_promotes_a_bare_lane_and_runs_to_completion) only under the full escalated parallel run; git blame confirms the racy done.json-before-claim-release ordering in supervise.py:295 vs :321/:330 was committed in b32167c31b (already-closed sase-ku.2), untouched by this diff, and matches the epic plan's documented 'terminal state precedes settlement' defect explicitly scoped to sase-ku.4. Not a regression from this phase's work.

[2026-08-13T14:27:45Z · sase-ku.3] Persisted monitor_pgid and a boot-id/start-ticks supervisor identity, scrubbed agent identity env from both the supervisor spawn and the monitored command, and switched stop/reconciliation to identity-checked liveness (supervisor_is_alive). Verified via 79/79 passing monitor tests plus two just-check runs; the sole recurring failure is a pre-existing, already-committed settlement-ordering race (git blame: b32167c31b, sase-ku.2) explicitly scoped to sase-ku.4, not introduced by this diff.

## Dependencies

- **Depends on:** [sase-ku.1](sase-ku.1.md) ✓ · ⧖ 2026-08-13
- **Depends on:** [sase-ku.2](sase-ku.2.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-ku.4](sase-ku.4.md) ✓ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ku.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ku.3/README.md) | [sase-ku.3](sase-ku.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`40d9a4d`](https://github.com/sase-org/sase/commit/40d9a4d98cb255904a84edf493ab84f998c90cc5) | feat(monitor): give the supervisor and its child a durable identity | [sase-ku.3](sase-ku.3.md) | 2026-08-13 10:29:07 EDT |
