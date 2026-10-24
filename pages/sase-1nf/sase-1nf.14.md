# Bead: sase-1nf.14 — Fix the measured GC freeze causes

[Bead Pages](../README.md) / [sase-1nf](README.md) / sase-1nf.14

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.12i](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.12i.md) · **Assignee:** `sase-1nf.14` · **Size:** large
**Created:** 2026-10-20 13:36:16 EDT
**Plan:** [202610/athena\_apollo\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/athena_apollo_audit_fixes.md)

## Description

gc-fix: plan from the measurement report, reduce allocation and retention at the measured producers before touching collector policy, resolve the backstop quiet-window conflict, and prove sase-1f3's targets on restarted TUIs. Closes sase-1nc.

## Notes

[2026-10-24T11:11:33Z · sase-1nv.1] GC closeout handoff: research:202610/tui_gc_measurement_20261023.md records r5 complete, gap-free four-hour windows on Athena (Python 3.14.7) and Apollo (3.12.3), ranked producer mechanisms, census types, and fault/swap correlation. These findings do not establish target acceptance. No representative busy hour was measured: r5 has one Athena prev and no Apollo navigation samples; r6 was interrupted after 1,206.768s Athena / 901.055s Apollo post-warmup and r7 found both replacement TUIs unflagged with zero census rows. Historical navigation is baseline only: r4 Athena Agents j/k p95 215.26ms n=52, Apollo largest hour 12 j/k actions, r6 short windows 3 Athena / 31 Apollo next/prev. Ranked priorities: Agent graph replacement / copy_agent_graph cycles; Textual Strip/FIFOCache render self-cycles; large archive/event/completion populations. Experiments identify mechanisms, not shares of live allocation traffic or proof of leaks. Before trusting tools/tui_freeze_report, fix/work around: unsorted idle p95; PASS with incomplete coverage or late hitches; endpoint-only swap; paired-heartbeat and float-boundary errors; mixed action types counted as j/k. Capture flags must be set in the shell launching sase tui; full relaunch loses them and restarts create new instances. Verify flags and early real j/k on both hosts before a long window. Perf rows have no PID/instance; use wall-clock bounds and one TUI per host. gc-fix acceptance now owns a representative busy hour, fixed-code Agents j/k p95 <16ms, other-tab latency, prompt-active comparison, and the 24-hour soak (gc_soak=no).

## Dependencies

- **Depends on:** [sase-1nf.13](sase-1nf.13.md) ✓ · ⧖ 2026-10-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.14](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.14.md) | [sase-1nf.14](sase-1nf.14.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nf.14.1.1][1] | Need parent phase scope and decisions relevant to this phase | 1 |
| read-by | [agent:sase-1nv.1][2] | Verify the GC closeout handoff was recorded for the receiving phase | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.14.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nv.1/README.md

<!-- sase:referenced-by:end -->
