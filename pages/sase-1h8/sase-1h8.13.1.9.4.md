# Bead: sase-1h8.13.1.9.4 — Open, close and remove as single view algorithms

[Bead Pages](../README.md) / [sase-1h8.13.1.9](sase-1h8.13.1.9.md) / sase-1h8.13.1.9.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1h8.13.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.13.1.land.md) · **Assignee:** `sase-1h8.13.1.9.4` · **Size:** medium
**Created:** 2026-10-08 21:24:19 EDT · **Closed:** 2026-10-09 01:17:42 EDT
**Plan:** [202610/unify\_bead\_mutation\_algorithms.md](https://github.com/sase-org/sase--plans/blob/main/202610/unify_bead_mutation_algorithms.md)

## Description

unify-lifecycle: run open, close, close-with-note and remove through the view-commit runner on both backings, and delete the close_remove.rs replay copies and its family stream-slot helper; suites and goldens stay green.

## Notes

[2026-10-09T05:17:28Z · sase-1h8.13.1.9.4] PROPOSED FOLLOW-UP: replay_goldens pins wall-clock lock_wait_ms and flakes under parallel load (0ms vs pinned 1-15ms, scenarios vary run to run; passes alone and on rerun) — normalize or drop lock_wait_ms from the golden outcome comparison. Evidence: sase-core bead::mutation runs 2026-10-09, run 5a1d7f29 gate green.

[2026-10-09T05:17:42Z · sase-1h8.13.1.9.4] unify-lifecycle done: open_issue, close_issues, close_issues_with_note, remove_issues/remove_issue now run as single view algorithms through run_mutation with stage_event + one view.commit on both backings. Deleted the MutableStore replay copies, lifecycle_stream_slot, CachedCloseBatch/Event, cached_close_one helper, store close_one/close_one replay helpers and the store-version reopen helper; kept reject_unclosed_descendants_in_batch (+its helpers, still used by notes_update) and append_note_to_store (still used by plus_one_snooze). close_remove.rs 1425->827 lines. Verified: just fmt clean; just fast zero warnings; bead::mutation 243 passed; bead::read_model 20 passed; bead_read_parity 35 + bead_event_parity 16 passed; bead_read_model_mutation_proof 2 passed; bead_read_model_parity sequence test passes on branch (420s vs 388s base); sase_core_py 297 passed; sase tool run check gate succeeded exit=0 (run 5a1d7f29). One load flake seen twice (golden lock_wait_ms 0 vs pinned, varying scenarios incl. untouched notes family; passes alone/rerun, base full-suite green) recorded as PROPOSED FOLLOW-UP. epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1h8.13.1.9.3](sase-1h8.13.1.9.3.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1h8.13.1.9.8](sase-1h8.13.1.9.8.md) ✓ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.13.1.9.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.9.4/README.md) | [sase-1h8.13.1.9.4](sase-1h8.13.1.9.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@e92f7f8`](https://github.com/sase-org/sase-core/commit/e92f7f83ebd72baee07dd622ef82e2adb41e8b6f) | feat(beads): unify open, close and remove mutations on one view commit | [sase-1h8.13.1.9.4](sase-1h8.13.1.9.4.md) | 2026-10-09 01:18:50 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1h8.13.1.9.4][1] | check phase notes and remaining work | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.9.4/README.md

<!-- sase:referenced-by:end -->
