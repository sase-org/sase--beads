# Bead: sase-pv.7 — Migrate the five live flag beads

[Bead Pages](../README.md) / [sase-pv](README.md) / sase-pv.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.06a](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.06a.md) · **Assignee:** `sase-pv.7` · **Size:** medium
**Created:** 2026-08-18 11:26:06 EDT · **Closed:** 2026-08-18 18:29:19 EDT
**Plan:** [202608/flag\_task\_type.md](https://github.com/sase-org/sase--plans/blob/main/202608/flag_task_type.md)

## Description

migrate: rewrite the five existing flag bead event streams in place into typed task beads with hand-authored field values, then regenerate the projection, the mirror, and the pages.

## Notes

[2026-08-18T20:30:49Z · sase-pv.7] BLOCKED: the plan's in-place event rewrite (rewrite issue_created payload issue_type flag->task + re-mint event_id, per the migrate phase text) is rejected by the bead stores own append-only integrity guard (sase.bead._stream_integrity.prepare_event_streams_for_commit / analyze_stream_against_ancestor, called from _commit_bead_state on every sase bead commit). That guard diffs local vs ancestor by event_id: an edited event either (a) keeps its old event_id -> classified "rewrite", reverted to ancestor + BeadStreamIntegrityError raised, or (b) gets a new event_id (re-minted, as the plan instructs) -> the old id is now "missing" from local, so the guard "restores" it by prepending the original ancestor event back, corrupting the stream into two issue_created events for one bead. I verified this live: staging the correctly-migrated event content for all 5 beads and running any sase bead commit (note/close/pages refresh) never actually committed the rewritten event-stream files across 13 attempts; a direct call to prepare_event_streams_for_commit confirmed the restore-superset corruption on all 5 files. There is no --force/bypass flag for this guard anywhere in the CLI, and no BeadIssueUpdateEventFieldsWire field exists for issue_type or task_type (only task_type_fields values, e.g. remove_by_date/remove_by_release via -b/--remove-by, are updatable post-creation) -- so issue_type is architecturally immutable after issue_created through every sanctioned mutation path. I fully reverted all exploratory changes: the beads-store workspace clone (sase/repos/beads) is hard-reset to origin/main, the canonical checkout at /home/bryan/projects/github/sase-org/sase/sase/repos/beads is untouched, and the linked sase-core checkout is clean (a temporary Rust unit test used only to discover/confirm this finding was reverted, never committed). No data was changed; the 5 flag beads are still issue_type=flag. This phase needs a design revision from the epic owner: either (a) a real, no-workaround mechanism for changing issue_type is added to sase-core (a new event/mutation with matching integrity-guard support, which is Rust core work outside D9's slug/retire boundary), or (b) the migrate phase is redesigned around close-old-create-new despite the plan's D-section rejecting that approach, or (c) some other route the epic owner prefers. Recommend the epic owner revisit the migrate phase design before this is reattempted.

[2026-08-18T22:28:46Z · sase-pv.7.f0] PROPOSED FOLLOW-UP: `just check` is red on master for every agent — `tests/_suite_gate.py` is 1197 lines and `_lint-toobig`'s hard limit is 1000, so the `lint (toobig)` gate fails before the test lane runs. Pre-existing and unrelated to this epic: the file is unmodified in my tree and last changed by f7e6acbf6 "fix(tests): reclaim wedged suite-gate worker-token grants". Fix is to split it, the same way sase split `snooze_gate.py` in 530c574d2.

[2026-08-18T22:29:19Z · sase-pv.7.f0] @/tmp/notes/close.txt

[2026-08-18T22:50:19Z · 070] RECOVERED: the note above this one was stored as the literal token `@/tmp/notes/close.txt` because `sase bead close -n` did not expand `@<path>`. This is that file's contents.

Migrated the five live flag beads by the owner-directed create-new + delete-old route, replacing the plan's in-place event-stream rewrite (which the store's append-only guard makes impossible; see this bead's BLOCKED note). Each old bead was removed with `sase bead rm` and re-created through `create_flag_bead` -- the path `sase flag new` uses -- preserving title, size, kind and both removal thresholds exactly: sase-nw->sase-qe, sase-nx->sase-qf, sase-om->sase-qg, sase-pa->sase-qh, sase-pk->sase-qi. Each new bead carries a PROVENANCE note naming the bead it replaces. `when_enabled`/`when_disabled`/`remove_when` are the plan's drafts after per-flag verification against the code (the `coder_inherits_planner_chat` "On" text was corrected: the fork prefix is prepended in addition to the plan-file reference, not instead of it). Repointed the only two files that named the old IDs: `src/sase/feature_flags/registry.py` and `tests/feature_flags/test_consumers.py`.

VERIFIED: `sase bead list -T flag` shows all five with unchanged countdowns (88d/88d/89d/89d/90d, all v0.18.0) and sizes; `sase bead show sase-qe` renders the typed flag body block; pages regenerated for all five; `just _lint-flags` green; `sase bead doctor` reports nothing flag-related; `tests/feature_flags` + `tests/test_bead/test_flag_fields.py` 77 passed; `just test-scoped` 4700 passed, 1 skipped. `issues.jsonl` and the compatibility mirror have zero `issue_type: flag` rows. `just check` fails only on the pre-existing `_lint-toobig` violation in `tests/_suite_gate.py` (recorded as a PROPOSED FOLLOW-UP on this bead), which aborts the gate before the test lane -- hence the separate `just test-scoped` run above.

CARRY-OVER: `sase bead rm` leaves a tombstoned event stream, so five streams still hold a flag-typed `issue_created` event. sase-pv.8 has a note with the full analysis and the two constraints on fixing it; that phase must prune them before `IssueTypeWire::Flag` can be deleted.

## Dependencies

- **Depends on:** [sase-pv.3](sase-pv.3.md) ✓ · ⧖ 2026-08-18
- **Depends on:** [sase-pv.5](sase-pv.5.md) ✓ · ⧖ 2026-08-18
- **Depends on:** [sase-pv.6](sase-pv.6.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pv.8](sase-pv.8.md) ✓ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pv.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pv.7/README.md) | [sase-pv.7](sase-pv.7.md) | 0 |
