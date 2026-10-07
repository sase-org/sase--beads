# Bead: sase-1h8.13 — Mutations load and write through the read model

[Bead Pages](../README.md) / [sase-1h8](README.md) / sase-1h8.13

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3u.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3u.linker.w0.md) · **Assignee:** `sase-1h8.13` · **Size:** large
**Created:** 2026-10-06 18:59:46 EDT
**Plan:** [202610/bead\_store\_history\_independent\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202610/bead_store_history_independent_performance.md)

## Description

read-model-mutations: make MutableStore load only affected rows from the read model and write rows plus frontier through in the same locked critical section.

## Notes

[2026-10-07T23:18:08Z · sase-1h8.13] Progress (read-model-mutations increment 1): landed sase-core groundwork in workspace sase_13 linked sase-core checkout. (1) store_io_stats extended with full_replays/hydrated_rows/stream_reads/validation_runs counters, wired into MutableStore::load/save. (2) jsonl partial writer factored: validates only selected streams + new write_event_store_changed_with_total(beads_dir, streams, changed, total_stream_count) keeps the manifest stream_count exact for lazily loaded slices. (3) read-model freshness: new ensure_cache_ready_for_mutation[_at] forces the full signature sweep inside the flock (never the 60s token-only skip), establishing the version/generation/token/signatures/config/frontier baseline for write-through. (4) new test-gated mutation/view.rs: common cached+replay view with overlay (resolve/get/children/descendants/ancestors/deps/reverse-dependents/external-ref owners/top-level+child allocation/stream routing/receipt checks), mirroring replay ordering and error kinds. (5) 8 new dual-mode tests (mutation/tests/read_model_mutations.rs) pass: cached-vs-replay parity, overlay batch exchange, io_stats proof, manifest-count proof, forced-sweep baseline, validation-rejection byte-stability. Full bead suite: 485 passed. Baseline bench (scale 1, 20 runs, core d2a56b4, /tmp/bead-mutations-before.json): note_append p50 749ms/p95 1185ms/max 1309ms; update p50 764ms/p95 1243ms/max 1260ms; corpus 6899 beads/44775 events/2000 streams/91.9% closed. Bead NOT closed: warm mutations still replay; end-to-end zero-replay note/update + write-through + 8x bench remain. -r Record sase-1h8.13 implementation evidence and baseline

[2026-10-07T23:18:26Z · sase-1h8.13] PROPOSED FOLLOW-UP: Port the full mutation surface (create, notes_update, close_remove, claims, dependencies, links, plus_one_snooze, ready-marking in store.rs) onto mutation/view.rs, then ungate `mod view` for production. The view and its 8 parity tests are landed and green; no caller uses it yet, so warm note/update still does a full replay (scale-1 baseline above). Evidence: git status shows view.rs test-gated with the port note; store_io_stats full_replays counter will prove zero-replay once ported. -r File follow-up for remaining read-model-mutations port

[2026-10-07T23:18:36Z · sase-1h8.13] PROPOSED FOLLOW-UP: Implement mutation write-through (dirty rows/deletes, edges, suffix/allocation entries, scalar columns, link provenance, stream signatures, config/manifest, frontier, freshness token) in one SQLite transaction under beads.db, with snapshot-plus-tail equivalence gating and repair-path fallback for backdated/relocated/rewritten streams. write_event_store_changed_with_total and ensure_cache_ready_for_mutation are landed as the building blocks; the transactional commit and generation-CAS guard are not. Measure fallback frequency in the 1x/8x benchmark for the land agent. -r File follow-up for write-through transaction

[2026-10-07T23:18:49Z · sase-1h8.13] PROPOSED FOLLOW-UP: Pre-existing failure bead_read_parity::event_store_supports_read_queries_without_legacy_projection fails identically on the clean base (verified via git stash: same assertion at bead_read_parity.rs:486, bead_doctor missing the "WARNING: issues.jsonl missing" string). Unrelated to read-model-mutations; needs its own triage bead. Repro: just test -p sase_core --test bead_read_parity event_store_supports_read_queries_without_legacy_projection on master d2a56b4. -r Record pre-existing parity failure as follow-up

[2026-10-07T23:19:00Z · sase-1h8.13] PROPOSED FOLLOW-UP: Pre-existing failure sase_core lib editor::directive::tests::contract_covers_the_audited_directive_matrix fails identically on the clean base (verified via git stash; directive matrix mismatch, nothing to do with beads). Unrelated to read-model-mutations; needs its own triage bead. Repro: just test -p sase_core editor::directive on master d2a56b4. -r Record pre-existing editor test failure as follow-up

## Dependencies

- **Depends on:** [sase-1h8.11](sase-1h8.11.md) ✓ · ⧖ 2026-10-06
- **Depends on:** [sase-1h8.12](sase-1h8.12.md) ✓ · ⧖ 2026-10-06
- **Blocks:** [sase-1h8.14](sase-1h8.14.md) ◐ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.13](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.13.md) | [sase-1h8.13](sase-1h8.13.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@4d5cf65`](https://github.com/sase-org/sase-core/commit/4d5cf6502324a5928a285861b099be393b26de91) | feat(bead): read-model mutation groundwork for sase-1h8.13 | [sase-1h8.13](sase-1h8.13.md) | 2026-10-07 19:21:56 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.3y.grk][1] | Need 1h8 phase statuses that overlap sase-1h5 Beads-pane work | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3y.grk/README.md

<!-- sase:referenced-by:end -->
