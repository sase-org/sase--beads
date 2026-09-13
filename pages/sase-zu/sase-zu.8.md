# Bead: sase-zu.8 — Finish indexed agent-history correctness, reuse and measured acceptance

[Bead Pages](../README.md) / [sase-zu](README.md) / sase-zu.8

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zu.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zu.land.md) · **Assignee:** `sase-zu.8.land`
**Created:** 2026-09-13 10:21:12 EDT
**Plan:** [202609/agent\_query\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_query_landing_repairs.md)

## Description

Repair the confirmed row-loss and freshness gaps, preserve later queue and Refresh panel changes, and prove the remaining sase-zu acceptance criteria.

## Notes

[2026-09-13T20:19:36Z · 55--code] DISCOVERED ISSUE: During swap_agents_retry_refresh implementation (2026-09-13), the full just-check lane failed tests/test_agent_loader_incomplete_history_dedup.py::test_incomplete_load_after_complete_history_keeps_non_workflow_suffix_guard: expected cached RUNNING cl_name 'active', got 'unknown'. Isolated rerun still fails. The keymap change does not touch the agent loader. Routed here because this epic owns indexed agent-history correctness. No new task.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zu.8.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zu.8.land/README.md) | [sase-zu.8](sase-zu.8.md) | 0 |
