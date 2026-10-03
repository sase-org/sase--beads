# Bead: sase-1ez.7 — Move fleet projection, digest building, and config-token refresh off the hot path

[Bead Pages](../README.md) / [sase-1ez](README.md) / sase-1ez.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vm](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vm.md) · **Assignee:** `sase-1ez.7` · **Size:** medium
**Created:** 2026-10-02 16:45:06 EDT · **Closed:** 2026-10-02 21:00:35 EDT
**Plan:** [202610/tui\_freeze\_gc\_heap.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_freeze_gc_heap.md)

## Description

off-loop-refresh: project fleet clan/tribe trees on the worker from immutable inputs and revalidate generation and selection on apply. Skip the prompt-panel Rich-tree digest on a cheap identity/content token. Replace the per-refresh Thread.start() in current_config_token() with one long-lived revalidator thread so the getter only peeks.

## Notes

[2026-10-02T21:15:36Z · sase-1ez.7] Verified: fleet project_fleet_agents runs via asyncio.to_thread with generation/tab/selection revalidation; prompt-panel update skips full digest on cheap token (identity fast path + CachedRenderable digests); config-token getter peeks with one long-lived revalidator (no Thread.start after warmup). Focused suites green: test_agents_fleet_refresh_off_loop (5), test_renderable_digest incl 3 new cheap-token tests, test_config_cache_token incl 2 new revalidator tests; full test_config_cache* lanes green. just check via verify monitor.

[2026-10-03T01:00:13Z · sase-1ez.7--3] PROPOSED FOLLOW-UP: full `just check` (tool run 81b29f848d4646864b4f5eb4b28b247f, loadavg ~32) showed 5 FAILED + 8 ERROR that all pass on this tree in isolation and in lane-grouped reruns (config-cache lane 39 passed; TUI/keymap batch 91 passed); timing-sensitive config-token drain/single-flight tests plus unrelated TUI fixture errors look like under-load flakes, consider quarantine or load-gating

[2026-10-03T01:00:35Z · sase-1ez.7--3] off-loop-refresh done: fleet projection via asyncio.to_thread with revalidation, cheap-token prompt-panel digest skip, long-lived config-token revalidator. Verified: config-cache lane 39 passed, TUI/keymap batch 91 passed, lint test-waits clean, 5 thread/timing tests stable across 3x reruns; full-check 13 failures reproduce neither in isolation nor grouped (under-load flakes, recorded as follow-up); no epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-1ez.8](sase-1ez.8.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ez.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ez.7.md) | [sase-1ez.7](sase-1ez.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f76efbe`](https://github.com/sase-org/sase/commit/f76efbe6b90882196c3d186d39968a8a0d676749) | feat(tui): move fleet projection, digest building, and config-token refresh off the hot path | [sase-1ez.7](sase-1ez.7.md) | 2026-10-02 21:02:49 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ez.7--3][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ez.7.md

<!-- sase:referenced-by:end -->
