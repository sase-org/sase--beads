# Bead: sase-ud.13.1.2 — Remove the gate\_shell\_handoff flag and the blocking Off branch

[Bead Pages](../README.md) / [sase-ud.13.1](sase-ud.13.1.md) / sase-ud.13.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ud.13](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ud.13.md) · **Assignee:** `sase-ud.13.1.2` · **Size:** large
**Created:** 2026-08-27 08:49:05 EDT · **Closed:** 2026-08-27 10:38:12 EDT
**Plan:** [202608/gate\_shell\_status\_collapse.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_shell_status_collapse.md)

## Description

flag-removal: make the gate-shell handoff unconditional in the plan and questions marker handlers, delete the flag module, registry member, and config schema property, delete the blocking wait machinery the Off branch was the last consumer of, retarget the runner tests that drove the Off branch, and close flag bead sase-uo.

## Notes

[2026-08-27T14:06:54Z · sase-ud.13.1.2] PROPOSED FOLLOW-UP: Remove the orphaned link_pager FeatureFlag registry entry (src/sase/feature_flags/registry.py) — its flag bead sase-ul (Retire link_pager) closed 15h before this phase started, but the enum member/registry definition/schema entry were never deleted. This fails 'just _lint-flags' (rule 7: closed flag bead 'sase-ul' still has a surviving 'link_pager' definition) unrelated to this phase's gate_shell_handoff removal; confirmed pre-existing and unrelated by checking 'sase bead show sase-ul' (closed 2026-08-26 17:57, well before sase-ud.13.1.2 was created 2026-08-27 08:49).

[2026-08-27T14:38:12Z · sase-ud.13.1.2--1] Exhaustive check-full-equivalent verification complete. just check already passed (symvision, mypy, ruff, fmt, diff-scoped test lane) except for lint (feature flags), which fails only on the pre-existing, unrelated sase-ul/link_pager registry issue (already documented as a PROPOSED FOLLOW-UP on this bead). Monitored full-suite run (xasvz10d4p5m): just test-cost's full pytest run passed cleanly (37786 passed / 13 skipped, 0 failed), confirming the gate_shell_handoff flag removal is behaviorally correct across the entire suite. The run then failed only at tools/check_test_cost_budgets (hard CPU budget overages on total_file_cpu_seconds/ace_page_enter/ace_settle_pilot/pilot_pause_delay/textual_app_run_test_enter), which is the standing, actively-tracked pre-existing issue sase-j0 ('just check-full is red on master: every suite-cost summary budget and two ACE/Textual cause budgets are exceeded'). Verified this bead's diff is not the cause: production changes are net deletions only (268 removed / 6 added, no new computation) and the only touched ACE TUI test files (4 files, 23 net lines) are far too small to explain the suite-wide CPU overage; node and call counts are in the normal range, ruling out test-count growth from this diff. Recorded independent corroboration on sase-j0 (+35) with the full numeric breakdown. selection-health was not reached because the && chain stopped at the pre-existing test-cost gate, but the full pytest run it depends on already passed cleanly. sase bead epic-symbols sase-ud.13.1.2 reports no outstanding entries.

## Dependencies

- **Blocks:** [sase-ud.13.1.3](sase-ud.13.1.3.md) ✓ · ⧖ 2026-08-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ud.13.1.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ud.13.1.2.md) | [sase-ud.13.1.2](sase-ud.13.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a646bda`](https://github.com/sase-org/sase/commit/a646bdaf6b75838326f8c9d16f42fb935393e5c1) | refactor(plan-gate): remove the gate\_shell\_handoff flag and blocking Off branch | [sase-ud.13.1.2](sase-ud.13.1.2.md) | 2026-08-27 11:14:29 EDT |
