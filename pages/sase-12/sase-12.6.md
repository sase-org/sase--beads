# Bead: sase-12.6 — Phase 6 — Quarantine legacy synchronous kill handlers

[Bead Pages](../README.md) / [sase-12](README.md) / sase-12.6

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-12.6`
**Created:** 2026-04-28 22:45:34 UTC · **Closed:** 2026-04-28 23:14:39 UTC
**Plan:** [202604/tui\_perf\_v2.md](https://github.com/sase-org/sase--plans/blob/main/202604/tui_perf_v2.md)

## Description

Remove (or convert to thin wrappers) the synchronous per-type kill methods in src/sase/ace/tui/actions/agents/_kill_type_handlers.py; verify all action paths route through _do_kill_agent / _do_bulk_kill_agents. Add a guard test asserting removed names are unreachable from AgentKillingMixin's MRO. See plans/202604/tui_perf_v2.md (Phase 6).

## Notes

COMMIT: e3e870ff

## Dependencies

- **Depends on:** [sase-12.1](sase-12.1.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`75c2508`](https://github.com/sase-org/sase/commit/75c2508f15e585d2eb85c49bcafc06b63cc80bc4) | ref: quarantine legacy synchronous kill handlers (sase-12.6) | [sase-12.6](sase-12.6.md) | 2026-04-28 23:14:43 |
