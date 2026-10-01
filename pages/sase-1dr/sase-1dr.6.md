# Bead: sase-1dr.6 — Pager time axis and read view

[Bead Pages](../README.md) / [sase-1dr](README.md) / sase-1dr.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3o](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3o.md) · **Assignee:** `sase-1dr.6` · **Size:** large
**Created:** 2026-09-30 19:09:26 EDT · **Closed:** 2026-10-01 05:56:36 EDT
**Plan:** [202609/memory\_history.md](https://github.com/sase-org/sase--plans/blob/main/202609/memory_history.md)

## Description

pager-axis: create the temporary beta flag. Add a generic section-history provider seam to the pager and the memory provider. Add the history mixin with the `(` `)` `{` `}` keys, version-pinned sections and trail entries, scroll anchoring, neighbour prefetch, and generation-guarded workers. Add the read-view change gutter, the subject chip, and the past accent. Links in a past version resolve at that revision. The CLI opens this pager by default on a TTY.

## Notes

[2026-10-01T07:58:58Z · sase-1dr.6] Implemented pager-axis read view: memory_history beta flag (sase-1dv), generic pager/history seam with sase_pager_history entry point, memory provider with HistoryService-backed timelines/versions/compares and historical link resolution, ( ) { } stepping with generation guards and prefetch, version pins in sections and trail, version-safe syntax keys, read gutter marks with goto priority, past/dirty/tombstone subject chip and footer verbs, Time help group, history palette with contrast checks, pinned copy (<sha>:<path>) and live-path edit, selector CLI pager entry with TTY default. Tests: tests/pager/test_history_models.py and tests/memory/test_history_pager_provider.py (15 passed with focused lane); full pager lane 425 passed after updating syntax-key expectations in test_screen_syntax/test_syntax_activation. Interim boundaries: -d opens read view with notice (word-diff pager is sase-1dr.8); no-selector feed uses text path with notice (feed phase owns pager feed).

[2026-10-01T07:59:20Z · sase-1dr.6] PROPOSED FOLLOW-UP: symvision reports 4 unused public symbols in files untouched by this change (HandoffSubmitResult in src/sase/tool/handoff_launch.py, StarterResolution in src/sase/tool/starter.py, fit_next_word_ghost in src/sase/ace/tui/widgets/next_word_completion.py, owner_ref in src/sase/tool/owner.py). Evidence: SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop --epic-symbol sase-1dq(PromptPredictionWordCompletion) lists only those 4; git diff --name-only shows none of those files were modified by this phase. Needs isolated base-tree comparison to confirm pre-existing and a separate owner to fix or whitelist.

[2026-10-01T08:34:00Z · sase-1dr.6--1] Warm prefetched version-step latency (action-to-pin-settled, SASE_TUI_PERF=1 SASE_TUI_TRACE=1): p50=5.8ms p95=6.4ms max=7.2ms over 20 warm alternating v3<->now steps (first 4 discarded), target p95<=30ms met. Constraints: headless SasePager run_test (no real terminal paint), injected fake in-process provider (no git/file I/O), body+comparison caches warm via prefetch path; measures action dispatch through pin-settled, excludes physical key handling and final paint. Probe is scratch at /tmp/history_perf_probe.py, not committed. Launch phase owns final end-to-end performance verification.

[2026-10-01T08:48:26Z · sase-1dr.6--1] Verification results before final check. (1) mypy: fixed 3 NEW errors from the joined run (object->int casts in _chrome.py, PagerHistoryMixin _body/_body_width/_label_layer declarations, sections annotation in cli_history.py); mypy clean on all 4 touched files. (2) Found and fixed 2 phase-owned worker bugs missed by existing tests: history mixin called nonexistent Screen.call_from_thread (9 sites; pump-free tasks run on the app loop so UI updates are now direct calls) and _swap_active_section passed (index, anchor, replacement) to _restore_history_anchor(index, replacement, anchor); restore-to-now now sets a live pin instead of None. Regression test test_paren_keys_step_between_now_and_newest_committed added to tests/pager/test_app_history.py (passes). (3) New deterministic PNG goldens tests/pager/visual/test_history_png_snapshots.py: past/dirty/tombstone x 120x40+60x30 x dark+light = 12 goldens, fixture providers + fixed OIDs/dates; all 12 inspected and approved (PAST v2/3 chip + gutter add/change/removal marks, uncommitted chip, deleted chip + deletion banner; narrow widths truncate honestly). (4) Fixed stale identity-key waits in test_syntax_png_snapshots.py and test_agent_conversation_png_snapshots.py to _syntax_key_for_section (phase changed prepared/attempted keys to (identity, blob) tuples); pager visual --check: 42 passed, 0 updated/stale, no skipped/partial warnings. (5) Pager lane 428 passed; memory history lane 38 passed; ruff check+format clean. (6) Symvision re-run: only the 4 pre-existing symbols in untouched files (handoff_launch, starter, next_word_completion, owner); sase bead epic-symbols sase-1dr.6 clean and Justfile exemptions already removed. (7) Perf note recorded separately (p95 6.4ms vs 30ms target).

[2026-10-01T09:24:04Z · sase-1dr.6--2] Post-monitor verification (this turn). (1) Feature-flag schema drift fixed: registry added memory_history but src/sase/config/sase.schema.json was stale, so just check failed lint(feature flags); ran tools/sync_feature_flags_schema --write, check_feature_flags now exits 0. mypy clean on all touched files; ruff check clean; just fmt clean. (2) Entry point sase_pager_history.memory resolves in installed env. (3) Visuals: fix-tui-screenshots targeted on test_history_png_snapshots.py: 12 passed, status clean, unchanged=12, skipped=0, warnings=0; affected selectors (test_syntax_png_snapshots.py + test_agent_conversation_png_snapshots.py): 18 passed, clean. Inspected past/dirty/tombstone dark 120x40 plus past light 120x40 and past dark 60x30: PAST v2/3 chip + gutter marks, uncommitted chip, deleted chip + deletion banner all correct; remaining narrow/light variants pixel-verified by exact-match maintenance. (4) Unit lanes: tests/pager (non-visual) 428 passed; tests/memory 217 passed; focused history subset 56 passed. (5) Perf re-run corroborates note #3: SASE_TUI_PERF=1 SASE_TUI_TRACE=1 warm version-step p50=5.71ms p95=5.88ms max=6.0ms over 20 steps vs 30ms target. (6) Symvision: only the 4 pre-existing symbols in untouched files (per note #2); no epic-symbol entries for sase-1dr.6 (Justfile exemptions removed). Full sase tool run check (run e271b4737f8ed097dd567ba2b91d35e5) still in flight under host load; joined to verify monitor for close-out.

[2026-10-01T09:56:11Z · sase-1dr.6--3] PROPOSED FOLLOW-UP: 6 remaining joined-check NEW failures reproduce identically on the clean base tree (HEAD ebf070e16a, phase changes stashed) and are not pager-axis regressions. Base evidence: git stash push -u, then .venv/bin/python -m pytest tests/completion/test_snapshot.py tests/completion/test_kind_coverage.py tests/test_force_reuse_launch_seam_rejection.py tests/test_agent_artifact_directory_operation_audit.py tests/test_contract_manifest.py -q --continue-on-collection-errors -> 7 failed, 11 passed in 110s; tests/ace/tui/widgets/test_agent_header_panel.py fails collection on base too (ImportError: cannot import name test_hint_document_forces_expansion from test_agent_header_panel_basic). Items: (1) test_kind_coverage -- missing kind for (memory,history):at; --at was added by sase-1dr.5 (ebf070e16a), needs a ValueKind/choices/hint entry in src/sase/completion/kinds.py. (2-3) test_force_reuse_launch_seam_rejection x2 (launch seam, untouched by this phase). (4) test_agent_header_panel collection ImportError (TUI test import, untouched). (5) test_artifact_directory_operation_sites_are_reviewed -- extra unreviewed site src/sase/bead/attachments/lifecycle.py:quarantine_local_object. (6) test_contract_manifest_matches_marker_selection -- pytest -m contract --collect-only exits 2. Phase-owned completion-snapshot drift (--format default/help for the CLI pager entry) was fixed this turn via just sync-completion-spec (tests/completion/snapshots/cli_spec.json regenerated; both snapshot tests green). Joined run for reference: sase tool show e271b4737f8ed097dd567ba2b91d35e5.

[2026-10-01T09:56:36Z · sase-1dr.6--3] Done: pager-axis read view implemented (memory_history beta flag sase-1dv; generic pager/history seam with sase_pager_history entry point; HistoryService-backed memory provider with timelines/versions/compares and historical link resolution; ( ) { } stepping with generation guards and prefetch; version pins in sections and trail; version-safe syntax keys; read gutter marks with goto priority; past/dirty/tombstone subject chip and footer verbs; Time help group; history palette with contrast checks; pinned copy (<sha>:<path>) and live-path edit; selector CLI pager entry with TTY default; -d opens read view with notice, word-diff stays sase-1dr.8). Targeted: pager non-visual lane 428 passed, memory lane 217 passed, focused history subset 56 passed. Visual: 12 new deterministic PNG goldens (past/dirty/tombstone x 120x40+60x30 x dark+light, fixture providers, fixed OIDs/dates) all inspected and passing, skipped=0 warnings=0; affected selectors (syntax + agent-conversation) 18 passed. Perf: warm prefetched version-step p95 5.88ms vs 30ms target (SASE_TUI_PERF=1/SASE_TUI_TRACE=1, headless, fake provider, caches warm; see notes 3 and 5). Lint: ruff/mypy/fmt/feature-flags clean; symvision shows only the 4 pre-existing untouched-file symbols (note 2) and sase bead epic-symbols sase-1dr.6 is clean. Check: joined run e271b4737f8ed097dd567ba2b91d35e5 had 8 NEW scoped failures; 2 (completion snapshot x2, phase-owned --format drift) fixed via just sync-completion-spec; remaining 6 reproduce identically on the clean base tree and are recorded as PROPOSED FOLLOW-UP in note 6. Leaving epic sase-1dr, follow-on phases, and flag bead sase-1dv open.

## Dependencies

- **Depends on:** [sase-1dr.5](sase-1dr.5.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1dr.7](sase-1dr.7.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1dr.8](sase-1dr.8.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1dr.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1dr.6.md) | [sase-1dr.6](sase-1dr.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`92c6337`](https://github.com/sase-org/sase/commit/92c6337de85b89f42b15a481a474f84091139aeb) | feat(sase-1dr.6): pager time axis and read view with memory provider, plus completion snapshot sync | [sase-1dr.6](sase-1dr.6.md) | 2026-10-01 06:46:04 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1dr.5--1][1] | Check whether pager phase will consume history vocabulary labels and hidden-filtering | 1 |
| read-by | [agent:sase-1dr.6--3][2] | verify close-out state | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1dr.5.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1dr.6.md

<!-- sase:referenced-by:end -->
