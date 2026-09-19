# Bead: sase-11l.11 — Complete hold admission and visibility after the landing audit

[Bead Pages](../README.md) / [sase-11l](README.md) / sase-11l.11

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11l.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.land.md) · **Assignee:** `sase-11l.11.land`
**Created:** 2026-09-18 18:08:40 EDT
**Plan:** [202609/hold\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/hold_landing_repairs.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/hold_landing_repairs.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | file:explicit:563b855a65c898f88a032e20 | attached via sase artifact create --bead |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/hold_landing_repairs.md

<!-- sase:links:end -->

## Description

Holds select the same targets across CLI, directives, admission, and display; arming is ordered with admission; capture and release evidence stays visible; and observable wait cycles are reported on a supported released core.

## Notes

[2026-09-19T10:25:55Z · sase-11l.11.5.land] LANDING REVIEW (pre-check-full): sase-11l.11.5 closed; pin 39602c95 v0.34.63 contains agent_hold_deadlock_reaches. All five descendants closed. Source contracts still present (shared hold_fields_to_selectors, runner_slot_admission_lock, capture/prune render, deadlock binding). Hold files were not drifted by later ToolRun/service/catalog commits. Focused hold regressions 104 passed. 11.4 PROPOSED FOLLOW-UP remains sase-10d / sase-12y.4 (declined new task). No --epic-symbol entries. Running just fix, just check-full, and sase-core just check before close, as required by plan:202609/hold_landing_repairs.md landing evidence.

[2026-09-19T12:24:47Z · sase-11l.11.5.land--1] LANDING BLOCKED: parent gate `just fix && just check-full && sase-core just check` failed in monitor pz319b38sapt (exit 1, 1h17m). just fix, fmt, ruff, mypy, symvision, SASE validation, and committed-plans all passed. Failure is test-cost: 3 failed / 43366 passed / 15 skipped, plus leak-detector blocking gate (12 poisoning changes).

None of the failures are caused by hold repairs or the core pin (commits 0e4cfe92cb, 8de747c36a, a1bb1df454, 388d516030, 0fc51c2998). Focused hold regressions previously passed (104). Did not close sase-11l.11. Did not --force.

Dispositions:
1. tests/ace/tui/actions/test_service_host_keys.py::test_x_does_not_toggle_the_host_on_nested_scheduler_rows — deterministic isolated failure; DISCOVERED ISSUE on in-progress epic sase-11y / phase sase-11y.7. Declined a new task as causally owned by the Services-tab epic.
2. tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget — full-lane fail (32.7s), isolated pass (2.75s); +1 on ready flake sase-136. origin 8989d0a724 later retries 3 times.
3. tests/dispatch/test_machine_bootstrap_real_gateway.py::test_bootstrap_issue_enroll_hello_round_trip_through_real_gateway — full-lane fail (status.state error), isolated pass; new flake task (no duplicate).
4. Leak detector poisoning of SASE_AXE_DISABLE_SYSTEMD_SCOPE / SASE_DETACH_SCOPE_DISABLE — session autouse guards ignored by isolation restore but not by the detector snapshot on this SHA. Declined a new task: origin 8989d0a724 (sase-zr.7.1.1.5.4.2) already reuses the isolation ignore list in leak-detector snapshots.

Published-package floor stays on sase-10d / sase-12y.4. Plan file 202609/hold_deadlock_core_pin.md remains status: done.

[2026-09-19T12:27:50Z · sase-11l.11.5.land--1] Gateway hello full-lane flake is now ready task sase-13h (declined as duplicate of nothing; not DISCOVERED ISSUE on sase-xe.16.11 because isolated pass shows no product gap in enrollment). Leak-detector report: file:explicit:05b5faf92b7d3260de286434.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11l.11.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.11.land.md) | [sase-11l.11](sase-11l.11.md) | 0 |
