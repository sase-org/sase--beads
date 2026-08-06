# Bead: sase-fp.5 — Selection health metrics and false-negative detection

[Bead Pages](../README.md) / [sase-fp](README.md) / sase-fp.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tn](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tn/README.md) · **Assignee:** `sase-fp.5` · **Size:** medium
**Created:** 2026-08-05 20:56:24 EDT · **Closed:** 2026-08-05 23:40:29 EDT
**Plan:** [202608/test\_suite\_tier1.md](https://github.com/sase-org/sase--plans/blob/main/202608/test_suite_tier1.md)

## Description

health: persist selection manifests to a durable host-local store, detect when a full run fails a test a recent scoped run excluded, and add `just selection-health` to summarize coverage, escalation, and false-negative rates.

## Notes

[2026-08-06T02:51:42Z · sase-fp.5] PROPOSED FOLLOW-UP: Correlate GitHub Actions test failures with local selection manifests — CI, not just local full-lane runs, should feed the false-negative metric; needs the manifest to travel with the change (noted in the epic plan as out of scope for the health phase).

[2026-08-06T02:52:06Z · sase-fp.5] PROPOSED FOLLOW-UP: The contract set now runs 24.3s serially against its 30s hard budget, leaving under 6s of headroom before `just check` starts failing on the budget guard; either raise the budget with a measurement or prune the set.

[2026-08-06T03:40:08Z · sase-fp.5] PROPOSED FOLLOW-UP: load-sensitive test flakes under parallel `just check` — tests/ace/tui/util/test_stall_watchdog.py::test_watchdog_keeps_hitch_and_stall_state_machines_independent, tests/test_contract_manifest.py::test_contract_set_serial_runtime_stays_within_budget, tests/ace/tui/test_prompt_bar_xprompt_selector_requests.py::test_vcs_tag_{offers_project_local_xprompts_by_canonical_name,directory_key_spelling_also_resolves}, and tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout each failed in one run and passed in isolation and in other runs; they need real timing/isolation hardening rather than wall-clock budgets.

[2026-08-06T03:40:29Z · sase-fp.5] Added the selection-health store (tests/_test_selection_health.py), the full-lane failure recorder plugin, tools/selection_health + `just selection-health`, and runner wiring in tools/run_pytest (scoped-manifest copy, escalation recording before handoff, opt-out via SASE_TEST_SELECTION_HEALTH_DISABLED). Verified: just lint clean (ruff, mypy over 2750 files, symvision, toobig); 105 targeted tests across the new health modules and the touched runner/Justfile tests pass; 278 contract-marked tests pass; two full `just check` runs each reached 25,681 passed with only load-induced flakes (each failure reproduced green in isolation and did not repeat across runs) — noted as a PROPOSED FOLLOW-UP. Fixed a real regression the full run caught: tests/test_suite_gate_integration.py's miniature repo now copies _test_selection_health.py and points SASE_HOME at the tmp tree, so the runner's new import resolves and records stay out of the developer's real ~/.sase.

[2026-08-06T03:47:02Z · sase-fp.5] PROPOSED FOLLOW-UP: add tests/ace/tui/test_app_title.py::test_on_mount_refines_title_to_resolved_version to the load-sensitive flake list — it failed once under parallel `just check-full` and passed in isolation, same shape as the other timing flakes noted above.

## Dependencies

- **Depends on:** [sase-fp.3](sase-fp.3.md) ✓ · ⧖ 2026-08-05
- **Blocks:** [sase-fp.6](sase-fp.6.md) ✓ · ⧖ 2026-08-05
- **Blocks:** [sase-fp.7](sase-fp.7.md) ✓ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fp.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fp.5/README.md) | [sase-fp.5](sase-fp.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`96183d7`](https://github.com/sase-org/sase/commit/96183d71b3ef6edd427d8c388ba0f96644af6244) | feat(tests): track test-selection health and detect selection false negatives | [sase-fp.5](sase-fp.5.md) | 2026-08-05 23:41:36 EDT |
