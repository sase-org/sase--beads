# Bead: sase-1bt.4 — ToolRun glance snapshot service and live-only ⚒ row chips

[Bead Pages](../README.md) / [sase-1bt](README.md) / sase-1bt.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tc.md) · **Assignee:** `sase-1bt.4` · **Size:** medium
**Created:** 2026-09-27 18:32:39 EDT · **Closed:** 2026-09-27 23:48:14 EDT
**Plan:** [202609/tool\_runs\_tui\_surfaces.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_runs_tui_surfaces.md)

## Description

glance-row-chips: build the TUI ToolRun snapshot service (surface token, live drift probe, coalesced worker load, attribution), then render the live and silent ⚒ row chips with session inheritance, minute ticking, render-cache keys, and row patching behind ace_tool_runs.

## Notes

[2026-09-28T03:47:34Z · sase-1bt.4] PROPOSED FOLLOW-UP: tests/ace/tui/test_agent_completion.py::test_agent_session_completion_candidate_attaches_cached_plan_preview fails identically on the clean base tree (verified via stash); pre-existing, not caused by glance-row-chips -r pre-existing failure triage

[2026-09-28T03:48:14Z · sase-1bt.4] glance-row-chips done: snapshot service (tool_runs/snapshot.py + loader.py with surface token, 2s drift probe on countdown tick, coalesced worker, patch-only-changed with rebuild escalation), pure attribution (attribution.py) and minute-quantized row chips (row_chip.py) rendered after the finalizer chip behind ace_tool_runs with cache keys and runtime ticks; verified with new tests/ace/tui/test_tool_runs_glance.py (14 tests), related suites (74 passed), ruff/mypy/symvision clean; pre-existing test_agent_completion failure reproduces on base and is recorded as PROPOSED FOLLOW-UP

## Dependencies

- **Depends on:** [sase-1bt.3](sase-1bt.3.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bt.5](sase-1bt.5.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bt.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bt.4/README.md) | [sase-1bt.4](sase-1bt.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4f09a28`](https://github.com/sase-org/sase/commit/4f09a28ea1bc6d6a7cd4828ab79a46a8719aea4e) | feat(ace-tui): implement glance row chips for tool runs | [sase-1bt.4](sase-1bt.4.md) | 2026-09-27 23:51:29 EDT |
