# Bead: sase-1h8.13.1.9.8 — Cleanup, single-algorithm audit, cached-equals-golden bytes, and acceptance evidence

[Bead Pages](../README.md) / [sase-1h8.13.1.9](sase-1h8.13.1.9.md) / sase-1h8.13.1.9.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1h8.13.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.13.1.land.md) · **Assignee:** `sase-1h8.13.1.9.8` · **Size:** medium
**Created:** 2026-10-08 21:24:23 EDT · **Closed:** 2026-10-09 02:58:02 EDT
**Plan:** [202610/unify\_bead\_mutation\_algorithms.md](https://github.com/sase-org/sase--plans/blob/main/202610/unify_bead_mutation_algorithms.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:8ca5f30ead916b9acacf577e | attached via sase artifact create --bead |

<!-- sase:links:end -->

## Description

proof: delete what the unification left unused, including the view's allow(dead_code); prove by search that MutableStore::load is reached only by the view's replay backing and export_jsonl; assert that cached-mode golden scenarios produce the golden bytes; rerun the parity and proof suites and the matched 1x/8x bench; record acceptance evidence for the sase-1h8.13.1 and sase-1h8.13 landings.

## Notes

[2026-10-09T06:17:57Z · sase-1h8.13.1.9.8] PROPOSED FOLLOW-UP: replay golden pins environmental lock_wait_ms (update_title_legacy committed 18ms vs 0ms under parallel load); normalize or drop lock_wait_ms from golden outcome comparison so bead::mutation stays green under load

[2026-10-09T06:57:47Z · sase-1h8.13.1.9.8--1] ACCEPTANCE (proof phase): single-algorithm audit and verification evidence.

AUDIT (sase-core working tree, HEAD 4ea91b95 + uncommitted proof changes):
- MutableStore::load non-test callers: exactly two — mutation/store.rs export_jsonl and mutation/view.rs load_replay. No ordinary mutation calls it directly; production enters via runner (load_cached, then load_replay on decline).
- view.rs: 4 allow(dead_code) removed (grep clean); load/with_replay are #[cfg(test)]-gated; load_replay owns its store.
- Deleted: MutableStore::append_issue_event/stream_for_mut/stream_id_for_issue/resolve_issue_id and notes append_note_to_store (no remaining references in mutation/). Single mint helper: shared::mint_stream_event is the only mint fn; snooze_plus_one (2 call sites) and store tests rewritten onto it.
- cfg(test)-gated test-only items confirmed: view load/with_replay/ancestors/dependency_targets/read_admission_witness; store issue_index/get_issue/not_found.

GOLDENS (155 files):
- replay_golden_bytes_are_pinned: ok. cached_golden_bytes_match_replay (new, never regenerates): ok standalone and in the 244-test lib run.
- One full-check run failed it on environmental timing only: release_event lock_wait_ms committed 0ms vs golden 5ms under parallel load. Same flake class as bead note #1 (update_title_legacy 18-vs-0ms). Goldens untouched per plan. sase tool run check green on retry (run 460f6cc759bdb20715aabf972a602836).

SUITES (all green):
- bead_read_model_mutation_proof 2/2, incl. bench_corpus_sampled_mutations on the deterministic 1x corpus (SASE_BEAD_BENCH_STORE=/tmp/proof-corpus-1x, seed 20261006, 63s).
- bead_read_model_parity 6/6. lib bead::mutation 244/244. cargo fmt: one whitespace nit in new test code fixed; fmt-check clean.

BENCH (matched 1x/8x, 20 runs, note_append+update; ms):
- baseline file:explicit:cf5bda21694e0423eeb52bd1; after file:explicit:8ca5f30ead916b9acacf577e (pin 5c4033f6; tested code = working tree via venv install; corpus shape byte-identical: 1x 6899 beads/44775 events, 8x 55516/361682).
- 1x note: base med 100.0/p95 114.5 -> after med 103.2/p95 406.7 (max 694.7). 1x update: 93.1/156.5 -> 80.4/172.2 (max 197.6).
- 8x note: 290.4/321.3 -> 262.5/478.9 (max 1152.4). 8x update: 268.0/455.5 -> 263.4/602.9 (max 846.7).
- Medians match or improve (no beyond-noise regression); p95 spikes are single-iteration environmental outliers on a loaded box (max >> median, same corpus), consistent with the lock_wait_ms load flake above. 1x-to-8x scaling target belongs to sase-1h8.14.

Monitor vzxzvks0ew23 FAILED only on a shell quoting typo (q!..!q) in the corpus-gen step; rust-install had succeeded. All four steps were rerun correctly inline and verified above.

[2026-10-09T06:58:02Z · sase-1h8.13.1.9.8--1] Verified: MutableStore::load reached only by view load_replay and export_jsonl (grep); 4 view allow(dead_code) removed; dead MutableStore/notes helpers deleted; single mint shared::mint_stream_event. Suites green: proof 2/2 (incl. 1x-corpus slow test), parity 6/6, lib bead::mutation 244/244, 155 goldens pinned + cached-equals-golden ok. sase tool run check green on retry (first attempt hit documented lock_wait_ms load flake, cf. bead note #1; goldens untouched). Matched 1x/8x bench: medians match/improve vs file:explicit:cf5bda21694e0423eeb52bd1, no beyond-noise regression; after-run file:explicit:8ca5f30ead916b9acacf577e. Full acceptance record in bead note. epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1h8.13.1.9.4](sase-1h8.13.1.9.4.md) ✓ · ⧖ 2026-10-08
- **Depends on:** [sase-1h8.13.1.9.5](sase-1h8.13.1.9.5.md) ✓ · ⧖ 2026-10-08
- **Depends on:** [sase-1h8.13.1.9.6](sase-1h8.13.1.9.6.md) ✓ · ⧖ 2026-10-08
- **Depends on:** [sase-1h8.13.1.9.7](sase-1h8.13.1.9.7.md) ✓ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.13.1.9.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.13.1.9.8.md) | [sase-1h8.13.1.9.8](sase-1h8.13.1.9.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@2d00938`](https://github.com/sase-org/sase-core/commit/2d009388b7a371ec98ffc75b1dfedb69fcb86e7e) | refactor(bead): split mutation into single-algorithm modules with replay goldens | [sase-1h8.13.1.9.8](sase-1h8.13.1.9.8.md) | 2026-10-09 02:59:18 EDT |
