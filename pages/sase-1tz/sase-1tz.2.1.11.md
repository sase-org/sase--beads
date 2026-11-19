# Bead: sase-1tz.2.1.11 — Move sampled synchronous filesystem work off the TUI main thread

[Bead Pages](../README.md) / [sase-1tz.2.1](sase-1tz.2.1.md) / sase-1tz.2.1.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.md) · **Assignee:** `sase-1tz.2.1.11` · **Size:** medium
**Created:** 2026-11-19 11:13:28 EST · **Closed:** 2026-11-19 14:53:20 EST
**Plan:** [202611/noise\_publication\_digests\_tui\_stalls.md](https://github.com/sase-org/sase--plans/blob/main/202611/noise_publication_digests_tui_stalls.md)

## Description

ui_io_offload: move the launchable-MRU tick's stat and config-token peek, the hijack roster's per-row realpath, and project-record listing behind pump-free workers or freshness-token caches. This is the separate fix for apollo's low-GC blocking-I/O stalls.

## Notes

[2026-11-19T19:52:20Z · sase-1tz.2.1.11] PROPOSED FOLLOW-UP: Agents apply still stats artifact paths per live agent on the UI thread — rearm_live_agent_watch_coverage (_live_watch_coverage.py) runs inside _apply_loaded_agents_prepared and calls Agent.get_artifacts_dir -> _get_artifacts_dir_uncached (Rust resolve_agent_artifact_timestamp_path + Path.is_dir) per agent. The alias-map part (apollo n=144, max 11.1 s) is now memory-only in the TUI, but the path stats remain (apollo: 128 low-GC samples on this chain, _get_artifacts_dir_uncached innermost n=23, max 4.4 s). Precompute watch dirs in the loader worker or memoize in _PreparedApplyData.

[2026-11-19T19:52:37Z · sase-1tz.2.1.11] PROPOSED FOLLOW-UP: LaunchContextSource._tick (widgets/launch_context_source.py:260-300) still runs peek_current_project_change_token, peek_launch_default_change_token, and peek_active_temporary_override on the UI thread each tick, and _schedule_project_resolution_if_needed peeks again. Apollo low-GC samples show launch_context_source _broadcast n=7 and a 71.7 s pump hitch in load_active_overrides via usage_attention_enabled. Move these peeks into a single-flight pump-free task like _launchable_mru_tick now does.

[2026-11-19T19:52:44Z · sase-1tz.2.1.11] PROPOSED FOLLOW-UP: ToolRunsPaneShellMixin.__init__ (modals/tool_runs_pane_shell.py:115) calls _resolve_scope_project -> resolve_current_project() synchronously on the UI thread when opened without a project (list_project_records, workspace is_dir per record, find_all_patches_cached). Apollo sampled 0 stalls there, but it is user-initiated main-thread I/O; resolve it in a worker like the other current-project callers.

[2026-11-19T19:52:51Z · sase-1tz.2.1.11] PROPOSED FOLLOW-UP: evidence for existing task sase-1s4 (test leaves a stale lock in the real checkout) — during this phase a zero-byte .git/index.lock appeared in the sase_16 checkout twice with no git process alive: 2026-11-19 13:46 EST mid sase tool run check (full lane escalation) and 14:29:58 EST during pytest -m slow tests/ace/tui/bench_tui_jk.py. Both broke git stash with "could not write index"; removed by hand after confirming no holder.

[2026-11-19T19:53:01Z · sase-1tz.2.1.11] PROPOSED FOLLOW-UP: base-tree check failure, not from this phase — tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed fails identically on clean base c756511c11 with unreviewed site src/sase/agents_sync/publication_scratch.py:sweep_publication_scratch (added by the pub_cleanup work). The epic land agent should get it reviewed into the audit allowlist. Also seen in the same full lane: test_bare_git_init::test_git_runner_removes_persistent_index_lock_after_retries failed once under load (79 s) and passes in isolation; the KNOWN failures were test_macro_terminology, agents_sync drain_accounting cleanup_after_success, and fakey gate_capacity_custom_e2e.

[2026-11-19T19:53:20Z · sase-1tz.2.1.11] ui_io_offload done. (1) _launchable_mru_tick now only schedules a single-flight pump-free peek; peek_current_project_change_token (MRU stat + config token) runs via asyncio.to_thread and the decision re-reads snapshot state after the await. (2) hijack_row_local_deps copies row fields only; the artifacts-dir index (per-row Path.resolve) is built lazily on first find_session_by_member_artifact_dir, i.e. on the hijack-decision worker. (3) Tick-managed alias-map cache in _project_display_cache: _run_ace_app opts the TUI in; load_project_alias_map/resolve_project_alias_ref serve a memory-only map; refresh_project_display_snapshot revalidates or prewarms it with the same ProjectSpec freshness token and record load; invalidate_project_display_snapshot and alias mutations drop it; CLI processes still load fresh every call. Hot caller confirmed from apollo stall stacks: rearm_live_agent_watch_coverage -> Agent.get_artifacts_dir -> resolve_project_alias_ref. Tests: tests/_main_thread_fs_guard.py (fails os.stat/lstat/scandir/Path.resolve on the main thread) plus test_launchable_mru (3 new/updated), test_agent_hijack_roster_offload (2), test_project_alias_map_tick_cache (10), and test_ace_handler scope test; the guard tests fail on the old code (negative controls run). sase tool run check dd0fd741: every lint gate passes; full test lane 62160 passed, 5 failed: 3 KNOWN, the artifact-dir audit reproduces on clean base (publication_scratch.py), bare_git index-lock test passes in isolation. bench_tui_jk under load avg 33-48: the failing budget/stall nodes fail the same way on the clean base (7 of 9 failed on base); archive warm-open flips 99.4/115.6 ms on the same tree. Apollo before-numbers and the after-install command are recorded on sase-1tz.2.

## Dependencies

- **Blocks:** [sase-1tz.2.1.13](sase-1tz.2.1.13.md) ◐ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.2.1.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.11/README.md) | [sase-1tz.2.1.11](sase-1tz.2.1.11.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.2.1.11][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.11/README.md

<!-- sase:referenced-by:end -->
