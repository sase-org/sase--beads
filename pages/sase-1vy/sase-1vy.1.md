# Bead: sase-1vy.1 — Fix the leak-detector thread poison on the CI Telemetry gate (sase-1vg)

[Bead Pages](../README.md) / [sase-1vy](README.md) / sase-1vy.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1vn.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vn.land.md) · **Assignee:** `sase-1vy.1` · **Size:** large
**Created:** 2026-11-28 03:14:44 EST
**Plan:** [202611/backlog\_epic\_2.md](https://github.com/sase-org/sase--plans/blob/main/202611/backlog_epic_2.md)

## Description

leak-gate: fix the root cause of sase-1vg. Read sase-1vg and all of its notes first. ACE pilot tests intermittently leave a sase-config-token-refresh thread alive past the leak-detector snapshot, poisoning global sase.config.core._live_config_token_refresh_threads on the CI Telemetry test-cost gate (run 46071761552: 63,676 passed in 2:03 inside the 180m cap, failing only this gate). Roughly 1 in 3 recent Telemetry runs. Fix it at its root; do not exempt the name from the detector. Verify with the cost lane and just check through sase tool run check, then close sase-1vg and the phase bead.

## Notes

[2026-11-28T08:22:48Z · sase-1vy.1] PLANNING EVIDENCE: On base 4010ecd89a, the reported deck-spread node passed with the blocking leak detector (1 passed, 0 poisoning), but tracing Thread.start identified sase-agent-detail-header_0 -> bead touches -> AgentIdentitySnapshot.current -> get_agent_owner_config_snapshot -> current_config_token as a real refresh-thread producer. A separate event-controlled probe reproduced the lifecycle gap deterministically: block a header resolver before its config read, call service.shutdown(), drain config, then release the resolver; service.is_running was false and the config worker slot empty after drain, yet the released resolver created a live sase-config-token-refresh thread. shutdown drops the executor and active job while wait=False permits the resolver to continue. All probe workers were joined afterward. Authoring a medium tale for retained worker completion and producer-before-config cleanup, including bare/shared pilot apps and timeout/deadlock regressions. No implementation edits or bead closure yet; this is the requested planning handoff, not an exhausted coding attempt.

[2026-11-28T08:51:02Z · sase-1vy.1] VERIFIED: Header enrichment retains the in-flight future across shutdown(wait=False); drain waits for the resolver, then _drain_config_producers_then_refresh joins sase-config-token-refresh. Isolation walks private _live_services via getattr so there is no public test-only drain helper. Cost lane this turn: 53 drain/leak tests passed, 0 poisoning; earlier 194-test cost lane also 0 poisoning. just _lint-symvision clean. sase bead epic-symbols sase-1vy.1: no entries. Close only this phase; leave sase-1vg and parent epic for the land agent.

[2026-11-28T09:24:02Z · sase-1vy.1--1] VERIFIED (recovery): just check failed with 169 NEW on worker gw9. Root cause was test_subprocess_count_does_not_scale_with_loaded_modules calling check_repository in-process; _prepare_import_env left _CommittedSourceFinder on sys.meta_path, so later tests imported first-party modules from the fake committed tree (ModuleNotFoundError: no committed first-party module named sase.ace.tui.actions.agents._types and siblings). check_repository now restores meta_path/path/modules after the check. Same-process canary (leak test then chop/core-health/commit/config/detach victims) passed; full test_check_rebase_imports.py, header-drain tests, and two former TUI victims passed. Nested admission test passed in isolation (gw13 failure looked load-related). Re-running just check for host completion. Close only this phase; leave sase-1vg and the parent epic for the land agent.

[2026-11-28T09:52:25Z · sase-1vy.1--2] VERIFIED (recovery 2): just check failed on NEW tests/tool/test_admission_processes.py::test_nested_agent_check_keeps_parent_and_never_queues (sase-1ve). Inner ToolRun appeared with parent_run_id and no admission record, then the test asserted started children without waiting; under load the stamp is late. Wait for _started_children before the count assert. Isolated node and whole admission module passed (8). Close only this phase; leave sase-1vg and the parent epic for the land agent. Closed sase-1ve because the missing wait is the documented flake.

## Dependencies

- **Blocks:** [sase-1vy.2](sase-1vy.2.md) ◐ · ⧖ 2026-11-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vy.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vy.1.md) | [sase-1vy.1](sase-1vy.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`42255c3`](https://github.com/sase-org/sase/commit/42255c3cce19e85ac18053d9b92921168c67c5c4) | fix(tui): drain header enrichment before config token refresh | [sase-1vy.1](sase-1vy.1.md) | 2026-11-28 05:14:42 EST |
