# Bead: sase-1pj.5 — Stage monitor starts and spawn after finalization

[Bead Pages](../README.md) / [sase-1pj](README.md) / sase-1pj.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5f.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5f.linker.w0.md) · **Assignee:** `sase-1pj.5` · **Size:** large
**Created:** 2026-10-28 20:28:59 EDT · **Closed:** 2026-10-31 08:33:43 EDT
**Plan:** [202610/staged\_handoffs.md](https://github.com/sase-org/sase--plans/blob/main/202610/staged_handoffs.md)

## Description

monitor-staging: split monitor start into CLI-time preflight/stage and post-finalizer spawn, integrate prepared (-f) completion and -J joins, and close the just-fix race between monitor checks and the commit finalizer.

## Notes

[2026-10-30T20:35:12Z · sase-1pj.5.1.land] LANDING BLOCKER: implementation and verification are complete, but nested closeout is waiting on the host-owned landing of the Justfile cleanup. The current Justfile removes all four sase-1pj.5.1 epic-symbol rows; the four symbols are private or deleted, `just symvision` passes, and `sase tool run check` passed as ToolRun a979738833b23ecfe67d0de6d32c8d85. However, `sase bead epic-symbols sase-1pj.5.1` still reports those same four rows from origin/master, and `sase bead close sase-1pj.5.1` refused to close for that reason. No force was used. After the host lands this change and origin/master no longer has those stale rows, rerun epic-symbols, close sase-1pj.5.1, set plan:202610/monitor_staging.md status to done, then close only phase sase-1pj.5; leave outer epic sase-1pj open. The repair follow-up dispositions are recorded in the child note.

[2026-10-31T12:35:11Z · sase-1pj.5.1.land] PHASE CLOSEOUT VERIFIED (sase-1pj.5.1 final lander): the note #1 blocker is resolved. feae9c8777 landed the Justfile cleanup, so epic-symbols for sase-1pj.5.1 and sase-1pj.5 are both empty. Closing sase-1pj.5.1 normally, without --force, cascaded this phase closed. Checked against the phase scope: (a) monitor start is split into a CLI-time preflight/stage step (frozen payload, reserved ToolRun/join/prepared intent, pending owner, Staged report) and a post-finalizer spawn by the monitor adopter. (b) Prepared -f intents are reserved at stage time, bound once at spawn, and use the green/red host-completion path (test_finalizers_prepared_bridge). (c) -J joins are reserved by the original starter and activate even when the run settles before adoption. (d) The just-fix race is closed: the launch waits for the real finalizer controller to settle (test_staged_monitor_waits_for_real_finalizer_controller, test_adoption_waits_for_finalizer_settlement). A failed finalization launches nothing, keeps the held stage, and releases its reservations. (e) The promotion, real-response/exact-continuation, and frozen-checkpoint repairs are verified in current source. With the flag off, and for non-agent starts, the immediate start path is unchanged. Integration fixes in this landing: the sase monitor start help text and the staged_handoffs flag description now cover staged monitors, and the generated docs/schema were refreshed. Checks: sase tool run check c9e76124c5e49cb90956fe00f4815d43 succeeded; just symvision is clean; 586 targeted tests passed. plan:202610/monitor_staging.md is set to status: done. Containing epic sase-1pj is left to its land agent; sase-1pj.6 and sase-1pj.7 now have this dependency satisfied.

## Dependencies

- **Depends on:** [sase-1pj.1](sase-1pj.1.md) ✓ · ⧖ 2026-10-28
- **Depends on:** [sase-1pj.2](sase-1pj.2.md) ✓ · ⧖ 2026-10-28
- **Blocks:** [sase-1pj.6](sase-1pj.6.md) ◐ · ⧖ 2026-10-28
- **Blocks:** [sase-1pj.7](sase-1pj.7.md) ◐ · ⧖ 2026-10-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.5.md) | [sase-1pj.5](sase-1pj.5.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pj.4.1.land][1] | Check whether staged self-wait helper overlaps gate own-stage wait refusal | 1 |
| read-by | [agent:sase-1pj.5.1.3][2] | Check the enclosing epic and phase decisions for constraints | 1 |
| read-by | [agent:sase-1pj.5.1.4][3] | Need parent epic DECISIONS | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.4.1.land/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.5.1.3/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.5.1.4/README.md

<!-- sase:referenced-by:end -->
