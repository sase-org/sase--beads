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

[2026-08-29T03:46:34Z · sase-um.9.5.4] STATUS: landed e856c6804 (tab-strip post-refresh reflow + wait_for) with stitch -B so this bead stays in_progress. just check green (escalated full suite, core-identity-changed). Master Gate 33232113220 in progress on e856c6804. Full CI 33232205513 queued on e856c6804 behind 33231000542 (623788895). publish.yml 33232206449 refreshing PR #284. Do not hand-merge. Do not auto-close.

[2026-08-29T03:59:02Z · sase-um.9.5.4--1] STATUS: Master Gate 33232113220 on e856c6804 is RED. Sole failed node: test(7) job 99046660131. FAILED tests/agents_sync/test_cross_machine_e2e.py::test_three_identities_converge_and_localize_through_non_fast_forward_race — git clone of the local bare remote into verify exited 128 after all identity/sync assertions passed. Helper used check=True so pytest omitted stderr. Reproduced locally: PASS (5/5). Lint and other shards on that run were green (core-wheel, lint, test 1-6+8). GitHub Actions cache was also 400/unavailable on several jobs (not the failing step). Hardening the test helper: surface git stdout/stderr, GIT_OPTIONAL_LOCKS=0, gc.auto=0 on repos, clone --no-local to avoid hardlink/auto-gc race. Do not mute. Do not hand-merge #284. Do not auto-close.

PROPOSED FOLLOW-UP: apply the same clone/--no-local + gc.auto=0 + stderr-on-failure helper to tests/agents_sync/git_sync_fixtures.py (shared git() used by other agents-sync verify clones). Consider GIT_OPTIONAL_LOCKS=0 (and GIT_DIR/GIT_WORK_TREE pop) in production sase.agents_sync.git._noninteractive_git_env so live sidecar clones cannot race receive-pack auto-gc.

[2026-08-29T04:06:03Z · sase-um.9.5.4--1] STATUS: landed 49d6c4188 (cross-machine e2e clone hardening: --no-local, gc.auto=0, GIT_OPTIONAL_LOCKS=0, stderr on git failure) with stitch -B so this bead stays in_progress. just check green (scoped 63 files). Master Gate 33232866336 in progress on 49d6c4188. Full CI 33232978442 queued on 49d6c4188 behind 33231000542 (623788895). 33232205513 (e856c6804) cancelled. publish.yml 33232979152 (publish_existing=false) queued to refresh PR #284. Do not hand-merge. Do not auto-close.

[2026-08-29T04:13:57Z · sase-um.9.5.4--2] STATUS: Master Gate 33232866336 on 49d6c4188 is GREEN (core-wheel, lint, test 1-8 all success; cache 400s are annotations only). PR #284 is OPEN MERGEABLE/CLEAN (head eaeaf47f, chore(master): release 0.17.0 + sync metadata). publish.yml 33232979152 (publish_existing=false) succeeded. Dry-run `sase axe chop run ci_watch -n -V` parsed JSON with errors=0: sase-org/sase green on master@49d6c4188; #284 skipped heavy workflow not green (expected); telegram #21 merge_state_not_clean (not gating_workflow_missing); github no_release_pr. Full CI 33232978442 pending on 49d6c4188 behind in-progress 33231000542 (old SHA 623788895: test 3.12/3.14 and coverage-contexts already failed; test 3.13 still running; concurrency group full-ci cancel-in-progress:false). Monitoring 33232978442 (4h). Do not hand-merge. Do not auto-close.

## Dependencies

- **Depends on:** [sase-um.9.5.1](sase-um.9.5.1.md) ✓ · ⧖ 2026-08-28
- **Depends on:** [sase-um.9.5.3](sase-um.9.5.3.md) ✓ · ⧖ 2026-08-28
- **Blocks:** [sase-um.9.5.5](sase-um.9.5.5.md) ◐ · ⧖ 2026-08-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-um.9.5.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-um.9.5.4.md) | [sase-um.9.5.4](sase-um.9.5.4.md) | 3 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e856c68`](https://github.com/sase-org/sase/commit/e856c68041ecee74e0a33836a86417a6d95d0a88) | fix(ace): reflow panel tabs after layout settles | [sase-um.9.5.4](sase-um.9.5.4.md) | 2026-08-28 23:43:28 EDT |
| sase | [`49d6c41`](https://github.com/sase-org/sase/commit/49d6c4188d1a282a73f600d334aca67718a7a81c) | test(agents-sync): harden cross-machine clone against auto-gc races | [sase-um.9.5.4](sase-um.9.5.4.md) | 2026-08-29 00:02:49 EDT |
| sase | [`c1a5b36`](https://github.com/sase-org/sase/commit/c1a5b36f5faf6f014d9d0bddea435a4e9fc4b0ee) | fix(pipe): inherit the parent model when a successor has no %model | [sase-um.9.5.4](sase-um.9.5.4.md) | 2026-08-29 03:04:20 EDT |
