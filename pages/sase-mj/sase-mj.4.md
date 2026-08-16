# Bead: sase-mj.4 — Perf view rendering

[Bead Pages](../README.md) / [sase-mj](README.md) / sase-mj.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.032](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.032.md) · **Assignee:** `sase-mj.4` · **Size:** medium
**Created:** 2026-08-15 20:26:22 EDT · **Closed:** 2026-08-15 23:46:22 EDT
**Plan:** [202608/statistics\_perf\_view.md](https://github.com/sase-org/sase--plans/blob/main/202608/statistics_perf_view.md)

## Description

perf_render: build the Perf renderable — the five hero tiles, the TUI startup and stall panels, the grouped latency table, the data-and-instrumentation strip, and every degraded, partial, and empty state.

## Notes

[2026-08-16T03:44:40Z · sase-mj.4] PROPOSED FOLLOW-UP: Pre-existing whole-repo Symvision unused-public-symbol failures on HEAD — FilesQueryIndexResult, PublicationDrainTimedOut, StreamIntegrityResult, analyze_stream_against_ancestor, clear_agent_page_url_registry_cache, configured_publication_drain_timeout, encode_stream_events, is_event_stream_relpath, parse_stream_text. Reproduced with my tree stashed; not caused by perf_render.

[2026-08-16T03:45:47Z · sase-mj.4] PROPOSED FOLLOW-UP: Flaky tests/ace/tui/test_top_bar_order.py::test_override_pills_keep_narrow_top_bar_in_bounds — full-suite run asserted CLAUDE(opus) vs CODEX(o3)@xhigh, rerun asserted " ... " vs the same expected string. Unrelated to Statistics Perf rendering.

[2026-08-16T03:46:22Z · sase-mj.4] Perf view rendering is in place: StatisticsPerfRenderingMixin paints the five hero tiles (reuse render_stat_tile; telemetry-disabled tiles name telemetry.enabled), stacked/wide startup+stalls panels, grouped latency table (subsystem/provider/workflow, tokens in provider mode), and the data-and-instrumentation strip (store resolution/freshness, per-log present/truncated/malformed, probe env hints). Empty/absent-log/no-samples/disabled/partial-coverage states all render instead of a blank view. Perf tiles are plain non-interactive Static widgets (no Overview tooltip/click). Verified: tests/ace/tui/test_statistics_perf.py (12) plus legends/overview-click/empty-bypass tests pass; just check lint gates through ruff/mypy/toobig/validate pass; just check fails on pre-existing HEAD Symvision unused symbols (not this phase); escalated full suite 30689 passed / 2 unrelated failures (flaky top-bar pill + one config-cache flake that passed on retry).

[2026-08-16T03:47:44Z · sase-mj.4] Perf view rendering: five hero tiles, startup/stall panels (wide+stacked), grouped latency table, data-and-instrumentation strip, degraded/empty states. Perf tiles are non-interactive Static widgets. Verified: tests/ace/tui/test_statistics_perf.py (12) plus legends/overview-click/empty-bypass; lint ruff/mypy/toobig/validate green; pre-existing HEAD Symvision unused-symbol failures and two unrelated full-suite flakes recorded as follow-ups.

## Dependencies

- **Depends on:** [sase-mj.3](sase-mj.3.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-mj.5](sase-mj.5.md) ◐ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mj.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mj.4/README.md) | [sase-mj.4](sase-mj.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9a3a861`](https://github.com/sase-org/sase/commit/9a3a8617cac79b79217520fbc5ba8c33bde5f17b) | feat(ace): render the Statistics Perf dashboard | [sase-mj.4](sase-mj.4.md) | 2026-08-15 23:48:50 EDT |
