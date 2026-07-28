# Bead: sase-w.1 — Phase 1 — Trace + Benchmark Foundation

[Bead Pages](../README.md) / [sase-w](README.md) / sase-w.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-w.1`
**Created:** 2026-04-27 16:16:23 UTC · **Closed:** 2026-04-27 16:38:03 UTC
**Plan:** [202604/tui\_perf\_overhaul\_1.md](https://github.com/sase-org/sase--plans/blob/main/202604/tui_perf_overhaul_1.md)

## Description

Add SASE_TUI_TRACE=1 scoped span recorder (tui_trace) emitting JSONL spans for hot-path functions in actions/changespec/_display.py, actions/agents/_display.py, actions/agents/_loading*.py, widgets/{changespec_list,agent_list,ancestors_children_panel,axe_dashboard}.py, and prompt/file/thinking panels. Build a synthetic-data benchmark harness (tests/perf/ or scripts/perf/) generating 100/500/2k ChangeSpecs, 50/200/1k agents, 1/5/20MB replies, driving headless TUI scenarios (cold start, query change, 50-key j/k burst, auto-refresh, large-reply select). Add docs/perf_runbook.md. Acceptance: tui_trace.jsonl populated, baseline numbers file produced, just check passes. Out of scope: any actual hot-path optimization.

## Notes

COMMIT: 5a9450dd

## Dependencies

- **Blocks:** [sase-w.2](sase-w.2.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`a23eca4`](https://github.com/sase-org/sase/commit/a23eca45ecc4f80387eb7d67d6c2784c0984021a) | feat(ace/tui/perf): Add SASE\_TUI\_TRACE span recorder + benchmark harness (sase-w.1) | [sase-w.1](sase-w.1.md) | 2026-04-27 16:37:46 |
