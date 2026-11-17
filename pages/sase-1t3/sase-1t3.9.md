# Bead: sase-1t3.9 — Post-storm GC census and heap-owner attribution

[Bead Pages](../README.md) / [sase-1t3](README.md) / sase-1t3.9

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.62.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.62.linker.w0.md) · **Assignee:** `sase-1t3.9` · **Size:** medium
**Created:** 2026-11-16 07:57:55 EST
**Plan:** [202611/tui\_storm\_trust\_heap\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202611/tui_storm_trust_heap_recovery.md)

## Description

heap-census: soak a separate TUI instance with the GC census at about 10 min and 2 h, then record a ranked list of surviving heap owners with code anchors for the heap-diet phases. Coordinate with sase-1sl.4.

## Notes

[2026-11-17T11:14:33Z · sase-1t3.9] SOAK STARTED: dedicated tmux session sase-1t3-9-census, pid 3987386, app_instance_id a428c9ee, Python 3.14.7, HEAD 694cdec86b (storm-hotfix ancestor), SASE_TUI_GC_CENSUS=1, logs /home/bryan/.sase/perf/sase-1t3.9/gc_census_20261117T111346Z/. Live TUI pid 3161729 left untouched. Census tooling now emits watchlist, shallow bytes, and known_caches. First idle census ~10 min, soak through ~2 h.

[2026-11-17T11:17:40Z · sase-1t3.9] SOAK RELAUNCHED after executor-gauge bind fix: tmux sase-1t3-9-census pid 4050454 instance d5ac2b89 logs /home/bryan/.sase/perf/sase-1t3.9/gc_census_20261117T111640Z/. First heartbeat RSS 1.24 GB, allocated_blocks 7.13M, default_executor 32 workers/16 threads/queue 0/not saturated. Python 3.14.7, HEAD 694cdec86b, census on, live TUI 3161729 untouched. Prior attempt a428c9ee discarded.

## Dependencies

- **Depends on:** [sase-1t3.1](sase-1t3.1.md) ✓ · ⧖ 2026-11-16
- **Blocks:** [sase-1t3.10](sase-1t3.10.md) ◐ · ⧖ 2026-11-16
- **Blocks:** [sase-1t3.11](sase-1t3.11.md) ◐ · ⧖ 2026-11-16
- **Blocks:** [sase-1t3.14](sase-1t3.14.md) ◐ · ⧖ 2026-11-16
- **Depends on:** [sase-1t3.2](sase-1t3.2.md) ✓ · ⧖ 2026-11-16
- **Depends on:** [sase-1t3.3](sase-1t3.3.md) ✓ · ⧖ 2026-11-16
- **Depends on:** [sase-1t3.5](sase-1t3.5.md) ✓ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.9/README.md) | [sase-1t3.9](sase-1t3.9.md) | 0 |
