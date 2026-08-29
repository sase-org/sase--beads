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

[2026-08-29T07:09:43Z · sase-um.9.5.4--3] STATUS: Full CI 33232978442 on 49d6c4188 is RED. Failed nodes (ignore obsolete 623788895): (1) full/test(3.12) job 99053300955 coverage leg FAILED tests/fakey/test_pipe_e2e.py::test_default_pipe_creates_family_member_with_fork_and_shared_workspace — successor invoke used LaunchSelection(provider=claude, model=opus, alias_origin=default_model) instead of inherited fakey; BrokenPipeError on Claude CLI stdin. test(3.14) green; test(3.13) cancelled. (2) full/visual-test job 99053300958 FAILED tests/ace/tui/visual/test_ace_png_snapshots_artifacts_files_empty.py wait_for _project_display_name==Alpha after 15s. Landed c1a5b36f5 with stitch -B: anonymous workflow prompt steps inherit agent_meta llm_provider/model when there is no %model and no live reservation; Artifacts Files panes that missed the first inventory get the seeded Alpha label without overwriting a live pane-local scope. just check green (escalated full suite). PR #284 OPEN MERGEABLE/CLEAN (head ebf8dfe8). publish.yml schedule 33239989521 succeeded; dispatched 33240161029 (publish_existing=false). Master Gate 33239974901 in progress on c1a5b36f5. Full CI 33240119114 (schedule, in_progress) and 33240160035 (dispatch, pending) both on c1a5b36f5; concurrency group full-ci cancel-in-progress:false. Monitoring 33240119114 (4h). Do not hand-merge. Do not auto-close.

[2026-08-29T09:01:46Z · sase-um.9.5.4--4] STATUS: Full CI 33240119114 on c1a5b36f5 is RED. Failed nodes (ignore obsolete 49d6c4188/623788895): (1) full/test(3.12) job 99068560982 coverage leg FAILED tests/test_running_agents_snapshot.py::test_list_all_agents_includes_done_and_failed — expected TS_ACE_RUN_RETRIED_CHILD (20260427140500, pid 33333) missing from list_all_agents. Reproduced: pid_is_thread(33333) is true when that number is a live host TID, so is_process_alive treats the retried child as dead. test(3.14) and coverage-contexts green on the same SHA; visual-test green (Alpha wait_for held); pipe e2e did not regress. (2) full/contention-test job 99068561001 FAILED after runner shutdown/cancel once 3.12 failed (no harness assertion). test(3.13) cancelled. Landed ca7692ee3 with stitch -B: stub pid_is_thread in the snapshot process fixture plus a colliding /proc regression. just check green (scoped 63 files). Cancelled obsolete Full CI 33240160035 (c1a5b36f5). PR #284 OPEN MERGEABLE/CLEAN (head ebf8dfe8). Dispatched Full CI 33244467241 and publish.yml 33244468516 (publish_existing=false) on ca7692ee3. Master Gate 33244341435 in progress. Monitoring 33244467241 (4h). Do not hand-merge. Do not auto-close.

PROPOSED FOLLOW-UP: other tests that plant hardcoded PIDs (11111/22222 in kill-named-agent helpers) without stubbing pid_is_thread can drop live fixture agents the same way on a busy runner.

[2026-08-29T11:18:10Z · sase-um.9.5.4--5] STATUS: Full CI 33244467241 on ca7692ee3 RED. Real failed nodes: (1) full/visual-test job 99080268574 — tests/ace/tui/visual/test_ace_png_snapshots_feature_flags.py::test_config_center_flags_narrow_png_snapshot, PNG mismatch config_center_flags_populated_70x32 (9499/724632 px). Detail title clipped to one line so ON/SUNSET wrap was missing and EFFECTIVE SOURCE showed; wait_for_visual_idle accepted that frame. Other flags snapshots passed. (2) full/coverage-contexts job 99080268747 — tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_confirm_executes_and_refreshes wait_for 5s for executed+timer_callbacks; the test's set_timer mock swallowed non-1.0 timers. test(3.12) GREEN. test(3.13)/test(3.14) cancelled after ~90m with no harness assertion (cascade). docs-build, release-core-floor-smoke, contention-test skipped. Master Gate 33244341435 RED: test(6) 99079107049 test_incompatible_exact_match_refuses_open still showed "Checking #review in ..." after pause(0.25); test(7) 99079106997 test_enter_returns_while_xprompt_file_read_is_blocked unhandled NoMatches #frontmatter-raw on hidden FrontmatterPanel during prompt-bar mount after blocked Path.read_text (production on_mount race — not patched; deferring that mount broke 468 PromptInputBar tests).

