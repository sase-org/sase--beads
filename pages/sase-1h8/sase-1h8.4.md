# Bead: sase-1h8.4 — One parse, one validation, no lockless-read deletes

[Bead Pages](../README.md) / [sase-1h8](README.md) / sase-1h8.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3u.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3u.linker.w0.md) · **Assignee:** `sase-1h8.4` · **Size:** medium
**Created:** 2026-10-06 18:59:33 EDT · **Closed:** 2026-10-06 19:39:06 EDT
**Plan:** [202610/bead\_store\_history\_independent\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202610/bead_store_history_independent_performance.md)

## Description

parse-once: in sase-core, move the removed-flag stream prune off the read path, drop the deep clone of every stream, and validate each event and issue once (~480 ms to ~290 ms per replay).

## Notes

[2026-10-06T23:38:44Z · sase-1h8.4] parse-once landed in sase-core working tree (linked sase-core checkout, uncommitted; land agent to commit + ratchet sase-core-revision.txt, no new bindings so no sase code changes needed). Read path: no prune/delete/manifest rewrite; removed-flag tombstones skipped in memory and counted in the stream_count check; live-flag still errors with todays message; streams dir listed once; events validated once at parse; no stream clone (reduce_parsed_* entry points, untrusted bead_reduce_event_streams path keeps full validation); per-event IssueWire::validate removed, issues validated once each in post-pass; validate_unique_external_refs O(n) via HashMap with identical error; prune now runs in MutableStore::load under the mutation lock; load-level duplicate ext-ref check removed (covered by reduce on event branch, import on legacy branch). Timing read_event_store_issues on /tmp copy of live-shape store (2112 streams, 7062 issues, debug build, 7 runs sorted): before 3016-3504ms -> after 1210-1345ms (~60% reduction). Relaxed intermediate-state check: a store with an invalid intermediate but valid final state now loads (final-invalid still fails kind=validation); covered by reduction_accepts_invalid_intermediate_state_repaired_by_later_event + reduction_still_rejects_invalid_final_state_with_validation_error. New tests: read_skips_removed_flag_stream_without_touching_the_store (byte-identical), read_rejects_live_flag_stream_with_todays_message, locked_load_prunes_removed_flag_tombstone_skipped_by_reads. Gate: sase tool run check in sase-core succeeded (run 243c48a2011e70b2de50e9290083b24e); bead/binding parity suites green (bead_event_parity 35, bead_storage_parity 15, bead_read_parity 8, 426 bead unit tests).

[2026-10-06T23:39:06Z · sase-1h8.4] parse-once done in sase-core: prune off read path (in-memory tombstone skip, dir listed once), events validated once at parse, no stream clone, per-event issue validation moved to single post-pass, O(n) ext-ref check, prune under mutation lock. Verified: read_store_issues 3016-3504ms -> 1210-1345ms on /tmp live-shape copy (2112 streams, debug); 5 new tests green; bead_event/storage/read parity suites green; sase tool run check succeeded (run 243c48a2011e70b2de50e9290083b24e). No epic-symbol leftovers. Uncommitted sase-core tree left for land agent (commit + ratchet pin); relaxed intermediate-state check recorded in bead notes.

## Dependencies

- **Blocks:** [sase-1h8.7](sase-1h8.7.md) ◐ · ⧖ 2026-10-06
- **Blocks:** [sase-1h8.8](sase-1h8.8.md) ◐ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.4/README.md) | [sase-1h8.4](sase-1h8.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@6573ebb`](https://github.com/sase-org/sase-core/commit/6573ebb0f2853658480086a6c821afdfcb0e7cd0) | feat(beads): one parse, one validation, no lockless-read deletes (sase-1h8.4) | [sase-1h8.4](sase-1h8.4.md) | 2026-10-06 19:40:19 EDT |
