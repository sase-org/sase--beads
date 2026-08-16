# Bead: sase-m6.6.1.5 — Migrate Stitches, Beads, Plans, Files, and provider panes

[Bead Pages](../README.md) / [sase-m6.6.1](sase-m6.6.1.md) / sase-m6.6.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m6.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.6.md) · **Assignee:** `sase-m6.6.1.5` · **Size:** large
**Created:** 2026-08-15 06:18:07 EDT · **Closed:** 2026-08-15 19:34:24 EDT
**Plan:** [202608/unified\_artifacts\_query\_1.md](https://github.com/sase-org/sase--plans/blob/main/202608/unified_artifacts_query_1.md)

## Description

flat_panes: configure the shared FilterBar and query engine from each ArtifactsPaneContract at boolean=false, migrate Stitches, Beads, Plans, Files and arbitrary ref providers while preserving their current tokens and canonical forms, derive free-text from searchable fields, generate completion/highlighting/facets from declared properties, add the shared host predicates, fix Files negation, and cache profiles and results by pane, snapshot generation, profile digest, and canonical query off the Textual event loop.

## Notes

[2026-08-15T13:12:14Z · sase-m6.6.1.5] Steps 1-3 of the 7-step plan (sase/repos/plans/202608/flat_pane_query_migration.md) are implemented, verified, and committed to master:
1. ArtifactsPaneContract now carries a real compiled CompiledQueryProfile (query_schema promoted from empty placeholder), included in presentation digest and explain output, covering healthy/degraded/built-in/synthetic-provider contracts.
2. New host facade src/sase/core/query_profile_corpus_facade.py wraps compile_corpus_with_profile / compile_query_with_profile / evaluate_many / parse_query_with_profile / canonicalize_query_with_profile with immutable ArtifactQueryIndex/ArtifactQueryResult records and an exact (pane_id, generation, profile_digest, canonical_query) cache key. Date literals resolve via the Python reference canonicalizer before Rust sees them.
3. Shared FilterBar widget is now instance-configurable from a compiled profile (key completions, static values, negation, repeatability, free-text hint, completion context).

Also fixed three real correctness bugs this wiring exposed in the already-closed sase-m6.6.1.2/.3 work (all now covered by tests, in both sase and the linked sase-core repo, committed to both):
- Rust's flat matcher always did exact-match on string fields (Patch-only assumption); added exact_match to the field schema (Rust + Python + wire + digest).
- Rust never implemented since/until date-range comparison (was plain string equality, silently zero matches).
- Python's flat canonicalizer fell back to boolean OR syntax for repeated same-key terms, which the flat-only Rust grammar can't parse.

Verified: just check passes clean (lint including symvision -- added --epic-symbol 'sase-m6.6.1.5(...)' whitelist entries in the Justfile for the new facade's symbols that steps 4-7 below will consume) and the full test-scoped suite, modulo two pre-existing flaky tests unrelated to this diff (independently investigated and routed: +1'd sase-lk with a fresh reproduction, and added a DISCOVERED ISSUE note to epic sase-j7 for test_procs_service.py::test_settlement_resumes_after_an_injected_crash).

NOT done -- steps 4-7 remain and this bead should stay in_progress:
4. Row adapters + off-thread index construction for Stitches, Beads, Plans, Files, and provider panes.
5. Migrate each pane's filter session (Stitches, Beads, Plans, Files) onto the shared parse/canonicalize/evaluate path, replacing their bespoke row matchers, while preserving session rollback/selection-restore/coverage/background-load behavior. Stitches does not use the shared ArtifactsSnapshotPane base and needs its own integration; Plans carries deep-archive coverage on top.
6. Enable negation for Files fields/free-text and the closed host predicate atoms, in both Rust and Python, with parity coverage.
7. Extend the Artifacts conformance harness and the artifacts-nav perf benchmark (tests/ace/tui/bench_artifacts_jk.py, which does not yet cover Beads or Files) to cover the migrated panes.

Left in_progress deliberately: closing this bead now would misrepresent an incomplete phase. Per sase_beads.md, sase bead work sase-m6.6.1 can reassign this phase to continue steps 4-7.

[2026-08-15T23:06:20Z · sase-m6.6.1.5] PROPOSED FOLLOW-UP: Stale compare_inventory_to_source epic-symbol — sase-m9.3.1.2 closed leaving compare_inventory_to_source test-only; just check failed with "bead sase-m9.3.1.2 is closed. Remove this stale --epic-symbol entry and clean up the symbol." Temporarily re-homed the whitelist to parent sase-m9.3.1 so this phase can verify. The owning proc-ownership epic should consume the symbol from a non-test caller or delete it and its tests.

[2026-08-15T23:13:54Z · sase-m6.6.1.5] Stabilization verified on current master + sase-core-rs 0.27.9: compiled-profile digest error is gone; Beads visual callers now use ArtifactEntryTarget; Commits visuals pin profile_reference_support.normalize_reference_time; sidecar completion sentinel uses the profile hint; inspected and accepted 6 Artifacts PNG goldens (profile-driven FilterBar hints/order and shared-shell footer separators). Focused facade/conformance/session/filter/nav tests passed. Artifacts j/k bench p95 all under 16ms including Beads and Files (worst stitches.next 9.72ms). just check passed (lint including re-homed sase-m6.6.1(canonicalize_artifact_query); scoped tests escalated on justfile/core-identity-changed). Remaining: just check-full via monitor, then close only this bead.

[2026-08-15T23:33:41Z · sase-m6.6.1.5--1] PROPOSED FOLLOW-UP: Models panel default-effort row flake — just check-full failed only tests/test_models_panel_effort.py::test_panel_title_and_chooser_show_effective_and_configured_values (1 failed, 30558 passed). The setting:default_effort row still showed the initial empty snapshot ('provider default' twice) instead of '@ medium' / 'override · 42m left'. Isolated re-run passed. The panel starts with configured_effort=None and applies the patched snapshot from a thread worker after one pilot.pause(); under full-suite load that pause can miss the worker. Unrelated to this phase; belongs to sase-mf / in-progress sase-mf.4 (Models redesign coverage).

[2026-08-15T23:34:24Z · sase-m6.6.1.5--1] Stabilization verified on current master + sase-core-rs 0.27.9: compiled-profile digest/floor error is gone; Beads visual callers use ArtifactEntryTarget; Commits fixtures pin profile_reference_support.normalize_reference_time; sidecar sentinel waits for the profile hint; inspected and accepted 6 Artifacts PNG goldens (profile-driven FilterBar descriptions/order + shared-shell footer separators). Focused facade/conformance/session/filter/nav tests passed. bench_artifacts_jk.py p95 all <16ms including Beads and Files (worst stitches.next 9.72ms). just check passed (including re-homed epic-symbols). just check-full lint/validation passed; test-cost was 1 failed / 30558 passed / 10 skipped — only unrelated Models-panel flake test_panel_title_and_chooser_show_effective_and_configured_values (isolated re-run passed; recorded as PROPOSED FOLLOW-UP). Remaining check-full flake-baseline gate also passed. Did not close sase-m6.6.1, sase-m6.6, or any other bead.

[2026-08-15T23:36:34Z · sase-m6.6.1.5--1] Verified the landed flat-pane query migration against current master: sase-core-rs 0.27.9 resolved the compiled-profile digest error; Beads visual callers use typed ArtifactEntryTarget; Commits fixtures pin profile_reference_support.normalize_reference_time; sidecar sentinel waits for include sidecar repositories; six inspected Artifacts PNG goldens accepted (profile-driven FilterBar descriptions/order and shared-shell footer separators); focused facade/conformance/session/filter/nav tests passed; bench_artifacts_jk.py p95 all under 16ms (worst stitches.next 9.72ms); just check passed; just check-full lint and validation passed with 30558 passed / 10 skipped. The only check-full failure is the unrelated Models-panel flake tests/test_models_panel_effort.py::test_panel_title_and_chooser_show_effective_and_configured_values, recorded as PROPOSED FOLLOW-UP. Stale --epic-symbol canonicalize_artifact_query re-homed to sase-m6.6.1; compare_inventory_to_source re-homed to sase-m9.3.1 (also noted as follow-up).

## Dependencies

- **Depends on:** [sase-m6.6.1.2](sase-m6.6.1.2.md) ✓ · ⧖ 2026-08-15
- **Depends on:** [sase-m6.6.1.3](sase-m6.6.1.3.md) ✓ · ⧖ 2026-08-15
- **Depends on:** [sase-m6.6.1.4](sase-m6.6.1.4.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-m6.6.1.6](sase-m6.6.1.6.md) ✓ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m6.6.1.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.6.1.5.md) | [sase-m6.6.1.5](sase-m6.6.1.5.md) | 3 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`545cb8e`](https://github.com/sase-org/sase/commit/545cb8e7055c61a81773c424a94a73386aa131db) | feat(query): wire the compiled query profile into contracts, host facade, and FilterBar | [sase-m6.6.1.5](sase-m6.6.1.5.md) | 2026-08-15 09:08:39 EDT |
| sase-core | [`sase-core@f898057`](https://github.com/sase-org/sase-core/commit/f8980573b24217d227a9931617443ceec0ceb302) | fix(query): correct exact-match, date-range, and digest handling in the profile engine | [sase-m6.6.1.5](sase-m6.6.1.5.md) | 2026-08-15 09:10:43 EDT |
| sase | [`e4c6460`](https://github.com/sase-org/sase/commit/e4c64607f693552d3101bd1d130c3c76680f6e7f) | test(ace): align flat-pane visual fixtures with query profiles | [sase-m6.6.1.5](sase-m6.6.1.5.md) | 2026-08-15 19:38:20 EDT |
