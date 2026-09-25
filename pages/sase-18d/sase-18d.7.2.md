# Bead: sase-18d.7.2 — Live row, process tree, and restart scenarios

[Bead Pages](../README.md) / [sase-18d.7](sase-18d.7.md) / sase-18d.7.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-18d.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-18d.land.md) · **Assignee:** `sase-18d.7.2` · **Size:** medium
**Created:** 2026-09-24 22:00:18 EDT · **Closed:** 2026-09-25 01:04:00 EDT
**Plan:** [202609/x\_kill\_e2e\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/x_kill_e2e_completion.md)

## Description

row_lifecycle: Complete the pilot scenarios for FAILED, DONE, immediate exit, and restart; repair any epic-caused defect exposed.

## Notes

[2026-09-25T04:56:32Z · sase-18d.7.2] PROPOSED FOLLOW-UP: fresh workspaces get PyPI sase-core-rs<=0.34.73 which rejects the agent_session capacity fields HEAD Python sends, so every TUI agents load fails until the binding is maturin-built from the linked sase-core checkout (sase-17m owns the pin/wheel-floor ratchet); this workspace has a locally built wheel

[2026-09-25T04:56:48Z · sase-18d.7.2] PROPOSED FOLLOW-UP: whole-repo just check blockers reported by sase-18d.7.1 reproduce on the clean base tree (mypy tools/sase_core_wheel_cache owned by sase-18q, test-waits tests/test_sase_core_wheel_cache_tool.py:490 owned by sase-18r, symvision stale sase-18i epic-symbol entries tracked by sase-o7 pattern); close policy says these never justify keeping this phase open

[2026-09-25T04:57:03Z · sase-18d.7.2] Kill-confirmation taxonomy: a done.json FAILED row is pid-less so x takes the immediate-dismiss path (no modal) with the durable safety net terminating the live twin; the kill-modal half is covered via the RETRYING backoff row (single FAILED+pid+live rows only arise from WORKFLOW merges) plus the core-wire FAILED+live planner unit tests

[2026-09-25T05:03:43Z · sase-18d.7.2--1] PROPOSED FOLLOW-UP: just check blocked by pre-existing mypy var-annotated error at tools/smoke_sase_core_rs_tool_runs:75 (fingerprint needs annotation); reproduces identically on clean base tree via git stash, unrelated to this phase diff

[2026-09-25T05:04:00Z · sase-18d.7.2--1] Phase scope done: FAILED/DONE/immediate-exit/restart pilot scenarios pass (25/25 in tests/test_kill_durable_termination.py + tests/ace/tui/test_agents_tab_x_row_lifecycle_e2e.py); mypy whole-repo clean on 4967 files; just check blocked only by pre-existing tools/smoke_sase_core_rs_tool_runs:75 var-annotated error reproducing on clean base tree (noted as follow-up); no epic-symbol leftovers

## Dependencies

- **Depends on:** [sase-18d.7.1](sase-18d.7.1.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18d.7.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-18d.7.2.md) | [sase-18d.7.2](sase-18d.7.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`02c4b02`](https://github.com/sase-org/sase/commit/02c4b029a67b743d45c564840c12adca8c4f3029) | test(ace): complete Agents-tab x row-lifecycle e2e coverage (sase-18d.7.2) | [sase-18d.7.2](sase-18d.7.2.md) | 2026-09-25 01:05:35 EDT |
