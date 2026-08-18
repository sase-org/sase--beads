# Bead: sase-ps.3 — Rust core parity for historical runner occupancy

[Bead Pages](../README.md) / [sase-ps](README.md) / sase-ps.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.063](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.063.md) · **Assignee:** `sase-ps.3` · **Size:** medium
**Created:** 2026-08-18 10:20:06 EDT · **Closed:** 2026-08-18 11:57:23 EDT
**Plan:** [202608/monitor\_runner\_slots.md](https://github.com/sase-org/sase--plans/blob/main/202608/monitor_runner_slots.md)

## Description

stats: update the duplicated runner-eligibility predicate in the sase-core Rust crate so the Statistics runner-occupancy analysis uses the same rule as live admission, then release the binding and repin it here.

## Notes

[2026-08-18T15:56:21Z · sase-ps.3] Implemented the Rust occupancy/admission split in sase-core: is_runner_eligible_record stays the admission/lineage predicate (now documented as the counterpart of Python is_runner_slot_user_agent_record); added is_runner_occupancy_record, runner_slot_family_key, is_runner_slot_occupying_record, running_agent_slot_count (Python snapshot table, case for case), occupancy_member_start (monitor uses the earlier of run_started_at and the artifact timestamp), and merge_family_occupancy_intervals (union serial family intervals; fill starter-to-monitor gaps; parallel members stay independent slots). RunnerStatsBuilder buffers per-record contributions and merges at finish so overlapping in-process handoffs do not double-count. query_run_stats user-hidden diagnostics now use the occupancy predicate; runner_overlap_candidate falls back to the artifact stamp so a monitor with pid but no run_started_at still reaches decode. Updated runner_eligibility and user_hidden tests; added family merge + monitor-gap unit/integration tests. Did not bump crate versions (release-plz owns them). just install rebuilt sase_core_rs 0.28.0 from the local checkout; pyproject.toml pin left at >=0.27.18,<0.28.0 because the release-branch reconciler ratchets the published window. Added tests/stats/test_runner_occupancy_parity.py: synthetic indexes produce the same peak/runner_seconds through query_run_stats as running_agent_slot_count as-of each second. Historical Statistics runner-occupancy numbers for windows before this change now read higher — the analyzer recomputes from stored artifacts; the old series under-counted serial children, monitors, and post-handoff follow-ups. sase-core just check (fmt, clippy, workspace tests) passed; sase just check passed after scoped escalation to the full suite (core-identity-changed from the rebuilt extension). sase-ps.3 has no --epic-symbol entries. sase-core changes are still uncommitted in the linked checkout.

[2026-08-18T15:56:56Z · sase-ps.3] PROPOSED FOLLOW-UP: land the uncommitted sase-core occupancy split on sase-core master (agent_runtime.rs + agent_stats runner/run + Unreleased changelogs) so release-plz can publish sase_core_rs and the sase pin can ratchet — this phase rebuilt the local binding only.

[2026-08-18T15:57:23Z · sase-ps.3] Rust occupancy/admission split matches Python: snapshot table, family interval merge, monitor handoff gap fill. just install rebuilt sase_core_rs from local sase-core; 6 parity tests pass (query_run_stats == running_agent_slot_count). sase-core just check and sase just check (escalated full suite) passed. No --epic-symbol leftovers. Historical runner-occupancy numbers now read higher because they were under-counting.

[2026-08-18T15:59:13Z · sase-ps.3] Rust occupancy/admission split matches Python: snapshot table, family interval merge, monitor handoff gap fill. just install rebuilt sase_core_rs from local sase-core; 6 parity tests pass (query_run_stats == running_agent_slot_count). sase-core just check and sase just check (escalated full suite) passed. No --epic-symbol leftovers. Historical runner-occupancy numbers now read higher because they were under-counting.

## Dependencies

- **Depends on:** [sase-ps.1](sase-ps.1.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-ps.4](sase-ps.4.md) ✓ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ps.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ps.3/README.md) | [sase-ps.3](sase-ps.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@769b9bc`](https://github.com/sase-org/sase-core/commit/769b9bc8fb2195e8deb91a67044f98e937e7448c) | fix(agent\_stats): count family shells in historical runner occupancy | [sase-ps.3](sase-ps.3.md) | 2026-08-18 12:00:26 EDT |
| sase | [`746c807`](https://github.com/sase-org/sase/commit/746c807051fc11b107bec62c475cd738d8716296) | test(stats): assert Rust historical occupancy matches Python slot count | [sase-ps.3](sase-ps.3.md) | 2026-08-18 12:03:38 EDT |
