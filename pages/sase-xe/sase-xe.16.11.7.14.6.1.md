# Bead: sase-xe.16.11.7.14.6.1 — Make owner-generated fleet labels valid and repair contract fixtures

[Bead Pages](../README.md) / [sase-xe.16.11.7.14.6](sase-xe.16.11.7.14.6.md) / sase-xe.16.11.7.14.6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-xe.16.11.7.14.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.16.11.7.14.land.md) · **Assignee:** `sase-xe.16.11.7.14.6.1` · **Size:** medium
**Created:** 2026-09-10 19:58:00 EDT · **Closed:** 2026-09-10 21:12:32 EDT
**Plan:** [202609/fleet\_remaining\_acceptance.md](https://github.com/sase-org/sase--plans/blob/main/202609/fleet_remaining_acceptance.md)

## Description

payload-safety: normalize owner-produced display intent and repair correlated wire fixtures with projection and gateway regressions.

## Notes

[2026-09-11T01:10:14Z · sase-xe.16.11.7.14.6.1--3] PROPOSED FOLLOW-UP: ci — tests/ace/tui/test_agent_display_diff.py::test_by_machine_badge_only_change_patches_after_finalize fails deterministically on an otherwise clean master (assert "row_patch" in _display_costs(app) sees []); test last touched by 4a862d6ea (by-machine status subgroup banners), nothing in this phase touches ACE display diff.

[2026-09-11T01:10:50Z · sase-xe.16.11.7.14.6.1--3] PROPOSED FOLLOW-UP: ci — tests/test_agent_artifact_marker_mutation_audit.py::test_reviewed_marker_mutation_sites_match_expected_mutations fails on clean master because src/sase/agent/_restart_recovery.py:_write_recovery_files gained a third write_text in 63a5dbef1 (plan 202609/grok_drain_relaunch_repair.md) without updating the reviewed mutation table.

[2026-09-11T01:11:02Z · sase-xe.16.11.7.14.6.1--3] PROPOSED FOLLOW-UP: ci — tests/fakey/test_runner_slots_e2e.py::test_installed_research_swarm_quarter_weights_fill_one_fakey_capacity_unit fails on clean master: the installed sase_research_artifacts research_swarm xprompt still emits %wait(priority=...), which core plan_typed_launch_units now rejects ("has moved to %queue"), so plugin and core are version-skewed.

[2026-09-11T01:11:47Z · sase-xe.16.11.7.14.6.1--3] PROPOSED FOLLOW-UP: ci — two whole-repo lint gates were already red on clean master and are FIXED in this phase diff (out of scope but they blocked just check from reaching any test): tests/fakey/test_provider_drain_e2e.py:65,86 lacked "# sase-test-wait:" pragmas since 63a5dbef1, and symvision flagged agent_live_query_entry/agent_live_query_row_id (landed test-only by closed phase sase-zf.1 at bfcdc0416), now whitelisted as --epic-symbol sase-zf.3(...) in the Justfile for the consumer phase to drop.

[2026-09-11T01:12:32Z · sase-xe.16.11.7.14.6.1--3] Payload-safety landed and verified. (1) core crates/sase_core/src/fleet_contract.rs: intent_for_record now maps control characters to spaces through a shared replace_control_characters helper (also reused by sanitize_diagnostic_message) BEFORE UTF-8-safe byte bounding, covering both agent_meta.plan_action and raw_prompt_snippet, and omits an intent that normalizes to empty instead of emitting an invalid empty label; 5 Rust regressions (newline/CR/tab, plan_action, Unicode byte limit, empty-after-normalization, strict external-wire rejection). (2) core crates/sase_gateway/src/fleet_reads.rs: build_snapshot_blocking no longer aborts a whole snapshot when one record fails to project — it skips and counts that row and reports freshness.partial=true with the safe reason "unresolved rows: N (code)" (the actual cause of the Apollo hello/summary HTTP 400); 2 gateway regressions. (3) sase tests/test_fleet_contract_sase_core_rs.py: 5 mirrored Python binding regressions; tests/test_fleet_contract_counts_sase_core_rs.py: correlated family_role=monitor added to the row_kind=monitor fixture override (repo sweep confirmed it was the only inconsistent override). VERIFICATION: core ./scripts/check.sh all PASSED (fmt+clippy+cargo test --workspace incl PyO3, with the known sase-xv loader-path workaround applied); just install rebuilt sase_core_rs from the patched core; just check — every lint gate green and the scoped lane ran 40529 tests, 40526 passed. TEN-NODE DISPOSITION: all green — the 25 nodes of tests/ace/tui/test_fleet_agents.py + tests/ace/tui/test_agents_fleet_refresh_laziness.py (which include the ten the grandparent epic note 1 flagged) pass against the freshly built binding; 37 passed together with this phase fleet-contract tests. NOT MINE: 3 scoped-lane failures reproduce deterministically on clean master and are recorded as PROPOSED FOLLOW-UP notes (test_by_machine_badge_only_change_patches_after_finalize; test_reviewed_marker_mutation_sites_match_expected_mutations from _restart_recovery.py at 63a5dbef1; test_installed_research_swarm_quarter_weights... from the sase_research_artifacts plugin still emitting %wait(priority=)). Two whole-repo lint gates were also red on clean master and blocked just check from reaching any test, so they are fixed in this diff and noted: sase-test-wait pragmas in tests/fakey/test_provider_drain_e2e.py:65,86, and --epic-symbol sase-zf.3(agent_live_query_entry|agent_live_query_row_id) in the Justfile for sase-zf.1 test-only adapter. epic-symbols clean for this phase.

## Dependencies

- **Blocks:** [sase-xe.16.11.7.14.6.2](sase-xe.16.11.7.14.6.2.md) ✓ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.11.7.14.6.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.16.11.7.14.6.1.md) | [sase-xe.16.11.7.14.6.1](sase-xe.16.11.7.14.6.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1546398`](https://github.com/sase-org/sase/commit/1546398faaea22036fa060f979a261737a46e6cc) | test(fleet): mirror intent normalization regressions and unblock check | [sase-xe.16.11.7.14.6.1](sase-xe.16.11.7.14.6.1.md) | 2026-09-10 21:13:56 EDT |
| sase-core | [`sase-core@381b643`](https://github.com/sase-org/sase-core/commit/381b643b6b2174b50bde8b3bcc978140daa3175c) | fix(fleet): keep owner-produced display intent presentable | [sase-xe.16.11.7.14.6.1](sase-xe.16.11.7.14.6.1.md) | 2026-09-10 21:17:15 EDT |
