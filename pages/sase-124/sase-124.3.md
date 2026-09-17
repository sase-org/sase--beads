# Bead: sase-124.3 — Take the federation attention RPC off the auto-refresh critical path

[Bead Pages](../README.md) / [sase-124](README.md) / sase-124.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0mc](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0mc.md) · **Assignee:** `sase-124.3` · **Size:** medium
**Created:** 2026-09-17 10:59:43 EDT · **Closed:** 2026-09-17 14:44:37 EDT
**Plan:** [202609/agents\_tab\_freshness.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_freshness.md)

## Description

tick-diet: make per-tick fleet-attention polling cache-backed with a longer network recompute cadence, run it concurrently with local surfaces, and add tick trace counters for it.

## Notes

[2026-09-17T18:44:37Z · sase-124.3] Implemented cache-backed fleet-attention auto-refresh with background network cadence and trace counters; verified with uv run pytest -q tests/ace/tui/test_remote_lifecycle_actions.py tests/ace/tui/test_event_handlers_auto_refresh_dirty_flags.py, just fmt, just check (passed; scoped lane escalated to full suite), and sase bead epic-symbols sase-124.3 (none).

## Dependencies

- **Blocks:** [sase-124.7](sase-124.7.md) ✓ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-124.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-124.3/README.md) | [sase-124.3](sase-124.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0af5b08`](https://github.com/sase-org/sase/commit/0af5b08151ac275b81cc1d2e790b29d1d43df53d) | perf(tui): cache fleet attention auto-refresh | [sase-124.3](sase-124.3.md) | 2026-09-17 14:46:35 EDT |