Landed 4a8b8358f (test-only waits: SUNSET sentinel + flags debounce idle; mini-xprompt wait_for verdict/analysis idle; sase-update set_timer passthrough + 15s wait; blocked-load wait for PromptTextArea) with stitch -B so this bead stays in_progress. just check green (scoped 65 files). Origin/master rebased over 1c184fb72, 72a96a801, a925744e4. Master Gate 33249652244 in progress on 4a8b8358f. Full CI 33249788999 in_progress and publish.yml 33249789774 queued (publish_existing=false) on 4a8b8358f. PR #284 OPEN MERGEABLE/CLEAN (head 7938caa41). Do not hand-merge #284. Do not auto-close.

PROPOSED FOLLOW-UP: PromptInputBar/FrontmatterPanel on_mount can raise NoMatches (#frontmatter-raw, #prompt-input-g0-p0) when load_xprompt_definition_into_home_prompt_bar mounts the bar after pop_screen while Path.read_text was blocked. A call_after_refresh deferral of on_mount setup failed 468 prompt-bar tests (query empty during on_mount always). Needs a mount-safe bind that does not skip the common path.

## Dependencies

- **Depends on:** [sase-um.9.5.1](sase-um.9.5.1.md) ✓ · ⧖ 2026-08-28
- **Depends on:** [sase-um.9.5.3](sase-um.9.5.3.md) ✓ · ⧖ 2026-08-28
- **Blocks:** [sase-um.9.5.5](sase-um.9.5.5.md) ◐ · ⧖ 2026-08-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-um.9.5.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-um.9.5.4.md) | [sase-um.9.5.4](sase-um.9.5.4.md) | 6 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e856c68`](https://github.com/sase-org/sase/commit/e856c68041ecee74e0a33836a86417a6d95d0a88) | fix(ace): reflow panel tabs after layout settles | [sase-um.9.5.4](sase-um.9.5.4.md) | 2026-08-28 23:43:28 EDT |
| sase | [`49d6c41`](https://github.com/sase-org/sase/commit/49d6c4188d1a282a73f600d334aca67718a7a81c) | test(agents-sync): harden cross-machine clone against auto-gc races | [sase-um.9.5.4](sase-um.9.5.4.md) | 2026-08-29 00:02:49 EDT |
| sase | [`c1a5b36`](https://github.com/sase-org/sase/commit/c1a5b36f5faf6f014d9d0bddea435a4e9fc4b0ee) | fix(pipe): inherit the parent model when a successor has no %model | [sase-um.9.5.4](sase-um.9.5.4.md) | 2026-08-29 03:04:20 EDT |
| sase | [`ca7692e`](https://github.com/sase-org/sase/commit/ca7692ee3329b17ef1e176e5deb95dadbc3cfc3a) | test(agent): stub pid\_is\_thread so fixture PIDs survive host TID collisions | [sase-um.9.5.4](sase-um.9.5.4.md) | 2026-08-29 04:57:19 EDT |
| sase | [`4a8b835`](https://github.com/sase-org/sase/commit/4a8b8358fdb55ef9f19c397959ed364dd50ea1c9) | test(ace): wait for TUI settle in CI-flaky flags and plugin tests | [sase-um.9.5.4](sase-um.9.5.4.md) | 2026-08-29 07:14:17 EDT |
| sase | [`60043de`](https://github.com/sase-org/sase/commit/60043deb95c5a2c730e278bd744462218de94d2b) | test(ace): capture only the sase-update restart poll timer | [sase-um.9.5.4](sase-um.9.5.4.md) | 2026-08-29 09:14:16 EDT |
