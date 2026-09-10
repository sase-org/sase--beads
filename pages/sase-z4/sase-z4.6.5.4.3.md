# Bead: sase-z4.6.5.4.3 — Compare runtime, CLI, and TUI capacity from one captured snapshot

[Bead Pages](../README.md) / [sase-z4.6.5.4](sase-z4.6.5.4.md) / sase-z4.6.5.4.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-z4.6.5.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-z4.6.5.land.md) · **Assignee:** `sase-z4.6.5.4.3` · **Size:** medium
**Created:** 2026-09-10 17:42:16 EDT · **Closed:** 2026-09-10 18:34:49 EDT
**Plan:** [202609/weighted\_capacity\_remaining\_acceptance.md](https://github.com/sase-org/sase--plans/blob/main/202609/weighted_capacity_remaining_acceptance.md)

## Description

snapshot-parity: from one captured source snapshot, compare runtime admission, sase agent list -j, the ACE capacity header, queue ranks/blockers/details, local and remote badges, unknown usage, and filtering/folding.

## Notes

[2026-09-10T22:33:12Z · sase-z4.6.5.4.3] PROPOSED FOLLOW-UP: lint (symvision) is red on clean master (840824c5b) -- 3 unused public symbols from the "feat(sdd): reconcile artifact link event unions" commit: ArtifactLinkBeadProjectionResult in src/sase/sdd/_artifact_link_event_project.py, and row_uses in both src/sase/sdd/_artifact_link_event_canonical.py and src/sase/sdd/_artifact_link_outbox_types.py. Needs privatizing or deleting by whoever owns that sdd work; unrelated to snapshot-parity.

[2026-09-10T22:33:40Z · sase-z4.6.5.4.3] PROPOSED FOLLOW-UP: lint (test waits) is red on clean master -- tests/fakey/test_provider_drain_e2e.py:65 and :86 have fixed sleeps missing the required '# sase-test-wait: <reason>' pragma. Needs either the pragma with a real reason or converting to an observable wait; unrelated to snapshot-parity.

[2026-09-10T22:34:14Z · sase-z4.6.5.4.3] PROPOSED FOLLOW-UP: 21 tests fail on clean master (840824c5b), confirmed independent of this phase (failures reproduce identically with tests/test_capacity_snapshot_parity.py removed). tests/sdd_store/test_sidecar_init_creation.py (2) and test_sidecar_bead_adoption.py (2) fail on a missing '/link-events/**/.staging/' .gitignore line, likely from the 'feat(sdd): reconcile artifact link event unions' commit. tests/ace/tui/test_fleet_agents.py (7) and test_agents_fleet_refresh_laziness.py (3) fail. tests/completion/test_snapshot.py (2) show checked-in-snapshot drift. Also failing: test_fleet_contract_counts_sase_core_rs.py::test_count_contract_deduplicates_current_instances_and_buckets, test_agent_display_diff.py::test_by_machine_badge_only_change_patches_after_finalize, test_agent_artifact_marker_mutation_audit.py::test_reviewed_marker_mutation_sites_match_expected_mutations, sdd_store/test_artifact_link_ignore.py::test_lock_ignore_appends_without_disturbing_existing_content, and fakey/test_runner_slots_e2e.py::test_installed_research_swarm_quarter_weights_fill_one_fakey_capacity_unit. Needs triage into task beads by the epic land agent; none of these are snapshot-parity regressions.

[2026-09-10T22:34:49Z · sase-z4.6.5.4.3] Added tests/test_capacity_snapshot_parity.py: 7 tests build one shared weighted-capacity source snapshot (three 0.25-weight running claims, an explicit weight-2.0 parked waiter blocked by weight/runner-count conditions, a parked waiter with unrecognized/invalid weight, and a live claim with unrecognized weight) and prove that runtime admission (runner_capacity_snapshot), sase agent list -j (agent_list_entries/_agent_to_json), and the ACE TUI (refresh_runner_slot_context, AgentInfoPanel capacity header text, queue detail text, badges) all agree on occupied capacity, effective limit, queue order/position, blockers, and eligibility when built from that one snapshot. Also proves: a remote agent's non-default weight badge never charges the local capacity snapshot; per-project CLI filtering and TUI fold-collapsing never recompute the shared global queue numbers (position/size stay identical pre- and post-filter); and a single live claim with unrecognized weight fails the whole snapshot closed (blocks even a previously-eligible waiter) identically across all three surfaces. Verified: pytest on the new file (7 passed); just fmt/ruff/mypy/keep-sorted all pass on it; ran the full just test-scoped lane (40391 passed, 21 failed) and confirmed by rerunning without the new file that all 21 failures, plus the red lint (feature flags)/lint (symvision)/lint (test waits) gates, pre-date and are independent of this change -- recorded as PROPOSED FOLLOW-UP notes on this bead for the epic land agent to triage. sase bead epic-symbols sase-z4.6.5.4.3 reports no --epic-symbol entries for this phase.

## Dependencies

- **Depends on:** [sase-z4.6.5.4.1](sase-z4.6.5.4.1.md) ✓ · ⧖ 2026-09-10
- **Blocks:** [sase-z4.6.5.4.4](sase-z4.6.5.4.4.md) ◐ · ⧖ 2026-09-10
- **Blocks:** [sase-z4.6.5.4.5](sase-z4.6.5.4.5.md) ◐ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-z4.6.5.4.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-z4.6.5.4.3/README.md) | [sase-z4.6.5.4.3](sase-z4.6.5.4.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`74a4e42`](https://github.com/sase-org/sase/commit/74a4e4282f7dbf29a4e258de2dad8687da01d6ae) | test(capacity-snapshot): add cross-view weighted-capacity parity tests | [sase-z4.6.5.4.3](sase-z4.6.5.4.3.md) | 2026-09-10 18:36:17 EDT |
