# Bead: sase-1h8.13.1.9.3 — View-owned staging and one commit on both backings; create and notes unified

[Bead Pages](../README.md) / [sase-1h8.13.1.9](sase-1h8.13.1.9.md) / sase-1h8.13.1.9.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1h8.13.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.13.1.land.md) · **Assignee:** `sase-1h8.13.1.9.3` · **Size:** medium
**Created:** 2026-10-08 21:24:18 EDT · **Closed:** 2026-10-08 23:49:55 EDT
**Plan:** [202610/unify\_bead\_mutation\_algorithms.md](https://github.com/sase-org/sase--plans/blob/main/202610/unify_bead_mutation_algorithms.md)

## Description

view-commit: give MutationView config and event staging, lazy stream loading and a single commit on both backings (the replay commit keeps MutableStore::save semantics exactly), plus one runner that retries the same algorithm on the replay backing when the cached path declines before any append; run create and the notes family as single algorithms through it and delete their replay copies.

## Notes

[2026-10-09T03:49:36Z · sase-1h8.13.1.9.3] view-commit API for the three unify phases: run mutations with runner::run_mutation(beads_dir, name, |view| -> Result<MutationStep<BeadMutationOutcomeWire>, BeadError>); inside the closure use view.config()/config_mut(), view.stage_issue()/stage_removal(), view.stage_event(issue_id, op, payload, ts, actor) -> Ok(Some(event_id)) or Ok(None) for needs-replay decline, and view.commit(&expected_ids) -> Ok(Some(rows))/Ok(None). Return MutationStep::Done(outcome) or MutationStep::NeedsReplay. Caller must stage_issue before stage_event so stream routing sees the row; commit order follows expected_ids. Caveats: replay commit applies the overlay to the owned store in stage_order then calls exactly MutableStore::save; stage_event on replay mints straight into the owned tracked streams; backing_contains does one indexed COUNT(*) only when a cached stream file is missing; MutableStore::append_issue_event and append_note_to_store stay until the unify phases delete their last callers; store.rs next_child_id/max_top_level_counter/direct_child_counter/from_base36/next_top_level_counter deleted as newly unused

[2026-10-09T03:49:44Z · sase-1h8.13.1.9.3] PROPOSED FOLLOW-UP: tool_run::store::tests::private_argv_is_not_serialized_on_queries fails under the full sase tool run check lane but passes alone (same load-flake shape as sase-qr/sase-vt/sase-x1 beads); unrelated to view-commit, no existing flake bead found — needs a flake task bead

[2026-10-09T03:49:55Z · sase-1h8.13.1.9.3] view-commit done: MutationView owns config (loaded once on cached, owned MutableStore on replay), lazy stream staging, single stage_event minting, and one commit (cached keeps commit_staged_write semantics; replay applies overlay in stage order then exactly MutableStore::save); runner::run_mutation retries the same closure on the replay backing on pre-write decline and fails declines after a write or on replay as io bugs. create_issue, update_issues, append/edit/remove_issue_note run as single algorithms; their MutableStore replay copies plus edit_note_in_store/remove_note_from_store and 5 newly-unused store counter helpers deleted (append_note_to_store kept for plus_one_snooze/close_remove). Verified: just fmt, just fast, bead::mutation 243 pass incl replay_goldens byte-identical and dual-mode suites, bead::read_model 20 pass, parity/proof suites 35+2+6+16 pass, sase_core_py 297 pass, new tests/view_commit.rs 2 pass (legacy replay commit; decline-then-replay with saves==1 and full_replays==1). sase tool run check: 4728 pass with 1 unrelated load flake (private_argv passes alone, PROPOSED FOLLOW-UP recorded). epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1h8.13.1.9.1](sase-1h8.13.1.9.1.md) ✓ · ⧖ 2026-10-08
- **Depends on:** [sase-1h8.13.1.9.2](sase-1h8.13.1.9.2.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1h8.13.1.9.4](sase-1h8.13.1.9.4.md) ◐ · ⧖ 2026-10-08
- **Blocks:** [sase-1h8.13.1.9.5](sase-1h8.13.1.9.5.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1h8.13.1.9.6](sase-1h8.13.1.9.6.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.13.1.9.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.9.3/README.md) | [sase-1h8.13.1.9.3](sase-1h8.13.1.9.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@3cb24b0`](https://github.com/sase-org/sase-core/commit/3cb24b04ef4d89e723f616e9bb070b94cff25204) | feat(beads): unify create and notes mutations on one view commit | [sase-1h8.13.1.9.3](sase-1h8.13.1.9.3.md) | 2026-10-08 23:51:14 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1h8.13.1.9.3][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.9.3/README.md

<!-- sase:referenced-by:end -->
