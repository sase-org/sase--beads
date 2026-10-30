# Bead: sase-1pu.2 — Keep long-waiting bead agents alive when their dependency wakes (sase-12v)

[Bead Pages](../README.md) / [sase-1pu](README.md) / sase-1pu.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pn.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pn.land.md) · **Assignee:** `sase-1pu.2` · **Size:** large
**Created:** 2026-10-29 19:19:01 EDT · **Closed:** 2026-10-29 21:22:40 EDT
**Plan:** [202610/task\_backlog\_epic\_3.md](https://github.com/sase-org/sase--plans/blob/main/202610/task_backlog_epic_3.md)

## Description

waiter-wake-recovery: reproduce the wake-time NameCollisionError after a long wait, identify the reservation or retry failure, and make the wake path recover or retry safely without launching duplicate successors. Preserve the original dependency and workspace state. Review the related sase-1el monitor-start report, but do not assume a shared root cause from the exception class alone.

## Notes

[2026-10-30T00:02:28Z · sase-1pu.2] Real-path replay evidence: an isolated registry-only stale owner is removed by the name-reservation load's staleness rebuild, and the refreshed bead waiter claims the same artifact identity; a rebuild containing a different live owner still raises NameCollisionError and leaves both artifact records intact. The historical sase-12v traceback remains unavailable, so this synthetic stale-owner case cannot be tied to the September 18 failure. The focused runner, registry, wait, bootstrap, handoff, and epic-launch modules pass (113 tests); repository check is still running.

[2026-10-30T01:22:25Z · sase-1pu.2--1] TASK RESOLVED: sase-12v — No new runner change was needed: the production refreshed claim rebuilds a stale registry-only owner, and the existing refresh path preserves the same waiter name. Real-registry regressions cover a simulated 41-hour wait with source refresh, preserved bead/clan/workspace/dependency/wait metadata, one workflow launch, wake without source update, refusal of a genuine live foreign owner, and session-attach payload replay. The focused module passes 4 tests; relevant existing runner, refresh, wait, registry, bootstrap, and bead-launch modules passed 113 tests. Final sase tool run check de8580e57016e8cae218b4247b099345 exited 0 with pass verdict and KNOWN 0 / FLAKY 0. The missing historical evidence artifact prevents tying the synthetic stale-owner case to the September report.

[2026-10-30T01:22:40Z · sase-1pu.2--1] Acceptance rechecked against plan: refreshed and unchanged-source waiter paths launch once; stale registry-only ownership rebuilds to the same artifact identity; live foreign ownership is refused; dependency barrier, wait marker, bead/clan/workspace context, and attach payload survive replay; existing explicit-collision, clan handoff, failed execv cleanup, and import-free refresh regressions remain covered. Focused regression: 4 passed; relevant existing modules: 113 passed; final sase tool run check passed with exit 0, KNOWN 0, FLAKY 0. No epic-symbol entries remained.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pu.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pu.2.md) | [sase-1pu.2](sase-1pu.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`188073f`](https://github.com/sase-org/sase/commit/188073fe063976592272847ff383578229d1aabf) | test(axe): cover waiter name recovery after refresh | [sase-1pu.2](sase-1pu.2.md) | 2026-10-29 21:24:01 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pu.2--1][1] | Verify the assigned phase closure before final declaration | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pu.2.md

<!-- sase:referenced-by:end -->
