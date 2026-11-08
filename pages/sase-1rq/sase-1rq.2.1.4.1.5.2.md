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

## Dependencies

- **Depends on:** [sase-1rq.2.1.4.1.5.1](sase-1rq.2.1.4.1.5.1.md) ✓ · ⧖ 2026-11-07
- **Blocks:** [sase-1rq.2.1.4.1.5.3](sase-1rq.2.1.4.1.5.3.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.2.1.4.1.5.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.1.4.1.5.2.md) | [sase-1rq.2.1.4.1.5.2](sase-1rq.2.1.4.1.5.2.md) | 3 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`dde1ada`](https://github.com/sase-org/sase/commit/dde1ada139e5698b8723b2166fab97d65d3d0f7c) | fix(test): isolate contention hang guards and nested soak records | [sase-1rq.2.1.4.1.5.2](sase-1rq.2.1.4.1.5.2.md) | 2026-11-08 04:31:55 EST |
| sase | [`2400e61`](https://github.com/sase-org/sase/commit/2400e61e938c0535ca3de61e83f63f698c8b25c2) | fix(test): keep contended TUI waits off the event loop | [sase-1rq.2.1.4.1.5.2](sase-1rq.2.1.4.1.5.2.md) | 2026-11-08 06:12:38 EST |
| sase | [`229f85a`](https://github.com/sase-org/sase/commit/229f85a998cb8fade8a4331f3ac4877b5104adf9) | fix(test): keep contended subprocess waits load-tolerant | [sase-1rq.2.1.4.1.5.2](sase-1rq.2.1.4.1.5.2.md) | 2026-11-08 08:33:25 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1rq.2.1.4.1.5.2--1][1] | Need remaining description, DECISIONS, and design after truncated first read | 2 |
| read-by | [agent:sase-1rq.2.1.4.1.5.2--2][1] | Need the phase scope, design file, notes, and DECISIONS after the y3mjfk red tally | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.1.4.1.5.2.md

<!-- sase:referenced-by:end -->
