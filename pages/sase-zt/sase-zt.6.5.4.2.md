# Bead: sase-zt.6.5.4.2 — Restore queue-capacity parity in synthesized remote agent rows

[Bead Pages](../README.md) / [sase-zt.6.5.4](sase-zt.6.5.4.md) / sase-zt.6.5.4.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zt.6.5.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zt.6.5.land.md) · **Assignee:** `sase-zt.6.5.4.2` · **Size:** medium
**Created:** 2026-09-13 22:09:27 EDT · **Closed:** 2026-09-13 23:43:46 EDT
**Plan:** [202609/queue\_capacity\_remote\_fleet\_parity.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_capacity_remote_fleet_parity.md)

## Description

remote-consumer: ratchet the supported core cohort, consume the new fleet fields through the existing Agent adapter, and prove remote row/detail capacity presentation without changing admission accounting.

## Notes

[2026-09-14T03:39:29Z · sase-zt.6.5.4.2] PROPOSED FOLLOW-UP: sase.pager fails to import with a circular-import ImportError (cannot import PagerDocument from sase.pager, via pager/_labels.py -> ace/tui/actions/navigation -> ace/tui/actions/agents/_core.py -> _metadata_pager.py -> sase.pager). Introduced by main commit a59ded7669 (feat(ace,pager): open agent metadata in the pager with V). Reproduces on a clean checkout of that commit with no other changes; breaks just check's "lint (feature flags)" gate and every test importing sase.pager (confirmed: tests/pager/test_refresh_provider.py; likely tests/gate_conformance/test_gate_conformance.py::test_gate_conformance[mobile-partial_attempt] and others transitively).

[2026-09-14T03:39:58Z · sase-zt.6.5.4.2] PROPOSED FOLLOW-UP: tests/test_gate_decision_acceptance.py has three fixed sleeps (lines 91, 101, 111) missing the required "# sase-test-wait: <reason>" pragma, failing just check's "lint (test waits)" gate. The same file also has two deterministically-failing tests in the diff-scoped lane: test_conflicting_selection_is_rejected_before_any_command_runs and test_racing_conflicting_submissions_exactly_one_wins. Introduced by main commit c8152f4978 (feat(gate-shell): accept gate decisions durably before slow execution); unrelated to queue-capacity remote fleet parity.

[2026-09-14T03:40:26Z · sase-zt.6.5.4.2] PROPOSED FOLLOW-UP: just check's "lint (symvision)" gate fails with "Private functions/classes should not be imported": _resolve_ref_from_link_index in src/sase/ace/tui/actions/hints/_files.py is imported by a non-owning file. Needs to be made public (or given a proper pragma) by whoever owns that hints module; unrelated to queue-capacity remote fleet parity and predates this phase (confirmed on a clean checkout with no local changes).

[2026-09-14T03:40:56Z · sase-zt.6.5.4.2] PROPOSED FOLLOW-UP: just test-scoped on current main (unrelated to this phase's fleet/queue-capacity changes, none of these files reference fleet_agents or queue_capacity) has additional deterministic-looking failures needing separate triage: tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase; tests/llm_provider/test_usage_config.py (6 params, e.g. test_usage_indicator_defaults_and_overrides asserts projected window key order and gets ("weekly","session-low",...) instead of ("session-low","weekly",...)); tests/test_bead/test_snooze_gate_actions.py::test_bead_snooze_rejects_an_unparsable_duration_and_leaves_the_gate_pending; tests/test_bead/test_cli_work_contention_regressions.py (2 tests, ~120s each, possibly lock-timeout flakiness under host load rather than a real defect — worth a rerun in isolation to confirm before filing as a bug).

[2026-09-14T03:43:46Z · sase-zt.6.5.4.2] Ratcheted sase-core-revision.txt ef2b9cfba772->a86cd9e9f56a (sase-core master; publishes ResolvedAgentSummaryWire.queue_capacity/queue_capacity_explicit, fleet schema v2->v3), rebuilt sase_core_rs via just rust-dev-install, kept pyproject.toml's >=0.34.25,<0.35.0 floor unchanged per the release-branch-reconciler convention (a subsequent unrelated release commit a35b18220f/v0.34.26 landed upstream mid-session with no functional diff from a86cd9e). Taught _fleet_agents_rows._agent_from_summary to call the existing Agent.set_queue_capacity(...) adapter from the new wire fields, mirroring the queue_weight pattern; remote capacity is display/metadata-only (verified local admission via refresh_runner_slot_context is unaffected by a remote c100 row). Added 4 contract tests in tests/ace/tui/test_fleet_agents_projection.py covering positive c100, explicit-zero c0 ('legacy 0'), absent-quiet, and legacy-wait_runners-normalizes-to-canonical (the last starts from a real fleet_project_resolved_agent_summary binding call, not a hand-built fixture). Fixing this exposed and repaired 3 latent, version-coupled fixture/production bugs surfaced by the schema bump to v3 (all now fixed): _fleet_agents_payload._is_normalized_response hardcoded schema_version==1 causing federation responses to be double-normalized (now checks structural count_hosts/configured_host_count instead); tests/ace/tui/_fleet_locator_fixture.py and tests/_fleet_contract_sase_core_rs_helpers.py hardcoded CapabilitySetWire/OriginLocatorWire schema_version:1, which core's normalized()/origin_from_host restamp to the current contract version and then compare by equality (now read dynamically via the fleet_contract_schema_version binding). Also fixed a stale tests/test_fleet_contract_sase_core_rs.py::test_fleet_contract_bindings_are_reachable_through_strict_loader assertion (1->3) and repaired 2 pre-existing unformatted files (tests/monitor/test_monitor_followup.py, test_monitor_start_nested_cwd.py) via just fmt so just check's fmt gate could run at all. Verified: all 78 fleet-tagged tests pass (pytest tests/ -k fleet, 1 pre-existing skip); ruff format/lint, mypy, keep-sorted, pyscripts, changelog, patch/stitch-terminology, toobig, and sase validate all pass; just test-scoped passed 41520/41535 with 15 unrelated failures (pager circular-import from a59ded7669, gate-decision-acceptance issues from c8152f4978, usage_config window ordering, bead lock-contention timing, etc. -- confirmed unrelated: none reference fleet_agents/queue_capacity, and the pager circular import independently reproduces on a clean a59ded7669 checkout with zero local changes) filed as 4 PROPOSED FOLLOW-UP notes on this bead, plus a pre-existing unrelated symvision private-import violation in ace/tui/actions/hints/_files.py also filed. sase bead epic-symbols sase-zt.6.5.4.2 reported no entries. Main SHA a59ded7669, core SHA a86cd9e9f56a.

## Dependencies

- **Depends on:** [sase-zt.6.5.4.1](sase-zt.6.5.4.1.md) ✓ · ⧖ 2026-09-13
- **Blocks:** [sase-zt.6.5.4.3](sase-zt.6.5.4.3.md) ◐ · ⧖ 2026-09-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zt.6.5.4.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zt.6.5.4.2/README.md) | [sase-zt.6.5.4.2](sase-zt.6.5.4.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1dd9160`](https://github.com/sase-org/sase/commit/1dd9160fdb98c187bbd09abf38f465df4345b0c1) | feat(ace/fleet): restore queue capacity parity for remote fleet agent rows | [sase-zt.6.5.4.2](sase-zt.6.5.4.2.md) | 2026-09-13 23:45:56 EDT |
