# Bead: sase-1cj.3 — Rust prompt\_prediction engine in sase-core

[Bead Pages](../README.md) / [sase-1cj](README.md) / sase-1cj.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.2x` · **Assignee:** `sase-1cj.3` · **Size:** medium
**Created:** 2026-09-29 07:14:28 EDT · **Closed:** 2026-09-29 09:14:02 EDT
**Plan:** [202609/prompt\_next\_word\_prediction.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompt_next_word_prediction.md)

## Description

core-engine: new sase_core::prompt_prediction module with the prose tokenizer and privacy filters, the legacy origin heuristic, the compiled n-gram corpus (recency-weighted mass, distinct support, project partitions), and multi-source stupid-backoff prediction with confidence presets, greedy continuation, and rank_prefix.

## Notes

[2026-09-29T13:14:02Z · sase-1cj.3] core-engine done in sase-core: new sase_core::prompt_prediction module (mod/wire/tokenize/origin/corpus/model/predict/tests, all files <=1009 lines, facade-only mod.rs, no root pub use). Verified: 61 unit/integration tests pass; sase tool run check gate green; release #[ignore] perf test on synthetic 10k corpus reports compile 75ms (budget 500), predict p95 0.34ms (budget 0.5), approx 39KB (budget 5MB); epic-symbols clean; sase tree untouched, changes uncommitted in linked sase-core checkout for the land agent.

## Dependencies

- **Blocks:** [sase-1cj.4](sase-1cj.4.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cj.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.3/README.md) | [sase-1cj.3](sase-1cj.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@f88fb25`](https://github.com/sase-org/sase-core/commit/f88fb255e1c17679f14abdf81dafba809c4db6a8) | feat(prompt-prediction): add Rust prompt\_prediction engine with tokenizer, n-gram corpus and backoff prediction | [sase-1cj.3](sase-1cj.3.md) | 2026-09-29 09:17:10 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1cj.3][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.3/README.md

<!-- sase:referenced-by:end -->
