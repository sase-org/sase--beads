# Bead: sase-1ez.7 — Move fleet projection, digest building, and config-token refresh off the hot path

[Bead Pages](../README.md) / [sase-1ez](README.md) / sase-1ez.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vm](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vm.md) · **Assignee:** `sase-1ez.7` · **Size:** medium
**Created:** 2026-10-02 16:45:06 EDT
**Plan:** [202610/tui\_freeze\_gc\_heap.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_freeze_gc_heap.md)

## Description

off-loop-refresh: project fleet clan/tribe trees on the worker from immutable inputs and revalidate generation and selection on apply. Skip the prompt-panel Rich-tree digest on a cheap identity/content token. Replace the per-refresh Thread.start() in current_config_token() with one long-lived revalidator thread so the getter only peeks.

## Notes

[2026-10-02T21:15:36Z · sase-1ez.7] Verified: fleet project_fleet_agents runs via asyncio.to_thread with generation/tab/selection revalidation; prompt-panel update skips full digest on cheap token (identity fast path + CachedRenderable digests); config-token getter peeks with one long-lived revalidator (no Thread.start after warmup). Focused suites green: test_agents_fleet_refresh_off_loop (5), test_renderable_digest incl 3 new cheap-token tests, test_config_cache_token incl 2 new revalidator tests; full test_config_cache* lanes green. just check via verify monitor.

## Dependencies

- **Blocks:** [sase-1ez.8](sase-1ez.8.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ez.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ez.7.md) | [sase-1ez.7](sase-1ez.7.md) | 0 |
