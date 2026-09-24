# Bead: sase-18e.2 — Make in-agent sase monitor start fast and never silent

[Bead Pages](../README.md) / [sase-18e](README.md) / sase-18e.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0re](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0re.md) · **Assignee:** `sase-18e.2` · **Size:** medium
**Created:** 2026-09-24 16:48:55 EDT · **Closed:** 2026-09-24 18:09:55 EDT
**Plan:** [202609/codex\_monitor\_handoff\_cutoff.md](https://github.com/sase-org/sase--plans/blob/main/202609/codex_monitor_handoff_cutoff.md)

## Description

fast-monitor-start: resolve a pinned caller without a full project scan, do one lane-scoped monitor read per start (adding an index filter in sase-core if needed), add start timing, and print a stderr line before any slow work.

## Notes

[2026-09-24T22:09:13Z · sase-18e.2] PROPOSED FOLLOW-UP: move sase-core-revision.txt past the sase-core commit that adds AgentArtifactCandidateFieldWire::AgentSession (this phase changed sase-core but the commit did not exist yet to pin, so the pin is unmoved) -- then drop _skip_unless_core_has_agent_session_filter from tests/monitor/test_monitor_store_lane_index.py; until then store.lane_monitor_records degrades to the old full scan on the pinned core, correct but slow

[2026-09-24T22:09:25Z · sase-18e.2] PROPOSED FOLLOW-UP: explicit -a/--agent monitor starts still call store_lane.resolve_lane, which runs a full project_records scan (lane match spans agent_session, workflow_name, name and agent_session_base(name), so the new agent_session candidate filter alone cannot serve it) -- only the implicit in-agent start was made fast

[2026-09-24T22:09:36Z · sase-18e.2] PROPOSED FOLLOW-UP: just check is red on the clean base tree independent of this phase: 15 mypy errors (ace/tui/widgets/_agent_detail_*.py, ace/tui/command_line/{input,screen}.py), symvision (_dispatch_preview_source_summary in _prompt_input_bar_dispatch.py), toobig (command_line/screen.py 1718 lines, widgets/decks/panel.py 1067), test-waits (tests/ace/tui/command_line/test_completion_popup.py:181), and 41 test-scoped failures (ACE TUI panels, keymaps, config schema, timezone, marker-mutation audit, axe wait_checks) -- all reproduce with this phase stashed

[2026-09-24T22:09:55Z · sase-18e.2] Implicit in-agent monitor start no longer scans project history. resolve_caller_agent reads the pinned SASE_ARTIFACTS_DIR directly (store.artifact_dir_record, ~4 ms) and only falls back to project_records on a missing/foreign pin. One lane-scoped monitor read per start (store.lane_monitor_records + store_lane.LaneMonitorReads) via a new AgentSession candidate-filter field in sase-core's artifact index (matches the indexed agent_family column; lane read skips full-history source reconcile); exact agent_session re-checked in Python. Per-phase StartTimer -> debug log + monitor_start_timing.json in the member artifacts. CLI prints a stderr line before any slow work when handing off from an agent. Measured on this host (12,015 records): read path before ~33s (project_records 12.2s x2 callers + monitor_records 4.3s + 4.1s); after 0.11s total (pinned resolve 0.01s, lane read 0.10s, shared has_any 0ms); lane reads matched the old full monitor scan for the 6 busiest lanes. Verified: sase-core just check passed (new agent_session_filter tests); sase monitor/main/shells/tool/gate_shell tests pass (3056) incl. new tests/monitor/test_monitor_start_fast_path.py, test_monitor_store_lane_index.py and CLI stderr tests; ruff, fmt, mypy-on-my-files, symvision-on-my-symbols clean. just check itself is red only on failures that reproduce on the clean base tree (15 mypy errors, symvision, toobig, test-waits, 41 scoped test failures, all in unrelated ACE TUI/keymap/config areas). sase-core-revision.txt not moved: the sase-core commit does not exist yet (PROPOSED FOLLOW-UP recorded).

## Dependencies

- **Blocks:** [sase-18e.3](sase-18e.3.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18e.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18e.2/README.md) | [sase-18e.2](sase-18e.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c9da1f1`](https://github.com/sase-org/sase/commit/c9da1f164786b5a94700124bbfb33d806f133b67) | feat(monitor): make in-agent sase monitor start fast and never silent (sase-18e.2) | [sase-18e.2](sase-18e.2.md) | 2026-09-24 18:11:04 EDT |
