# Bead: sase-um.9.5.4 — Let ci\_watch merge and publish SASE v0.17.0, then remeasure acceptance

[Bead Pages](../README.md) / [sase-um.9.5](sase-um.9.5.md) / sase-um.9.5.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-um.9.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-um.9.land.md) · **Assignee:** `sase-um.9.5.4` · **Size:** medium
**Created:** 2026-08-28 20:17:50 EDT
**Plan:** [202608/finish\_release\_gate\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202608/finish_release_gate_landing.md)

## Description

ship: install the hardened chop revision, exercise its guarded live merge of PR #284, publish v0.17.0, and record all seven acceptance measurements.

## Notes

[2026-08-29T03:27:11Z · sase-um.9.5.4] STATUS: chopcolor 36c925f is live (ci_watch.py SHA256 match; GH_FORCE_TTY/NO_COLOR/CLICOLOR forced in GitHubReader). Dry-run `sase axe chop run ci_watch -n -V` errors=0. sase #284 gating_workflow_running then blocked by CONFLICTING/DIRTY; telegram #21 merge_state_not_clean (not gating_workflow_missing/heavy_lane_not_green); github no_release_pr. Plugin GitHub settings: sase merge-only, plugins squash-only. Dispatched Full CI 33231000542 and publish.yml 33231054511 (publish_existing=false) on 623788895. Master Gate 33230479947 test(7) FAILED tests/ace/tui/test_panel_tab_strip_compact.py::test_reflow_to_fit_ladder_picks_tier_by_width (assert full==compact); 9.5.3 pause() did not settle resize. Replacing pause with wait_for plus post-refresh reflow. Do NOT auto-close this bead: 9.5.5 is waiting on it and v0.17.0 is unpublished. Do not hand-merge #284.

## Dependencies

- **Depends on:** [sase-um.9.5.1](sase-um.9.5.1.md) ✓ · ⧖ 2026-08-28
- **Depends on:** [sase-um.9.5.3](sase-um.9.5.3.md) ✓ · ⧖ 2026-08-28
- **Blocks:** [sase-um.9.5.5](sase-um.9.5.5.md) ◐ · ⧖ 2026-08-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-um.9.5.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-um.9.5.4/README.md) | [sase-um.9.5.4](sase-um.9.5.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e856c68`](https://github.com/sase-org/sase/commit/e856c68041ecee74e0a33836a86417a6d95d0a88) | fix(ace): reflow panel tabs after layout settles | [sase-um.9.5.4](sase-um.9.5.4.md) | 2026-08-28 23:43:28 EDT |
