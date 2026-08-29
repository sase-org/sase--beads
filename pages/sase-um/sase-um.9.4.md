# Bead: sase-um.9.4 — Ship v0.17.0 and re-measure every acceptance criterion

[Bead Pages](../README.md) / [sase-um.9](sase-um.9.md) / sase-um.9.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-um.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-um.land.md) · **Assignee:** `sase-um.9.4` · **Size:** medium
**Created:** 2026-08-28 15:49:00 EDT · **Closed:** 2026-08-28 19:54:32 EDT
**Plan:** [202608/release\_gate\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202608/release_gate_completion.md)

## Description

ship: watch ci_watch reach eligible on sase-org/sase, confirm the guarded merge of PR #284 succeeds with --merge --match-head-commit, confirm publish.yml tags and publishes v0.17.0 to PyPI, and re-measure all seven acceptance criteria against live data.

## Notes

[2026-08-28T21:44:04Z · sase-um.9.4] STATUS: Master Gate on tip ed74b9f7b is green (run 33211957365, wall 23.3 min: core-wheel 9.1 min cache-miss on pin 0060003 plus test(3) 14.1 min). Full CI 33212832198 is in progress on the same SHA (workflow_dispatch). PR #284 still OPEN/MERGEABLE/CLEAN. Live ci_watch was check_error on every tick since 16:55 because host uv still had editable bugyi-chops 0.8.0 while chezmoi vars are per-repo mappings; installed git 0.9.0 (c3d613d) and added GH_FORCE_TTY=0/NO_COLOR/CLICOLOR=0 to the chop env so gh 2.98 JSON color on pipes no longer fails closed. Dry-run now: sase release_reason=heavy_lane_not_green (expected until Full CI greens), telegram #21 release_pr_not_clean, github no_release_pr. Do not hand-merge #284.

[2026-08-28T21:44:24Z · sase-um.9.4] PROPOSED FOLLOW-UP: Publish bugyi-chops 0.9.0 (tag v0.9.0; PyPI still 0.7.0) and ratchet its sase pin off <0.17.0 before the host upgrades to sase 0.17.0. Also neutralize gh JSON color inside ci_watch run_command so hosts without the chop env still parse.

[2026-08-28T21:44:44Z · sase-um.9.4] Baseline AC snapshot 2026-08-28T21:42Z: (1) 1 cancelled in last 50 — run 33127407974, test(1) already failed then sibling shards cancelled under fail-fast:false (same signature as the parent plan, not push supersession). (2) trailing-50 p50 wall 9.48 min (completed n=49); newest 8-shard green is 23.3 min. (3) 42/42 master commits in 24h have a gate run, 41/42 completed (97.6%). (4) ci_watch reasons are now gating/heavy (heavy_lane_not_green), never default_branch_not_green; not yet eligible. (5) #284 unmerged. (6) PR ci.yml pull_request queue wait p50 0s over 30 runs (startedAt==createdAt). (7) PyPI still 0.16.0, no v0.17.0 tag.

[2026-08-28T23:18:20Z · sase-um.9.4--1] STATUS: Full CI 33212832198 on ed74b9f7b is RED. Attribution: visual-test green (11m48s); test(3.12) green; coverage-contexts green; lint/perf-floors/ace-page-group green. The only failing job is test(3.14) (27m46s): 1 failed / 37943 passed — tests/test_models_panel_display.py::test_panel_warns_once_and_keeps_alias_warning_through_refresh. After mutating configured_source to builtin, a single pilot.pause() raced the async provider-snapshot worker, so the row still showed "  ! small". test(3.13) was cancelled after that failure, not a second defect. Master moved 5 commits past the dispatched SHA; HEAD 0235ff059 Master Gate 33217991552 is RED on test(2) only: tests/test_agent_loader_query_window.py::test_windowed_loader_keeps_completed_when_active_exceeds_limit (same failure on 45a0a8880 and 84263159f). Root cause: 45a0a8880 landed the Python contract for sase-core aeeaddd/v0.32.14 without ratcheting sase-core-revision.txt off 0060003 (v0.32.13). Pin ratchet a320fc88922a (v0.32.14) plus wait_for on the models-panel refresh are in this workspace; not dispatching Full CI until they land on origin/master.

[2026-08-28T23:50:44Z · sase-um.9.4--2] STATUS: just check passed (ky488s13h53d, exit 0, 4m18s). Pin a320fc88922a plus wait_for_snapshot_idle are still uncommitted; submitting host stitch next. This is a mid-flight ship-phase commit: do not treat it as phase completion. After it lands on origin/master, continue: confirm Master Gate on the new HEAD, dispatch Full CI, watch ci_watch merge #284, confirm v0.17.0 publish, re-measure all seven ACs, then close only this bead.

[2026-08-28T23:54:32Z · sase-um.9.4--2] Auto-closed by `sase stitch create` after create_commit landed fa74163b5 ("fix(ci): ratchet core pin and wait for models-panel snapshot refresh"). No verification is implied by this note. Reopen with `sase bead open sase-um.9.4`, or pass `-B|--do-not-close-bead` on mid-flight commits.

## Dependencies

- **Depends on:** [sase-um.9.2](sase-um.9.2.md) ✓ · ⧖ 2026-08-28
- **Depends on:** [sase-um.9.3](sase-um.9.3.md) ✓ · ⧖ 2026-08-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-um.9.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-um.9.4.md) | [sase-um.9.4](sase-um.9.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fa74163`](https://github.com/sase-org/sase/commit/fa74163b5a742fa1cd7e8bfcf98fdd5c0b579da3) | fix(ci): ratchet core pin and wait for models-panel snapshot refresh | [sase-um.9.4](sase-um.9.4.md) | 2026-08-28 19:52:06 EDT |
