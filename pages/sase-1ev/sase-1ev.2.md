# Bead: sase-1ev.2 — App-scoped history service and the public history kit

[Bead Pages](../README.md) / [sase-1ev](README.md) / sase-1ev.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vj.md) · **Assignee:** `sase-1ev.2` · **Size:** medium
**Created:** 2026-10-02 14:43:05 EDT · **Closed:** 2026-10-02 16:39:48 EDT
**Plan:** [202610/memory\_history\_tui.md](https://github.com/sase-org/sase--plans/blob/main/202610/memory_history_tui.md)

## Description

history-service: add one app-scoped AceMemoryHistory over a process-wide shared HistoryService, which the pager provider factory also uses. It provides a stale-while-revalidate timeline memo, content-addressed body and comparison LRUs, single-flight queries, stat-only change tokens, explicit invalidation, and a quiet-time warm-up. Also publish sase.pager.history_kit as the only door ACE uses for history presentation, and migrate the History row onto the service with an honest unavailable state.

## Notes

[2026-10-02T20:39:48Z · sase-1ev.2] history-service done: shared_history_service + pager factory share it; AceMemoryHistory (SWR timeline memo, blob-keyed body/comparison LRUs, single-flight, stat-only change tokens, explicit invalidation, 5s quiet probe, post-stopwatch warm-up); history_kit facade + promoted picker rows; History row on timeline() with unavailable+r-retry; r/publish/add/edit/delete/editor-return invalidate. Verified: 17 new service tests + kit-door guard + 19 panel history + 292 pager/memory tests pass; ruff/mypy/symvision/test-waits/keep-sorted clean; full check: all lint stages pass, 51664 tests pass with 5 failures (2 mine: ref-prefix allowlist + shard-timings refresh, fixed and re-verified; 3 flakes in untouched tool/config areas pass on rerun). Memo-hit timeline p95 0.002ms vs 16ms j/k budget. No pager golden changes; no epic-symbols needed.

## Dependencies

- **Depends on:** [sase-1ev.1](sase-1ev.1.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1ev.10](sase-1ev.10.md) ◐ · ⧖ 2026-10-02
- **Blocks:** [sase-1ev.3](sase-1ev.3.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ev.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ev.2/README.md) | [sase-1ev.2](sase-1ev.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f42f9f2`](https://github.com/sase-org/sase/commit/f42f9f225ad9a78892c357312c2b9efb988bd7c2) | feat(history): shared history service with ACE SWR timeline and pager history kit | [sase-1ev.2](sase-1ev.2.md) | 2026-10-02 16:42:13 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ev.2][1] | check prior work notes | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ev.2/README.md

<!-- sase:referenced-by:end -->
