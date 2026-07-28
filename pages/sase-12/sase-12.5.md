# Bead: sase-12.5 — Phase 5 — Unify launch fan-out + source-aware refresh coalescing

[Bead Pages](../README.md) / [sase-12](README.md) / sase-12.5

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-12.5`
**Created:** 2026-04-28 22:45:29 UTC · **Closed:** 2026-04-28 23:04:01 UTC
**Plan:** [202604/tui\_perf\_v2.md](https://github.com/sase-org/sase--plans/blob/main/202604/tui_perf_v2.md)

## Description

Replace threading.Thread fan-out in agent_workflow helpers with asyncio.to_thread / Textual workers, snapshot launch context on the UI thread, and add request_agents_refresh(source, debounce_ms, latest_only) so multi-prompt/multi-model/repeat/bulk launches collapse into a single coalesced refresh. See plans/202604/tui_perf_v2.md (Phase 5).

## Notes

COMMIT: 6d902520

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`156face`](https://github.com/sase-org/sase/commit/156face4685e0dec827a3915379750b1df3567e1) | feat(ace/tui/perf): unify launch fan-out + coalesce refresh (sase-12.5) | [sase-12.5](sase-12.5.md) | 2026-04-28 23:04:05 |
