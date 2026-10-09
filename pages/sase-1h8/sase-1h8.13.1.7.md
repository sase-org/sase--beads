# Bead: sase-1h8.13.1.7 — Parity, affected-row and failure-recovery proof plus matched 1x/8x evidence

[Bead Pages](../README.md) / [sase-1h8.13.1](sase-1h8.13.1.md) / sase-1h8.13.1.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0yi](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0yi.md) · **Assignee:** `sase-1h8.13.1.7` · **Size:** medium
**Created:** 2026-10-08 14:46:07 EDT · **Closed:** 2026-10-08 20:47:25 EDT
**Plan:** [202610/finish\_read\_model\_mutations\_child\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_read_model_mutations_child_epic.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:cf5bda21694e0423eeb52bd1 | attached via sase artifact create --bead |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

<!-- sase:links:end -->

## Description

proof: clean up after the parallel ports, prove no ordinary mutation still replays, extend the randomized production-mutation parity harness to every family, cover the remaining failure and edge cases, assert bounded work on a history-shaped fixture, run sampled corpus parity, rerun the matched 1x/8x benchmark, and record phase-acceptance evidence for sase-1h8.13.

## Notes

[2026-10-09T00:47:01Z · sase-1h8.13.1.7] PROPOSED FOLLOW-UP: Matched 1x/8x note/update misses the parent-epic <10% p95 target (after: 1x note p95 114.5ms vs 8x 321.3ms = 2.8x; update p95 156.5ms vs 455.5ms = 2.9x; /tmp/bead-mutations-epic-after.json, artifact file:explicit:cf5bda21694e0423eeb52bd1, same 6899/2000-stream and 55516/16000-stream corpora as before) for perf-gate sase-1h8.14 with a sweep-vs-publication-vs-binding breakdown; threshold stays, no relaxation -r Record measured follow-up for the perf gate

[2026-10-09T00:47:13Z · sase-1h8.13.1.7] Phase acceptance (sase-1h8.13.1.7 proof): every ordinary mutation family runs one shared algorithm on the indexed mutation view with direct write-through publication and replay fallback — create/notes (1h8.13.1.3), open/close/remove (1h8.13.1.4), claims/ready/dependencies (1h8.13.1.5), links/+1/snooze (1h8.13.1.6). Cleanup: no dead code or clippy drift from the parallel ports; MutableStore::load audit shows every src call site is the cached-first replay fallback except export_jsonl (explicit admin path). New proof: mutation/tests/proof_bounded.rs (18 tests: per-family bounded work on a history-shaped fixture — 1 sweep, 0 replays/snapshots, bounded rows/streams, 1 changed-stream signature, token-only next read, cache==replay — plus guarded-close/invalid-batch/no-op byte-stability, old-version-cache fallback+heal, counter-only vs non-counter config gates) and tests/bead_read_model_mutation_proof.rs (randomized 60-step every-family dual-run outcome+state parity; gated bench_corpus_sampled_mutations, proven locally on a generated 1x corpus in 65s). Verified: sase tool run check in sase-core exit 0 (fmt, features, clippy -D warnings, all tests, script tests); bead::mutation 240 pass; fmt clean; epic-symbols clean. Matched bench (seed 20261006, 20 runs, SASE_ALLOW_STALE_CORE=1 rust-install of dd1a67c0+proof WIP into sase .venv; JSON echoes pin e8606a56; host load ~17 like before): before->after p95 — 1x note 238.6->114.5ms, update 267.6->156.5ms; 8x note 1337.9->321.3ms, update 1586.2->455.5ms. Artifacts: before file:explicit:c6e84b9abb0aa9ec8460fdf0, after file:explicit:cf5bda21694e0423eeb52bd1. Work is uncommitted in the linked sase-core checkout (mod.rs + 2 new files) for host finalizers; sase repo tree clean; no pin move (no new bindings). The 1x->8x p95 ratio (2.8-2.9x) misses the <10% target: filed as PROPOSED FOLLOW-UP for sase-1h8.14, threshold not relaxed. -r Record phase-acceptance evidence for sase-1h8.13

[2026-10-09T00:47:25Z · sase-1h8.13.1.7] Proof complete and verified: all families on the mutation view with direct write-through (sibling ports 1.4/1.5/1.6); MutableStore::load only via replay fallback plus export_jsonl; 18 bounded-work + 2 every-family parity tests green (incl. local 1x corpus mutation run); sase tool run check exit 0; matched 1x/8x after-evidence recorded (1x note p95 114.5ms, update 156.5ms; 8x note 321.3ms, update 455.5ms; artifacts before file:explicit:c6e84b9abb0aa9ec8460fdf0 / after file:explicit:cf5bda21694e0423eeb52bd1); 1x->8x miss filed as follow-up for sase-1h8.14; epic-symbols clean; uncommitted sase-core work left for host finalizers.

## Dependencies

- **Depends on:** [sase-1h8.13.1.4](sase-1h8.13.1.4.md) ✓ · ⧖ 2026-10-08
- **Depends on:** [sase-1h8.13.1.5](sase-1h8.13.1.5.md) ✓ · ⧖ 2026-10-08
- **Depends on:** [sase-1h8.13.1.6](sase-1h8.13.1.6.md) ✓ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.13.1.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.7/README.md) | [sase-1h8.13.1.7](sase-1h8.13.1.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@3e45924`](https://github.com/sase-org/sase-core/commit/3e45924865a58d23cbe704e0a1b6e6130c086039) | test(sase-core): prove bounded mutation work and every-family read-model parity | [sase-1h8.13.1.7](sase-1h8.13.1.7.md) | 2026-10-08 20:48:29 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1h8.13.1.7][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.7/README.md

<!-- sase:referenced-by:end -->
