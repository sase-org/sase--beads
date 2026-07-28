# Bead: sase-12.4 — Phase 4 — Incremental row-removal fast path

[Bead Pages](../README.md) / [sase-12](README.md) / sase-12.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-12.4`
**Created:** 2026-04-28 22:45:24 UTC · **Closed:** 2026-04-28 23:06:44 UTC
**Plan:** [202604/tui\_perf\_v2.md](https://github.com/sase-org/sase--plans/blob/main/202604/tui_perf_v2.md)

## Description

Add AgentList.try_remove_rows() to apply optimistic removes in place when conservative gates hold (agents tab, no search, STANDARD grouping, single panel, no workflow parents); fall back to full _refresh_agents_display otherwise. Wire kill+dismiss in-memory paths to use it. See plans/202604/tui_perf_v2.md (Phase 4).

## Notes

COMMIT: c11aad91

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`4b13664`](https://github.com/sase-org/sase/commit/4b13664c6ae3a07fa1b5df835dc36667dd82f7a0) | feat(ace/tui): incremental row-removal fast path for kill+dismiss (sase-12.4) | [sase-12.4](sase-12.4.md) | 2026-04-28 23:06:48 |
