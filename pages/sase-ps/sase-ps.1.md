# Bead: sase-ps.1 — Occupancy rule and live admission gate

[Bead Pages](../README.md) / [sase-ps](README.md) / sase-ps.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.063](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.063.md) · **Assignee:** `sase-ps.1` · **Size:** medium
**Created:** 2026-08-18 10:20:05 EDT · **Closed:** 2026-08-18 11:01:42 EDT
**Plan:** [202608/monitor\_runner\_slots.md](https://github.com/sase-org/sase--plans/blob/main/202608/monitor_runner_slots.md)

## Description

count: separate slot occupancy from slot admission in the pure runner-slot core, make a serial agent family hold one slot while any of its shells (agent or monitor) is live, and wire the live admission gate to the new count.

## Notes

[2026-08-18T15:01:08Z · sase-ps.1] PROPOSED FOLLOW-UP: Justfile:342 has a stale --epic-symbol "sase-pq.3(gate_chip_from_action_data)" entry now that sase-pq.3 is closed, breaking `just check`/`just check-full` symvision lint for every agent host-wide (Error: bead sase-pq.3 is closed. Remove this stale --epic-symbol entry). With that one line removed, symvision also flags gate_chip_from_action_data in src/sase/notification_gates/presentation.py as newly unused (needs private-ing or deletion). Neither is caused by this phase (runner_slots admission/occupancy split); land agent should route to the sase-pq epic owner or file a task bead.

[2026-08-18T15:01:42Z · sase-ps.1] Implemented the occupancy/admission split in src/sase/core/runner_slots/_admission.py per plan: is_runner_slot_user_agent_record docstring now scoped to admission-only; added is_runner_slot_occupying_record (monitor-aware started check via pid vs run_started_at), runner_slot_family_key/group_records_by_runner_slot_family (project_name, agent_family-or-timestamp grouping), and running_agent_slot_count (1 slot per family with any occupying serial member, plus 1 per live parallel member), replacing running_root_agent_count with __init__.py re-exports updated. run_agent_wait_slots.py's _try_claim_runner_slot now sources running_count from running_agent_slot_count; wait_for_runner_slot's serial-exemption docstring extended to explain occupancy vs waiting. Extended tests/test_runner_slots.py, tests/test_run_agent_runner_slot_capacity.py, tests/_runner_slot_fixtures.py, tests/test_run_agent_runner_slots.py, and tests/fakey/test_runner_slots_e2e.py per the plan's test list (monitor holding last slot, monitor follow-up claims without parking, releasing monitor releases parked waiter, e2e cap=1 monitor lifecycle); fixed 4 cross-file callers of the renamed function (test_axe_run_agent_runner_started_at, test_agent_loader_dedup_pid_families, test_axe_chop_preflight_policy, test_running_agents_snapshot) plus test_run_agent_runner_slots.py's own renamed-function usage. Verified: fmt-py, fmt-md, keep-sorted, ruff, mypy (0 issues/3449 files), feature-flags, pyscripts, test-waits, changelog, patch/stitch-terminology, toobig, sase validate, validate-committed-plans, and symvision (0 new issues from this diff — confirmed by running it manually past a pre-existing unrelated stale --epic-symbol entry from closed bead sase-pq.3, noted as PROPOSED FOLLOW-UP) all pass; just test-scoped: 33242 passed, 12 skipped, 0 failed. sase-ps.1 has no --epic-symbol entries of its own.

## Dependencies

- **Blocks:** [sase-ps.2](sase-ps.2.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-ps.3](sase-ps.3.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-ps.4](sase-ps.4.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ps.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ps.1/README.md) | [sase-ps.1](sase-ps.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`63accbf`](https://github.com/sase-org/sase/commit/63accbfc9979f46e1ee39204f3786a269de8c624) | fix(runner-slots): count monitors and post-handoff shells against max\_running\_agents | [sase-ps.1](sase-ps.1.md) | 2026-08-18 11:02:26 EDT |
