# Bead: sase-1io.7.1 — Make the sase-core read-model cache safe under concurrent access

[Bead Pages](../README.md) / [sase-1io.7](sase-1io.7.md) / sase-1io.7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1io.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1io.land.md) · **Assignee:** `sase-1io.7.1` · **Size:** medium
**Created:** 2026-10-09 06:48:48 EDT · **Closed:** 2026-10-09 07:52:22 EDT
**Plan:** [202610/finish\_release\_v0\_18\_0.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_release_v0_18_0.md)

## Description

core-cache-race: stop unlinking or implicitly recreating a live SQLite read-model cache, keep cache faults from failing mutations, prove it with a stress run, and drop the now-redundant lock_wait_ms golden helper.

## Notes

[2026-10-09T11:52:05Z · sase-1io.7.1] core-cache-race fix ready to land in sase-core checkout (uncommitted): store.rs no longer unlinks/replaces/truncates a live SQLite cache anywhere (drop_cache_file now invalidates in place inside one IMMEDIATE txn: rows/streams/frontier intact, token cleared, streams_known removed, generation+content_generation+invalidated_generation monotonic, version keys reset to current); open_read_write opens without CREATE so no schema-less file is ever published; missing files are created atomically via sibling-temp + no-clobber hard_link (macOS+Linux); schema-less/partial files heal in place via DDL+backfill; MutationView cached reads decline with BeadError kind cache_fault (checked opener verifies the invalidation marker, faults invalidate best-effort) and run_mutation replays pre-write cache faults instead of failing the mutation, never after a durable write. Deleted normalize_lock_wait_ms + its test (outcome_string already pins lock_wait_ms=0); module doc updated. How each CI failure mode is removed: (1) no-such-table meta — no unlink + no implicit create + atomic full-schema publish + heal, so a schema-less file can never be observed or persist; (2) SIGBUS — WAL companions of a live DB are never removed (unlink only when the file is provably not SQLite); (3) append failing unable-to-open-database-file — the cache file cannot vanish mid-mutation, and a vanished/invalidated cache now falls back to replay instead of BeadError; (4) torn concurrent-read state — readers never see a schema-less or half-replaced file, rows stay intact across invalidation, writer CAS still guards stale commits. Evidence: new tests invalidation_never_unlinks_a_live_cache, schemaless_cache_file_heals_on_next_read, cache_disappearance_falls_back_to_replay_mid_mutation, invalidated_cache_declines_cached_reads_and_mutation_succeeds all pass; replay_golden_bytes_are_pinned + cached_golden_bytes_match_replay byte-identical; stress concurrent_readers_see_consistent_snapshots 0 failures in 960 runs (2x 16 workers x 30 iters, before-fix baseline is land-agent 1/240 Linux repro + CI modes above); sase tool run check run 6c89e99a35191a6b92b275da50744cc6 SUCCEEDED (4755+ passed incl. full lib suite). Suggest land commit subject fix(bead-read-model): stop unlinking the live read-model cache under concurrent access. No version/changelog/binding/wire changes.

[2026-10-09T11:52:22Z · sase-1io.7.1] Fix + regression tests ready in sase-core checkout (uncommitted, for host finalizer): in-place invalidation replaces all 35 unlink sites, no-CREATE opens, atomic create, schema-less heal, mutation replay fallback, lock_wait helper dropped. Verified: 4 new regression tests pass, replay goldens byte-identical, stress 0/960 (before: 1/240 Linux repro + 4 CI modes), sase tool run check 6c89e99a succeeded. Failure-mode analysis in bead note for core-release.

## Dependencies

- **Blocks:** [sase-1io.7.4](sase-1io.7.4.md) ◐ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1io.7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1io.7.1/README.md) | [sase-1io.7.1](sase-1io.7.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@5c5bcdc`](https://github.com/sase-org/sase-core/commit/5c5bcdc43fca7787dbc0a46711b3307e25150148) | fix(bead-read-model): stop unlinking the live read-model cache under concurrent access | [sase-1io.7.1](sase-1io.7.1.md) | 2026-10-09 07:53:34 EDT |
