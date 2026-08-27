# Bead: sase-ud.13.1.3.1.1 — Pin the post-gate-shell family projection contract

[Bead Pages](../README.md) / [sase-ud.13.1.3.1](sase-ud.13.1.3.1.md) / sase-ud.13.1.3.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ud.13.1.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ud.13.1.3.md) · **Assignee:** `sase-ud.13.1.3.1.1` · **Size:** small
**Created:** 2026-08-27 11:52:52 EDT · **Closed:** 2026-08-27 12:26:45 EDT
**Plan:** [202608/status\_strip.md](https://github.com/sase-org/sase--plans/blob/main/202608/status_strip.md)

## Description

gate-contract: add guard tests that a family whose newest member is a plan or question gate shell renders the gate's status on the container row and `DONE` on the planner, for pending and settled branches alike, driven from real gate-shell member metadata rather than the override map.

## Notes

[2026-08-27T16:26:18Z · sase-ud.13.1.3.1.1--2] PROPOSED FOLLOW-UP: just check on master (commit a646bdaf6, unrelated to this phase) has 13 pre-existing failures reproducing in isolation, not just under parallel contention — tests/test_agent_wait_cli.py::test_all_excludes_caller_and_its_family, tests/test_agent_wait_cli.py::test_exit_code_timeout, tests/test_agent_wait_live.py::test_why_column_for_waiting_queued_monitor_and_prompt, tests/test_agent_wait_live.py::test_terminal_blocker_warning_when_dependency_failed, tests/test_running_agents_snapshot.py (5 tests: filters_done_and_dead, surfaces_slot_relevant_parallel_children, running_listing_slot_occupancy_matches_admission_count, reports_waiting_marker, list_all_agents_includes_done_and_failed), tests/axe/test_agent_meta_atomic.py::test_generic_and_specialized_agent_meta_writers_use_atomic_publication, tests/test_agent_chat_from_name.py::test_explicit_running_agent_falls_back_to_meta_chat_path. Two more (tests/fakey/test_runner_slots_e2e.py::test_fakey_priority_admission_differs_from_park_order and ::test_child_is_exempt_while_repeat_roots_stay_capped) pass in isolation but fail under just check parallel contention, suggesting host-contention flakiness. None of these overlap sase-j0 (check-full budget overruns) — no existing bead tracks them. Worth filing as a CI-failure task bead for triage.

[2026-08-27T16:26:45Z · sase-ud.13.1.3.1.1--2] Added tests/test_agent_loader_status_override_gate_shell_family.py: 9 guard tests building plan/question families from real gate-shell member metadata (root + concrete planner main-step + gate member via enrich_agent_from_meta_wire/FamilyShellWire/FamilyShellGateWire) and asserting _apply_status_overrides projection — pending/settled tale+epic+question gates mirror onto container and gate row, planner member stays DONE, mirrored gate_start_status/gate_stop_status/gate_state/gate_accent pair on the container equals the gates row, and settled gate + running/completed coder child yields WORKING TALE / TALE DONE (R-1 guard). All 9 tests pass in isolation (2.34s). just check's only failures are 13 pre-existing, unrelated tests (agent-wait CLI/live, running-agent snapshots, agent-meta atomic publication, agent-chat resume, fakey runner slots) that reproduce independent of this change — confirmed by isolated re-run — and are untracked by sase-j0; filed as a PROPOSED FOLLOW-UP note for the epic land agent to triage. No --epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-ud.13.1.3.1.2](sase-ud.13.1.3.1.2.md) ◐ · ⧖ 2026-08-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ud.13.1.3.1.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ud.13.1.3.1.1.md) | [sase-ud.13.1.3.1.1](sase-ud.13.1.3.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2f8bc9a`](https://github.com/sase-org/sase/commit/2f8bc9abb4e90d23f5e1dd1c171da61d5639b1b8) | test(status-strip): pin gate-shell family projection contract for \_apply\_status\_overrides | [sase-ud.13.1.3.1.1](sase-ud.13.1.3.1.1.md) | 2026-08-27 12:27:38 EDT |
