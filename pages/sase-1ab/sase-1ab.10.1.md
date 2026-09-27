# Bead: sase-1ab.10.1 — Legacy reader and sunset-flag repair

[Bead Pages](../README.md) / [sase-1ab.10](sase-1ab.10.md) / sase-1ab.10.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ab.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.land.md) · **Assignee:** `sase-1ab.10.1` · **Size:** medium
**Created:** 2026-09-27 08:44:26 EDT · **Closed:** 2026-09-27 09:40:54 EDT
**Plan:** [202609/sase\_turn\_rename\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_turn_rename_finish.md)

## Description

reader-repair: fix the durable readers the runtime cutover corrupted (the agent_session_turn stripper, the continuation_mode and proc origin no-ops), route authored gate specs and the gate.shell config key through the flag-gated normalizers, fix the undefined LEGACY_NAMED_PROC_SECTION_ID, and audit every rename commit for more corruption, with a legacy-input test for each fix.

## Notes

[2026-09-27T13:07:32Z · sase-1ab.10.1] PROPOSED FOLLOW-UP: tests/agent/test_legacy_agent_family_syntax.py::test_gate_help_lists_only_canonical_next_fork_value still expects --next-fork {session,shell,none}; help now correctly shows {session,turn,none} — rename-stale, owned by test-repair phase (sase-1ab.10.2)

[2026-09-27T13:40:25Z · sase-1ab.10.1--1] PROPOSED FOLLOW-UP: 5 just-check failures reproduce identically on clean base (verified via git stash) and are rename-stale owned by test-repair: tests/main/test_parser_proc.py::test_proc_run_help_documents_command_and_examples, tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed, tests/test_agent_artifact_marker_mutation_audit.py::test_reviewed_marker_mutation_sites_declare_lifecycle_coverage, tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot, tests/test_check_sase_core_rs_bindings_tool.py::test_dev_extension_exposes_every_collected_name

[2026-09-27T13:40:36Z · sase-1ab.10.1--1] PROPOSED FOLLOW-UP: tests/test_timezone_display_guard.py::test_no_system_clock_display_sites reproduces identically on clean base (verified via git stash); flags _agent_finalizer_receipt.py:45, already routed as KNOWN foreign to finalizer epic sase-1b2 per parent plan

[2026-09-27T13:40:54Z · sase-1ab.10.1--1] Verified all 7 reader-repair fixes in tree (plan_chain stripper, model_request continuation no-op, proc-shell origin mapping, authored gate-spec flag gating, gate.shell reclaim reporting, LEGACY_NAMED_PROC_SECTION_ID import, wire bogus import); 60 phase regression tests + 78-test targeted sweep pass, mypy clean on hint_sections; epic-symbols empty; 6 remaining just-check failures reproduce identically on clean base (git-stash verified) and are recorded as PROPOSED FOLLOW-UPs for test-repair/foreign owners

## Dependencies

- **Blocks:** [sase-1ab.10.3](sase-1ab.10.3.md) ◐ · ⧖ 2026-09-27
- **Blocks:** [sase-1ab.10.5](sase-1ab.10.5.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ab.10.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.10.1.md) | [sase-1ab.10.1](sase-1ab.10.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c13cb5d`](https://github.com/sase-org/sase/commit/c13cb5d11314b76832dd0d16f95e1bcaab6846be) | fix(sase-1ab.10.1): complete reader-repair design fixes across gates, procs and wire | [sase-1ab.10.1](sase-1ab.10.1.md) | 2026-09-27 09:44:41 EDT |
