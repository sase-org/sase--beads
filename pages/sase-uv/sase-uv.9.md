# Bead: sase-uv.9 — Index retention tooling and self-inflicted stall fixes

[Bead Pages](../README.md) / [sase-uv](README.md) / sase-uv.9

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ex](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ex.md) · **Assignee:** `sase-uv.9` · **Size:** medium
**Created:** 2026-08-27 12:26:48 EDT
**Plan:** [202608/ace\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_tui_responsiveness.md)

## Description

hygiene: add retention/vacuum tooling for the unbounded index and registry state, open the index read-only on query paths, and stop the stall watchdog from extending the freeze it measures.

## Notes

[2026-08-27T17:53:16Z · sase-uv.9] PROPOSED FOLLOW-UP: just check test-scoped consistently fails ~13 tests unrelated to this phase diff (tests/test_agent_wait_cli.py, tests/test_agent_wait_live.py, tests/test_running_agents_snapshot.py, tests/test_agent_chat_from_name.py, tests/axe/test_agent_meta_atomic.py, tests/fakey/test_runner_slots_e2e.py) across two independent just check runs on this branch. Reproduced test_running_agents_snapshot.py::test_list_running_agents_reports_waiting_marker failing identically on a clean git-stashed master tree, confirming it predates this phase and is not caused by these changes. Failures cluster around process-liveness/_fixture_processes fixtures and runner-slot e2e timing, and this host runs many concurrent SASE agent workspaces (e.g. sase_20 was running its own pytest concurrently) — suspect host-load/process-table contention rather than a code defect, but worth a dedicated flake/CI investigation.

[2026-08-27T17:53:43Z · sase-uv.9] PROPOSED FOLLOW-UP: hygiene retention scope note — this phase shipped VACUUM/compact tooling (sase agent index vacuum) plus freelist/dismissed-row visibility reporting, but deliberately did not implement automatic pruning for the two unbounded JSON registries the plan cites (agent_name_registry.json ~17MB/13,118 entries; dismissed_agents.json ~2.4MB). The SQLite dismissed_agents table is a full mirror rebuilt from dismissed_agents.json on every sync (see sync_dismissed_agent_artifact_index_report), so a real retention policy has to bound the JSON source, not just the SQLite mirror, and needs a product decision on TTL/count caps plus care not to un-hide previously dismissed agents. That design work is bigger than a cheap hygiene phase; needs a dedicated task.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-uv.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-uv.9/README.md) | [sase-uv.9](sase-uv.9.md) | 0 |
