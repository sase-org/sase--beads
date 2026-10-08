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

[2026-10-08T12:40:47Z · sase-1h8.13--1] Phase evidence: indexed note/update read-model path (WIP on ec92ecce).

Implemented (sase-core, uncommitted WIP, 6 files):
- New crates/sase_core/src/bead/mutation/indexed.rs: lazy indexed note_append/update path (avoids full-issue Vec rebuild for note/update).
- Tail-refresh write-through in mutation/store.rs + mutation/mod.rs + mutation/notes_update.rs.
- Non-database cache heal in bead/read_model/store.rs.
- New tests in mutation/tests/read_model_mutations.rs (6 new indexed tests).
Production mutations still use the full-issue Vec; indexed path is additive/WIP, NOT a cutover. View still test-gated.

Tests proven this turn (before benchmark):
- bead::mutation: 165 pass incl 6 new indexed tests.
- bead::mapping: 17 pass.
- sase_core_py: 41 pass.
- Parity suites pass except pre-existing bead_read_parity:486 failure, reproduced identically on clean base.
- sase tool run check 391s with only that same failure.

Benchmark AFTER (SASE_ALLOW_STALE_CORE=1 just rust-install + bench_bead_scale --scale 1 --scale 8 --runs 20 --only note_append,update; exit 0; core_revision ec92ecce1688f85f15c4f989ee82b0537a95d925 + WIP):
- scale 1 (6899 beads / 44775 events / 2000 streams): note_append p50 169.39ms / p95 180.36ms / max 218.66ms; update p50 169.75ms / p95 189.34ms / max 192.66ms.
- scale 8 (55516 beads / 361682 events / 16000 streams): note_append p50 1081.54ms / p95 1184.46ms / max 1265.04ms; update p50 1073.83ms / p95 1104.83ms / max 1108.23ms.
BEFORE baseline (bead note #1, different SHA d2a56b4, context only): scale-1 note p50 749ms/p95 1185ms/max 1309ms, update p50 764ms/p95 1243ms/max 1260ms. So scale-1 p50 ~4.4-4.5x faster after; p95 also down sharply. No 8x before-baseline exists, so 8x after is data only.

REMAINING (do not close this bead):
- create/close/claims/deps/links/snooze/ready still replay; view still test-gated.
- Allocator metadata work outstanding.
- Full streams-table rewrite still lives in tail commit.
- No 8x before-baseline for comparison. -r Record sase-1h8.13 implementation evidence

[2026-10-08T17:52:05Z · sase-1h8.13] Phase evidence (read-model-mutations increment 2, sase-core HEAD cd73d968 + WIP): (1) allocation metadata landed: new read_model/alloc.rs (textual top/child maxima matching store.rs oracle, incl mismatched parent fields, malformed/nested/multiple-prefix/empty, staged creates/removes, max-removal recompute via prefix-scoped LIKE), schema 2->3 with rebuild population, tail maintenance on upserts/deletes, view allocators now index-only with overlay (replay backing fixed to textual scan). Reducer/wire versions unchanged. (2) MutationView ungated to production: load_cached admits inside beads.db flock after forced sweep without preloading replay (with_replay only on fallback/repair), memoized hydrated rows + overlay staged-final-state, baseline witness (generation/frontier/token), SQLite/decode faults stay io (never not-found). (3) tail publication hardened: stream signatures upsert-only (no DELETE+reinsert; untouched rows not rewritten), content_generation CAS added (generation alone could not distinguish successive tails) + rebuild bump, alloc maintenance in write_tail_rows. (4) shared mutation/publish.rs: forced-sweep tail publication with witness-advance check, reducer-truth corrections, fail-open cache-fault contract (events stand, next read tails/rebuilds/replays; non-database heal via read path). (5) create_issue ported onto view+lazy single stream+indexed external-ref check+manifest-total write+publish; replay fallback preserved for legacy/missing-stream/corrupt. (6) tests: alloc unit (3) + cached-create parity (zero full_replays, <=5 hydrated rows, <=2 stream reads, verify matched) + child-alloc oracle match; suites green: bead::mutation 168 pass, bead::read_model 20 pass, full lib 4645 pass; sase tool run check has 1 failure which reproduces identically on clean base via git stash (bead_read_parity:486 issues.jsonl-missing warning expectation, already filed as PROPOSED FOLLOW-UP #4 + epic DISCOVERED ISSUE #3). Bead NOT closed: close/claims/deps/links/snooze/ready + notes_update consolidation still replay; direct (no-second-sweep) publication + no-snapshot tail refresh + full parity/affected-row proofs + 1x/8x benchmarks remain (see PROPOSED FOLLOW-UPs #2/#3). -r Record sase-1h8.13 implementation evidence

## Dependencies

- **Depends on:** [sase-1h8.11](sase-1h8.11.md) ✓ · ⧖ 2026-10-06
- **Depends on:** [sase-1h8.12](sase-1h8.12.md) ✓ · ⧖ 2026-10-06
- **Blocks:** [sase-1h8.14](sase-1h8.14.md) ◐ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.13](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.13.md) | [sase-1h8.13](sase-1h8.13.md) | 3 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@4d5cf65`](https://github.com/sase-org/sase-core/commit/4d5cf6502324a5928a285861b099be393b26de91) | feat(bead): read-model mutation groundwork for sase-1h8.13 | [sase-1h8.13](sase-1h8.13.md) | 2026-10-07 19:21:56 EDT |
| sase-core | [`sase-core@7b3b9aa`](https://github.com/sase-org/sase-core/commit/7b3b9aa51876f7435e9b2e8dcfca97dd59529dde) | feat(beads): add indexed note/update read-model path with tail-refresh write-through | [sase-1h8.13](sase-1h8.13.md) | 2026-10-08 08:41:35 EDT |
| sase-core | [`sase-core@1ff4360`](https://github.com/sase-org/sase-core/commit/1ff436055b128f21349e0f8d1136020e0a4cb079) | feat(beads): indexed allocation metadata, shared mutation view/publish, cached create port | [sase-1h8.13](sase-1h8.13.md) | 2026-10-08 13:54:44 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.3y.grk][1] | Need 1h8 phase statuses that overlap sase-1h5 Beads-pane work | 1 |
| read-by | [agent:sase-1h7.land][2] | Check whether the in-progress read-model mutations phase already knows about the sase-core bead_read_parity legacy-projection failure | 1 |
| read-by | [agent:sase-1h8.13.1.1][3] | phase scope | 1 |
| read-by | [agent:sase-1h8.13.1.2][4] | phase scope | 1 |
| read-by | [agent:sase-1h8.13.1.4][5] | phase scope and progress notes | 1 |
| read-by | [agent:sase-1h8.13.1.5][6] | Need parent phase scope | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3y.grk/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h7.land/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.1/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.2/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.4/README.md
[6]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.5/README.md

<!-- sase:referenced-by:end -->
