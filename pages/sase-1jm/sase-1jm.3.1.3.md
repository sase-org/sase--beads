# Bead: sase-1jm.3.1.3 — Paged Archive list and live Inbox pulse

[Bead Pages](../README.md) / [sase-1jm.3.1](sase-1jm.3.1.md) / sase-1jm.3.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.3.md) · **Assignee:** `sase-1jm.3.1.3` · **Size:** medium
**Created:** 2026-10-10 20:21:21 EDT · **Closed:** 2026-10-11 01:06:54 EDT
**Plan:** [202610/agents\_archive\_view\_phase.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view_phase.md)

## Description

archive-column: lazily mount an Archive column beside the mounted Inbox column, containing a selectable Inbox pulse and an OptionList-style Archive list. Render core light rows, date banners, containers, and banner-local pages of 100 rows; add j/k/g/G/h/l and J/K navigation, echo guards, responsive columns, and truthful past-tense outcomes and time chips. Keep all Archive navigation state separate from Inbox state.

## Notes

[2026-10-11T05:06:24Z · sase-1jm.3.1.3] Archive-column contracts for later phases. List keys: run = user.machine@run (index agent_id), container:<container_key>, banner:<banner_key>, tail:<banner_key>; ArchiveViewState.selected_key now holds the highlighted item of ANY kind (is_archive_row_key tells runs/containers from banners/tails); new state fields folded_banners (explicit fold overrides; expanded_banners holds explicit opens) and reveal_row (exact-arrival row, walked into view by opening its banner, paging, then expanding its container). get_agents_tab_selection: row_kind agent|container|none (banner, tail, loading, focused pulse => none) plus light_row; archive_read_only_context is None for non-run items. Key routing: route_archive_key(owner, INTENT_*) in _archive_view is called first by action_next_patch/prev_patch (j k), scroll_to_top/bottom (g G), expand_or_layout/hooks_or_collapse (l h), focus_next/prev_agent_panel (J K, one switch), act_on_agent (Enter); Archive navigation clamps (no wrap). Column code lives in _archive_column.py (state/plan/paint/chrome; public column_archive/column_runtime/column_widget/refresh_column/schedule_detail/sync_archive_chrome/archive_light_row/archive_container_members) and _archive_column_nav.py; widgets in widgets/agents_archive/. Detail seam for 3.1.5: _paint_detail_placeholder in _archive_column.py (debounced through schedule_detail with the DetailOwnership token); it currently just calls AgentDetail.show_empty(). Query/grouping changes (3.1.4) must call request_archive_view_load after changing ArchiveViewState; the column plans windows from the held summary only when snapshot.applied_query/grouping match committed_query/grouping. open/close_agents_archive_view now call sync_archive_chrome (lazy mount, #agents-content.-archive-active toggles #agent-list-container vs #archive-column; Inbox widgets stay mounted). Pulse: attention = Inbox header asking(stopped) count via _agent_info_metrics; updated live through refresh_archive_inbox_pulse without touching the list or detail debounce.

[2026-10-11T05:06:29Z · sase-1jm.3.1.3] Fixed a phase-2 integration bug found with the real corpus: the controller passed the committed query (in:archive) straight to corpus.summary/rows/count, which the Rust-backed profile rejects (summary silently None); _archive_controller_build._query_handle now strips the host in: scope via extract_scope first (CLI parity), and the column paints "Archive results unavailable" instead of a blank list when a summary cannot be produced. Controller row_identity now delegates to archive_row_key (container/key-triple aware; legacy name rows unchanged).

[2026-10-11T05:06:33Z · sase-1jm.3.1.3] PROPOSED FOLLOW-UP: six failures reproduce identically on the clean HEAD tree (git worktree of HEAD, PYTHONPATH=worktree/src) and are not caused by this phase: tests/ace/tui/test_app_import_budget.py (module count 3516 vs cap 3513 on base; this phase adds zero modules to the app import, guarded by tests/ace/tui/test_agent_archive_column_lazy.py), tests/test_agent_artifact_marker_path_passing_audit.py (axe/run_agent_directive_metadata_preserved.py:session_root_tab), tests/completion/test_snapshot.py x2 (CLI completion spec drift), tests/completion/test_candidates_providers.py::test_flag_candidates_come_from_the_in_process_registry, tests/test_file_hook_dispatch_regression.py::test_bob_dry_run_canonical_report_has_no_digest_suffix; sase tool run check ids fcd4ecedcc5d417c907cdcadf7bd47b7 and 93bd8f2c4dbd8f2fac9c3ab4ab4cd306 (three more load flakes in the second run passed in isolation: test_launch_context_bar full_cluster, test_provider_drain_e2e, test_settlement_retention sigterm)

[2026-10-11T05:06:38Z · sase-1jm.3.1.3] Verified: 122 new/related archive tests pass three times in a row (list model incl. page boundaries with expanded members, rendering/widgets with echo guards and resize refit, glue against a Rust-contract model corpus, real Rust corpus for roots/containers/expanded rows/timezone/scope, mounted AceApp key routing and clicks); ruff, mypy, symvision (only KNOWN update_failure_geometry/project_for_done), test-waits, flags, toobig clean; visually inspected SVG->PNG renders at 160x40 and 100x28 (open banners, pulse focus, WAS RUNNING violet, start-only italic time, container glyph/count, model/runtime drop, middle-truncated names). sase bead epic-symbols sase-1jm.3.1.3 has no leftovers (re-keyed archive_corpus_is_warm to sase-1jm, whitelisted archive_container_members and agents_view_is_archive under sase-1jm.3.1).

[2026-10-11T05:06:54Z · sase-1jm.3.1.3] Archive column implemented: lazily mounted #archive-column beside the mounted Inbox column (class toggle, Inbox widgets stay mounted); live Inbox pulse via format_agent_count_chip; OptionList-style list rendering core light rows with date banners (Today/Yesterday/last-week days/weeks/months via BY_DATE label helpers), containers and banner-local pages of 100 with exact ⋮ N more tails (root counts vs expanded member rows); j/k/g/G/h/l/J/K/Enter/click routing with echo guards, clamped navigation and responsive MODEL/RUNTIME drop; truthful past-tense outcomes and core-basis time chips; all state on ArchiveViewState, Inbox untouched. Fixed phase-2 bug: in: scope is now stripped before corpus calls (real corpus rejected in:archive). Verified: 122 archive tests x3 stable (model, widgets, glue vs Rust-contract corpus, real Rust corpus, mounted AceApp), ruff/mypy/symvision/test-waits/flags clean except KNOWN, inspected SVG->PNG renders; sase tool run check ran the full lane with only clean-base-reproducing failures (6) plus three load flakes that pass in isolation, recorded as PROPOSED FOLLOW-UP; zero modules added to the TUI app import.

## Dependencies

- **Depends on:** [sase-1jm.3.1.2](sase-1jm.3.1.2.md) ✓ · ⧖ 2026-10-10
- **Blocks:** [sase-1jm.3.1.4](sase-1jm.3.1.4.md) ✓ · ⧖ 2026-10-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.3.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.3/README.md) | [sase-1jm.3.1.3](sase-1jm.3.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b6acacf`](https://github.com/sase-org/sase/commit/b6acacfa082643fa298e217b9159256acc40b5ba) | feat(tui): add paged Archive list column and live Inbox pulse | [sase-1jm.3.1.3](sase-1jm.3.1.3.md) | 2026-10-11 01:08:10 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jm.3.1.3][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.3/README.md

<!-- sase:referenced-by:end -->
