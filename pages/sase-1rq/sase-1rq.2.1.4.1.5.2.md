# Bead: sase-1rq.2.1.4.1.5.2 — Repair the remaining failures under the real contention shape

[Bead Pages](../README.md) / [sase-1rq.2.1.4.1.5](sase-1rq.2.1.4.1.5.md) / sase-1rq.2.1.4.1.5.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.2.1.4.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.1.4.1.land.md) · **Assignee:** `sase-1rq.2.1.4.1.5.2` · **Size:** medium
**Created:** 2026-11-07 23:46:20 EST
**Plan:** [202611/contention\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202611/contention_completion.md)

## Description

failures: repair every failure family from the completed repeat without weakening workload or gates, and prove a complete zero-failure contention repeat.

## Notes

[2026-11-08T07:43:38Z · sase-1rq.2.1.4.1.5.2] Runtime complete-red inventory (986 failed / 8 errors, monitor 0kkpwxe1tesr) was an incomplete Python 3.12 env: sase-core-rs 0.43.2 without required bindings, missing sase-macro-lsp, missing plugins.required (no #gh). Hosted CI installs the pin wheel + visual extras + LSP + plugins. Repaired /tmp/sase-1rq-runtime-py312 in place (0.44.0 wheel, LSP copy, setup_required_plugins). Serial 303 passed across the largest lastfailed families; contended -n 8 on CPUs 0-1: 63 passed including the hosted SIGTERM node tests/test_sudo_ssh.py::test_wait_for_remote_sudo_ledger_stop_writes_remote_stop. Starting a full default py312 contention repeat for the zero-failure proof. Hosted 17 unnamed reports from cancelled Telemetry 42437776062 remain leads only.

[2026-11-08T09:12:41Z · sase-1rq.2.1.4.1.5.2--1] Complete py312 contention repeat nchwjrsd0sjp (SHA ea5c1f0561, 60578 passed / 3 failed / 21 skipped in 4355s, 26 workers, CPUs 0-1): pytest FAILED tests/ace/tui/test_app_title.py::test_on_mount_refines_title_to_resolved_version (15s mount hang guard), tests/ace/tui/test_macro_browser_load_keymap.py::test_enter_returns_while_macro_file_read_is_blocked (10s wait_for hang guard), tests/test_core_rust.py::test_require_rust_extension_raises_when_missing (live install_context was other, not checkout_venv). Harness tally listed tests/t.py::test_before_cancel because test_interrupted_failure_reports_stay_separate_from_completed_tally called main(["contention"]) without isolating CONTENTION_ARTIFACT_DIRECTORY and rmtree/overwrote parent repeat-01.json. Related beads sase-1s2/1s3/1s4/xo/1rf/1nf.10.1 did not recur. Repairs: pin rust test to checkout_venv; title/macro waits use DEFAULT_WAIT_TIMEOUT/LOAD_TOLERANT_TIMEOUT hang detectors; SASE_CONTENTION_ACTIVE nested artifact dir; isolate the interrupted-tally test. Serial 9 passed; contended -n 8 on CPUs 0-1: 74 passed (macro node 12.96s, above the old 10s bound). Next: sase tool run check, then an unchanged-shape full py312 repeat.

[2026-11-08T11:00:17Z · sase-1rq.2.1.4.1.5.2--2] Complete py312 contention repeat y3mjfkcrrhe9 (SHA dde1ada139, 60579 passed / 3 failed / 21 skipped in 4351s, 26 workers, CPUs 0-1): pytest FAILED tests/ace/tui/test_artifacts_agents_loading.py::test_agent_first_page_paints_before_full_extension (synchronous full_started.wait starved run_worker/call_later; loop stall recovered after 60.102s), tests/ace/tui/test_update_toast_startup.py::test_startup_update_toast_appears_once_in_tui (12s toast timeout expired during pause after ~10s stall), tests/ace/tui/widgets/test_auto_macro_completion.py::test_vcs_tag_project_namespace_opens_project_macro_menu (empty-text soft-completion requested project=None before VCS tag resolved). Related beads sase-1s2/1s3/1s4/xo/1rf/1nf.10.1 did not recur. Repairs: page.wait_for(full_started.is_set()); pin _TOAST_TIMEOUT_SECONDS to 3*LOAD_TOLERANT_TIMEOUT; wait_for_canonical_catalog_project drops empty-text None lookups. Serial 5 passed; contended SASE_PYTEST_WORKERS=8 on CPUs 0-1: 39 passed (agents-loading 8.35s, toast 8.25s, vcs-tag menu 0.66s). Next: sase tool run check, then an unchanged-shape full py312 repeat.

[2026-11-08T13:31:27Z · sase-1rq.2.1.4.1.5.2--3] Complete py312 contention repeat przd5aakw2gc (SHA 2400e61e93, 60579 passed / 3 failed / 21 skipped in 4659s, 26 workers, CPUs 0-1): pytest FAILED tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply (gated_muse_script wait_for 8s and wait_for_page 5s pause; process.poll() was not None after a pump stall), tests/test_provider_disable.py::test_facade_try_disable_one_winner_under_process_contention (communicate timeout 10s while six workers imported sase under swap; peaks soak swap 4.6G, pressure_memory_full 25.14), tests/llm_provider/test_codex_usage_probe.py::test_descendant_processes_are_reaped (os.kill(pid,0) treated a SIGKILL zombie as live). Related beads sase-1s2/1s3/1s4/xo/1rf/1nf.10.1 did not recur. Repairs: wait_for_page uses settle_pilot DEFAULT_WAIT_TIMEOUT; muse gate/parser/process waits use LOAD_TOLERANT_TIMEOUT; provider-disable communicate uses one shared LOAD_TOLERANT hang guard plus leftover kill; wait_until_reaped treats zombies as gone. Serial 5 passed; contended SASE_PYTEST_WORKERS=8 on CPUs 0-1: 58 passed (live-reply session 15.55s, above the old 8s bound). sase tool run check 772e940304d545c1c45c7f247c2c5f7b succeeded. Next: unchanged-shape full py312 repeat.

[2026-11-08T15:33:57Z · sase-1rq.2.1.4.1.5.2--4] Complete py312 contention repeat qc8w44552q7q (SHA 229f85a998, 60583 passed / 4 failed / 21 skipped in 4715s, 26 workers, CPUs 0-1): pytest FAILED tests/fakey/test_cli.py::test_sigterm_during_barrier_exits_cleanly (2s started-file hang guard), tests/test_config_cache_isolation.py::test_blocked_refresh_worker_does_not_poison_a_later_config_read (nested pytest timeout 60s, SIGKILL after TimeoutExpired), tests/test_notification_modal_scroll.py::test_uppercase_g_reaches_detail_bottom_from_real_input_path[#notification-list-shift+g-G] (single pilot.pause after Key left scroll_y at 100 of 221), tests/fakey/test_provider_drain_e2e.py::test_provider_drain_e2e_relaunches_stranded_agent (_wait_for_json 30s expired waiting for replacement done.json). Related beads sase-1s2/1s3/1s4/xo/1rf/1nf.10.1 did not recur. Peaks: cgroup 13.3G, soak rss 13.2G, soak swap 3.3G, oom_kill 0, pressure_memory_full 12.6, collected 26/26 (60607) tests 60607 done 4 failed. Repairs: fakey CLI started/wait hang guards use LOAD_TOLERANT_TIMEOUT; nested pytest uses 3*LOAD_TOLERANT_TIMEOUT; notification G/g waits use wait_for on scroll_y; drain grandchild JSON waits use _DRAIN_WAIT_TIMEOUT and report last payload. Serial 14 passed; contended SASE_PYTEST_WORKERS=8 on CPUs 0-1: 126 passed (drain e2e 26.91s, nested pytest 16.95s, both above the old bounds). sase tool run check f271a90bfada6ca42e7a614bb494cd73 succeeded. Next: unchanged-shape full py312 repeat.

[2026-11-08T17:39:09Z · sase-1rq.2.1.4.1.5.2--5] Complete py312 contention repeat h1tfhztprh27 (SHA 6a6cc2b426, 60590 passed / 5 failed / 21 skipped in 4728s, 26 workers, CPUs 0-1): pytest FAILED tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding (5s AcePage.press hang guard), tests/ace/tui/test_config_pane_widget_jump.py::test_config_jump_preserves_collapsed_sections (settle_pilot Pilot.pause(0) WaitForScreenTimeout 30s during AcePage enter), tests/ace/tui/test_gate_input_panel_layout.py::test_tab_reaches_every_field_and_scrolls_it_into_view (same WaitForScreenTimeout during wait_for_terminal), tests/completion/test_zsh_smoke.py::test_tab_completes_after_root_print_command_option (zsh PTY _read_until 5s), tests/completion/test_zsh_smoke.py::test_dynamic_completion_does_not_leak_extendedglob_to_shell (same 5s PTY marker wait). Related beads sase-1s2/1s3/1s4/xo/1rf/1nf.10.1 did not recur. Peaks: cgroup 14.4G, soak rss 14.0G, soak swap 2.5G, oom_kill 0, pressure_memory_full 45.25, min_mem_available 6.5G, collected 26/26 (60615) tests 60615 done 5 failed. Repairs: settle_pilot bounds pause with _REFRESH_TIMEOUT_SECONDS and returns on TimeoutError/WaitForScreenTimeout; AcePage.press hang detector DEFAULT_WAIT_TIMEOUT; remaining 5s press wraps use LOAD_TOLERANT_TIMEOUT; gate tab loop wait_for focus change; zsh PTY READY/marker/file waits use LOAD_TOLERANT_TIMEOUT. Serial 21 passed; contended SASE_PYTEST_WORKERS=8 on CPUs 0-1: 56 passed (empty-panel escape 12.53s, above the old 5s bound). sase tool run check b04bef56db82dacb850e586b94500810 succeeded. Next: unchanged-shape full py312 repeat.

[2026-11-08T19:18:33Z · sase-1rq.2.1.4.1.5.2--6] Complete py312 contention repeat jt48add3fpnw (SHA 11de7c8591, 60596 passed / 1 failed / 21 skipped in 4721s, 26 workers, CPUs 0-1): pytest FAILED tests/ace/tui/test_post_update_toast.py::test_post_update_toast_appears_once_and_suppresses_available_toast (wait_for notifications timed out after DEFAULT_WAIT_TIMEOUT 60s; 10s production toast UX timeout can expire during AcePage enter/pause under soak). Related beads sase-1s2/1s3/1s4/xo/1rf/1nf.10.1 did not recur. Peaks: cgroup 15.5G, soak rss 14.6G, soak swap 1.6G, oom_kill 0, pressure_memory_full 3.36, min_mem_available 14.1G, collected 26/26 (60617) tests 60617 done 1 failed. Repair: pin post_update_toast._TOAST_TIMEOUT_SECONDS to 3*LOAD_TOLERANT_TIMEOUT in the AcePage test (UX deadline, not the once-per-session suppression) and wait_for with that hang guard. Serial 22 passed; contended SASE_PYTEST_WORKERS=8 on CPUs 0-1: 64 passed (post-update toast 2.18s). sase tool run check 1efe1bdf78b995fc3b6b6cf39099da1a succeeded. Next: unchanged-shape full py312 repeat.

[2026-11-08T21:06:21Z · sase-1rq.2.1.4.1.5.2--7] Complete py312 contention repeat sgssd0zxfape (SHA 8f82a88607, 60596 passed / 1 failed / 21 skipped in 4643s, 26 workers, CPUs 0-1): pytest FAILED tests/ace/tui/test_commits_pane_collection.py::test_unlimited_commits_status_follows_backend_coverage_without_a_query_cap[above-old-default-cap] (status was preview; wait treated preview as exact because neither contains capped; collection apply re-canonicalized since:24h on the UI thread and missed the snapshot-worker query cache). Related beads sase-1s2/1s3/1s4/xo/1rf/1nf.10.1 did not recur. Peaks: cgroup 16.1G, soak rss 14.9G, soak swap 0.9G, oom_kill 0, pressure_memory_full 1.12, min_mem_available 19.1G, collected 26/26 (60617) tests 60617 done 1 failed. Repairs: _apply_result passes initial_query_result into _filtered_result so first paint does not re-query; wait_for requires status.content.plain == exact/capped; isolation test keeps exact when ArtifactQuerySession.result always misses. Serial 27 passed; contended SASE_PYTEST_WORKERS=8 on CPUs 0-1: 49 passed (above-old-default-cap 1.31s). sase tool run check 682cfec66e27f7d2e0e65cee95e20bc4 succeeded. Next: unchanged-shape full py312 repeat.

[2026-11-08T23:04:23Z · sase-1rq.2.

… and 4425 more characters

## Dependencies

- **Depends on:** [sase-1rq.2.1.4.1.5.1](sase-1rq.2.1.4.1.5.1.md) ✓ · ⧖ 2026-11-07
- **Blocks:** [sase-1rq.2.1.4.1.5.3](sase-1rq.2.1.4.1.5.3.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.2.1.4.1.5.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.1.4.1.5.2.md) | [sase-1rq.2.1.4.1.5.2](sase-1rq.2.1.4.1.5.2.md) | 10 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`dde1ada`](https://github.com/sase-org/sase/commit/dde1ada139e5698b8723b2166fab97d65d3d0f7c) | fix(test): isolate contention hang guards and nested soak records | [sase-1rq.2.1.4.1.5.2](sase-1rq.2.1.4.1.5.2.md) | 2026-11-08 04:31:55 EST |
| sase | [`2400e61`](https://github.com/sase-org/sase/commit/2400e61e938c0535ca3de61e83f63f698c8b25c2) | fix(test): keep contended TUI waits off the event loop | [sase-1rq.2.1.4.1.5.2](sase-1rq.2.1.4.1.5.2.md) | 2026-11-08 06:12:38 EST |
| sase | [`229f85a`](https://github.com/sase-org/sase/commit/229f85a998cb8fade8a4331f3ac4877b5104adf9) | fix(test): keep contended subprocess waits load-tolerant | [sase-1rq.2.1.4.1.5.2](sase-1rq.2.1.4.1.5.2.md) | 2026-11-08 08:33:25 EST |
| sase | [`6a6cc2b`](https://github.com/sase-org/sase/commit/6a6cc2b4268eb6c14f70d20f58d1a5e3cbc43580) | fix(test): keep contended nested and TUI waits load-tolerant | [sase-1rq.2.1.4.1.5.2](sase-1rq.2.1.4.1.5.2.md) | 2026-11-08 10:36:05 EST |
| sase | [`11de7c8`](https://github.com/sase-org/sase/commit/11de7c8591e506af66ae7029480e0e64a86011a0) | fix(test): bound TUI settle and zsh PTY waits under contention | [sase-1rq.2.1.4.1.5.2](sase-1rq.2.1.4.1.5.2.md) | 2026-11-08 12:40:57 EST |
| sase | [`8f82a88`](https://github.com/sase-org/sase/commit/8f82a88607750ed1c87156b0656220b30a96b19d) | fix(test): pin post-update toast timeout under contention | [sase-1rq.2.1.4.1.5.2](sase-1rq.2.1.4.1.5.2.md) | 2026-11-08 14:20:39 EST |
| sase | [`7190490`](https://github.com/sase-org/sase/commit/719049003053750ddf089d7eab53af5eee6a294c) | fix(tui): keep stitches first-paint coverage exact under contention | [sase-1rq.2.1.4.1.5.2](sase-1rq.2.1.4.1.5.2.md) | 2026-11-08 16:08:03 EST |
| sase | [`9c4cebe`](https://github.com/sase-org/sase/commit/9c4cebea9820b5917f9027f70aa2a0409edb6ba9) | fix: stabilize bump microbench and provider timer under contention | [sase-1rq.2.1.4.1.5.2](sase-1rq.2.1.4.1.5.2.md) | 2026-11-08 18:06:48 EST |
| sase | [`d1c6a2c`](https://github.com/sase-org/sase/commit/d1c6a2c10b3473020df6831b71d2d21096156a9f) | fix: skip same-key highlight echo and wait for group-kill reaping under contention | [sase-1rq.2.1.4.1.5.2](sase-1rq.2.1.4.1.5.2.md) | 2026-11-08 21:09:04 EST |
| sase | [`7a7ecd6`](https://github.com/sase-org/sase/commit/7a7ecd6885b32ea969d462881673e96d776a37d1) | fix(tui): return archive pulse Enter to inbox and drop paused stalls | [sase-1rq.2.1.4.1.5.2](sase-1rq.2.1.4.1.5.2.md) | 2026-11-09 00:09:40 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1rq.2.1.4.1.5.2--1][1] | Need remaining description, DECISIONS, and design after truncated first read | 2 |
| read-by | [agent:sase-1rq.2.1.4.1.5.2--2][1] | Need the phase scope, design file, notes, and DECISIONS after the y3mjfk red tally | 1 |
| read-by | [agent:sase-1rq.2.1.4.1.5.2--3][1] | Need the phase scope, design file, DECISIONS, and notes after complete red tally from monitor przd5aakw2gc | 1 |
| read-by | [agent:sase-1rq.2.1.4.1.5.2--4][1] | Need the phase scope, design file, DECISIONS, and notes | 1 |
| read-by | [agent:sase-1rq.2.1.4.1.5.2--5][1] | Need the phase scope, notes, and design file for the contention completion phase | 1 |
| read-by | [agent:sase-1rq.2.1.4.1.5.2--6][1] | Need the phase scope, design file, notes, and DECISIONS before inspecting this complete red tally | 1 |
| read-by | [agent:sase-1rq.2.1.4.1.5.2--7][1] | Need the phase scope, notes, and parent DECISIONS before repairing the latest contention failure | 1 |
| read-by | [agent:sase-1rq.2.1.4.1.5.2--8][1] | Need the phase scope, design file, DECISIONS, and notes before inspecting the red contention tally | 1 |
| read-by | [agent:sase-1rq.2.1.4.1.5.2--9][1] | Need the phase scope, notes, and design file before recording this red-tally inventory | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.1.4.1.5.2.md

<!-- sase:referenced-by:end -->
