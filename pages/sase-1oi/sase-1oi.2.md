# Bead: sase-1oi.2 — Production-shaped mounted TUI fixture

[Bead Pages](../README.md) / [sase-1oi](README.md) / sase-1oi.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.research.2i.linker.w0` · **Assignee:** `sase-1oi.2` · **Size:** medium
**Created:** 2026-10-26 15:05:48 EDT · **Closed:** 2026-10-27 00:22:11 EDT
**Plan:** [202610/muse\_commentary\_live\_reply.md](https://github.com/sase-org/sase--plans/blob/main/202610/muse_commentary_live_reply.md)

## Previously Closed

> ↺ Closed 2026-10-27T04:02:38Z · done
>
> (none)
>
> Reopened 2026-10-27T04:06:27Z by `sase bead open`

## Description

mounted-fixture: rewrite gated_muse_script so stdout carries no mid-run deltas and commentary arrives only through a session log, then update the four mounted live-reply follow tests to assert commentary reaches the Reply card before the terminal event.

## Notes

[2026-10-27T03:33:29Z · sase-1oi.2] PROPOSED FOLLOW-UP: Retire the Muse commentary tail once muse exec --json exports message phase; parse that event, dedupe against the tail by message_id during transition, then remove the tail module and on_tick call site.

[2026-10-27T03:33:44Z · sase-1oi.2] PROPOSED FOLLOW-UP: Record a decisions-web strand for private provider logs feeding display-only surfaces and never control flow; the epic decision_record was finalized as no.

[2026-10-27T03:52:16Z · sase-1oi.2] PROPOSED FOLLOW-UP: Resolve the two known capacity-scan check failures: test_capacity_blocked_waiter_does_not_park_the_queue_behind_it (unreleased core pruning drops fake PIDs 100/101/102) and test_capacity_only_scan_preserves_admission_and_candidate_decisions (capacity-only/full accounting differs after sase-1om.2). Both reproduce on clean master; prior evidence is sase-1om.3 notes #2/#3 and sase-1oe.3 note #2. No exact task bead tracks these test failures.

[2026-10-27T04:02:38Z · sase-1oi.2] Rewrote the mounted Muse fixture to emit only lifecycle events during gated tool stages and write commentary to its session log. Updated all four mounted Reply-card tests to assert commentary before terminal output. The first check passed lint and reported 57,928 passed, 17 skipped, plus two capacity-scan failures already reproduced on clean master (sase-1om.3 notes #2/#3; sase-1oe.3 note #2). A subsequent sase tool run check passed. Epic symbols: none.

[2026-10-27T04:22:11Z · sase-1oi.2] Rewrote gated_muse_script to emit only task.lifecycle/model.configured on stdout with commentary via its own session log (plus an unphased final message); all four mounted Reply-card tests now assert commentary-before-terminal, single-answer, and no-duplication, and pass. sase tool run check verdict: pass (lint gates + scoped lane); fmt applied.

## Dependencies

- **Depends on:** [sase-1oi.1](sase-1oi.1.md) ✓ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1oi.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1oi.2/README.md) | [sase-1oi.2](sase-1oi.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`027125d`](https://github.com/sase-org/sase/commit/027125d57b651d99cdd31d6f294476395bef7e85) | test(tui): mount production-shaped Muse commentary fixture in live-reply follow tests | [sase-1oi.2](sase-1oi.2.md) | 2026-10-27 00:23:57 EDT |
