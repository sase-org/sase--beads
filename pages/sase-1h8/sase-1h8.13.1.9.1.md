# Bead: sase-1h8.13.1.9.1 — Run the nine existing mutation suites in cached and replay modes

[Bead Pages](../README.md) / [sase-1h8.13.1.9](sase-1h8.13.1.9.md) / sase-1h8.13.1.9.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1h8.13.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.13.1.land.md) · **Assignee:** `sase-1h8.13.1.9.1` · **Size:** medium
**Created:** 2026-10-08 21:24:16 EDT · **Closed:** 2026-10-08 22:40:12 EDT
**Plan:** [202610/unify\_bead\_mutation\_algorithms.md](https://github.com/sase-org/sase--plans/blob/main/202610/unify_bead_mutation_algorithms.md)

## Description

suite-modes: make every test in the nine existing mutation suites run against both a git-backed cached store and a plain replay store, without macro_rules; assert cache equals replay after each cached mutating test; fix every parity defect this exposes in the try_cached_* algorithms with a regression test.

## Notes

[2026-10-09T02:40:12Z · sase-1h8.13.1.9.1] suite-modes done. Mechanism: thread-local dual-mode runner in mutation/tests/support.rs (all_store_modes, dual_tempdir, run_dual_mode_test, assert_dual_mode_parity_for_current_mode) with zero macro_rules; each wrapped test runs Cached then Replay on fresh temps, and the cached half asserts cache-path admission plus cache-equals-replay over every beads dir found under its temps. Per-mode coverage: 143 of 151 tests run in both modes (claims 9, close 21, create 16, delegation_remove 13, dependencies 7, links 17, notes 30 incl. 3 moved to new notes_attachments.rs, snooze 24, store 6); 8 stay replay-only with one-line comments (1 lock-contention, 3 concurrent, 2 corrupt-store, 1 legacy-migration, 1 load/save-cycle mechanics). Split notes_update.rs (1501->1415, 200 lines to notes_attachments.rs) and links.rs (3 tests to new links_projection.rs, 1377) to hold the 1500 cap. Parity defects in try_cached_*: none exposed, so no product change and no new regression test; only test files touched. Verify: just fmt ok; just fast ok zero warnings; just test bead::mutation 240 pass; bead::read_model 20 pass; bead_read_parity 16, bead_event_parity 35, bead_read_model_parity 6, bead_read_model_mutation_proof 2 pass; sase_core_py 297 pass; sase tool run check in sase-core succeeded exit 0. Cached-path evidence: dual_mode no-full-replay asserts plus warm-path suites unchanged and green.

## Dependencies

- **Blocks:** [sase-1h8.13.1.9.3](sase-1h8.13.1.9.3.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.13.1.9.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.9.1/README.md) | [sase-1h8.13.1.9.1](sase-1h8.13.1.9.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@ddafffd`](https://github.com/sase-org/sase-core/commit/ddafffd2be4ddb223d6eb767753283531795f939) | test(beads): run nine mutation suites in cached and replay modes | [sase-1h8.13.1.9.1](sase-1h8.13.1.9.1.md) | 2026-10-08 22:41:11 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1h8.13.1.9.1][1] | Need the phase scope and design file | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.9.1/README.md

<!-- sase:referenced-by:end -->
