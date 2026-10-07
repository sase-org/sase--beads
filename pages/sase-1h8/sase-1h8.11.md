# Bead: sase-1h8.11 — issues.jsonl off the per-mutation path

[Bead Pages](../README.md) / [sase-1h8](README.md) / sase-1h8.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3u.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3u.linker.w0.md) · **Assignee:** `sase-1h8.11` · **Size:** medium
**Created:** 2026-10-06 18:59:43 EDT · **Closed:** 2026-10-07 13:58:03 EDT
**Plan:** [202610/bead\_store\_history\_independent\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202610/bead_store_history_independent_performance.md)

## Description

projection-off: stop rewriting and committing issues.jsonl on every mutation, untrack it with a mixed-version-safe migration, migrate its content consumers, and add on-demand export.

## Notes

[2026-10-07T17:56:43Z · sase-1h8.11] PROPOSED FOLLOW-UP: Fix 3 fast-path tests broken by sase-1h8.7 — _ALWAYS_DEFERRED_VERBS defers +1 so test_fast_path_guards_mutations_but_not_reads cannot raise, and the stem-probe resolution bypasses the resolve_beads_location patch in the two rm-refusal tests; fails identically with sase-1h8.11 fast-path delta reverted (commit b0687d0180)

[2026-10-07T17:57:00Z · sase-1h8.11] PROPOSED FOLLOW-UP: Raise or ratchet the TUI import budget — test_tui_app_import_stays_under_startup_budget fails 3570 < 3570 with zero contribution from sase-1h8.11 (no new modules in the tui import graph; all new imports are lazy or stdlib)

[2026-10-07T17:57:06Z · sase-1h8.11] PROPOSED FOLLOW-UP: Fix test_post_dispatch_foreign_race_on_external_is_exempt — fails standalone with sase-1h8.11 finalizer files reverted; stitch-resume push guard trips on a foreign commit race the test declares exempt, no bead store involved

[2026-10-07T17:57:16Z · sase-1h8.11] PROPOSED FOLLOW-UP: Repair sase-core HEAD gate (cargo fmt --check diffs in agent_launch/typed_units.rs and macro_lsp completion tests, plus editor_completion directive_contract test failure) — all reproduce on a clean HEAD worktree, blocking sase-core just check independently of sase-1h8.11

[2026-10-07T17:58:03Z · sase-1h8.11] projection-off done: core save skips issues.jsonl rewrite for event stores (legacy unchanged); new bead_referenced_artifact_ids + binding; protection/mirror/resolver migrated to canonical reads; unlink-only migration + on-demand sase bead export -o. Verified: sase_core bead tests 512 pass; tests/test_bead 2689 pass; targeted 190 pass; ruff/mypy clean; live 7k-bead store: export byte-identical to committed projection in 2.8s, first new-code note committed migration (.gitignore rule + D issues.jsonl + stream only), read-model verify matches replay (7067). 5 pre-existing failures filed as PROPOSED FOLLOW-UP (fast-path x3 from 1h8.7, tui import budget boundary, finalizers race, sase-core fmt+editor test). UNCOMMITTED in sase + sase-core; land flow must commit core then just ratchet-core-revision.

## Dependencies

- **Blocks:** [sase-1h8.13](sase-1h8.13.md) ◐ · ⧖ 2026-10-06
- **Depends on:** [sase-1h8.5](sase-1h8.5.md) ✓ · ⧖ 2026-10-06
- **Depends on:** [sase-1h8.7](sase-1h8.7.md) ✓ · ⧖ 2026-10-06
- **Depends on:** [sase-1h8.8](sase-1h8.8.md) ✓ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.11/README.md) | [sase-1h8.11](sase-1h8.11.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@7df86f4`](https://github.com/sase-org/sase-core/commit/7df86f4a3ae3aa677386d875d3fc5a1f348c376c) | feat(bead): skip projection rewrite on event-store save; add referenced-artifact-ids query (sase-1h8.11) | [sase-1h8.11](sase-1h8.11.md) | 2026-10-07 14:00:07 EDT |
| sase | [`ee00218`](https://github.com/sase-org/sase/commit/ee0021821fa3adf8401ea725967e1414682432d0) | feat(bead): take issues.jsonl off the per-mutation path (sase-1h8.11) | [sase-1h8.11](sase-1h8.11.md) | 2026-10-07 14:52:27 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.3y.grk][1] | Need 1h8 phase statuses that overlap sase-1h5 Beads-pane work | 1 |
| read-by | [agent:sase-1h8.11][2] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3y.grk/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.11/README.md

<!-- sase:referenced-by:end -->
