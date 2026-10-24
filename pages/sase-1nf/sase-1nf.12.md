# Bead: sase-1nf.12 — GC attribution telemetry and an acceptance-grade freeze report

[Bead Pages](../README.md) / [sase-1nf](README.md) / sase-1nf.12

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.12i](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.12i.md) · **Assignee:** `sase-1nf.12` · **Size:** medium
**Created:** 2026-10-20 13:36:15 EDT · **Closed:** 2026-10-20 15:18:17 EDT
**Plan:** [202610/athena\_apollo\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/athena_apollo_audit_fixes.md)

## Description

gc-instrument: fix tui_freeze_report's startup-row, rotation, and trigger handling and add an acceptance mode, add collection start, input age, fault deltas, source revision, and allocator stats to TUI telemetry, and add an opt-in GC census. Closes sase-1f4.

## Notes

[2026-10-20T19:18:17Z · sase-1nf.12] Verified gc-instrument: tui_freeze_report parses ISO timestamp, reads tui_stalls.jsonl.1 unless --no-rotated, splits idle/backstop/rss_backstop/startup_freeze/automatic, counts automatic+backstop gen-2 near input (prefers input_age_s), sums heartbeat loop_hitch_seconds including suppressed, --acceptance marks sase-1f3 targets (exit 1 on fail). Pause rows gain start_ts/input_age_s/major_faults_delta (callback stays lock-free; getrusage for faults). Heartbeats gain gc_stats/allocated_blocks/python_version. Startup rows gain source_revision (closes sase-1f4). Opt-in SASE_TUI_GC_CENSUS=1 idle census every 10m with DEBUG_SAVEALL top-40 types. Privatized unused public helpers for Symvision. Targeted 71 tests passed; sase tool run check fa0dbd8c2ef41d91c90c9d481e6d41b3 green (symvision+scoped tests). epic-symbols empty. gc_soak=no left for later phases.

## Dependencies

- **Blocks:** [sase-1nf.13](sase-1nf.13.md) ◐ · ⧖ 2026-10-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.12/README.md) | [sase-1nf.12](sase-1nf.12.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`aae7eae`](https://github.com/sase-org/sase/commit/aae7eae66779aa03486f215f7b44defa2912a508) | feat(tui): add GC attribution telemetry and an acceptance freeze report | [sase-1nf.12](sase-1nf.12.md) | 2026-10-20 15:19:41 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nf.12][1] | Need close-note evidence and whether sase-1f4 is in this phase's close set | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.12/README.md

<!-- sase:referenced-by:end -->
