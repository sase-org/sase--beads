# Bead: sase-1cj.12.3 — Meet the prompt prediction latency, compile, and memory budgets

[Bead Pages](../README.md) / [sase-1cj.12](sase-1cj.12.md) / sase-1cj.12.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1cj.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1cj.land.md) · **Assignee:** `sase-1cj.12.3` · **Size:** medium
**Created:** 2026-09-29 18:29:17 EDT · **Closed:** 2026-09-30 10:37:16 EDT
**Plan:** [202609/finish\_prompt\_next\_word\_prediction.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_prompt_next_word_prediction.md)

## Description

core-perf: make the perf test representative, measure production predict on real history, and optimize the corpus layout and predict path until p95, compile time, and corpus bytes meet their budgets, with identical results.

## Notes

[2026-09-30T13:34:03Z · sase-1cj.12.3] PROPOSED FOLLOW-UP: predict p95 budget unreachable under identical-results contract — confident queries run up to ~20 scoring rounds (continuation + per-menu previews) at ~40-80us per round over ~100-200 candidates x 5 orders; real-history --bench shows p95 8.7ms on the old release wheel and ~1.7ms synthetic on new code (dev-update), both far above the 0.5ms budget; reaching it needs a contract change (cap preview rounds/candidates or gate-then-menu) or a higher budget

[2026-09-30T13:34:30Z · sase-1cj.12.3] PROPOSED FOLLOW-UP: compile 50ms-per-1k budget unreachable for full rebuilds — ~1.5M pairs must be aggregated per 4k rows (~76 tokens each) and tokenization alone costs ~28ms per 1k; measured 235ms per 1k on real history (old release wheel) and ~250-386ms per 1k synthetic on new code (dev-update); reaching it needs tokenize+compile co-design (zero-alloc interning) or an incremental-compile contract

[2026-09-30T13:34:42Z · sase-1cj.12.3] PROPOSED FOLLOW-UP: corpus 5MB budget unreachable losslessly — the real-history evidence set (225k contexts, 320k successors) floors above ~14MB even with perfect packing, and HashMap residency puts the new layout at ~44-71MB synthetic / ~54MB real; options are lossy pruning/quantization (a product decision) or a raised budget

[2026-09-30T13:35:00Z · sase-1cj.12.3] PROPOSED FOLLOW-UP: re-measure release numbers on new code and tighten pins — run the ignored release perf test plus tools/prompt_prediction_replay --bench with a fresh release wheel (just rust-install), then tighten the dev-update pins in performance_budgets_on_representative_corpus and refresh the docs/rust_backend.md cost paragraph; release should beat dev-update by ~10-25%

[2026-09-30T13:35:12Z · sase-1cj.12.3] Phase work verified this turn: sase-core sase tool run check green (177s); 4019 lib tests + 81 prompt_prediction tests incl replay_matches_production_ranking_and_gate green; 96 sase prediction-suite tests green (incl one 12.1-leftover facade fixture fix: added 4th implement row); clippy/fmt clean; --bench works on real history; sase just check pending via verify monitor

[2026-09-30T14:36:56Z · sase-1cj.12.3--3] PROPOSED FOLLOW-UP: just check lint (patch/stitch terminology) fails on clean base too — 14 defects all in untouched sase-core fixture crates/sase_core/tests/fixtures/note_attachment/at_bearing_notes.jsonl; audit output byte-identical with and without this bead diff; no bead file flagged

[2026-09-30T14:37:16Z · sase-1cj.12.3--3] validate_sase_core_rs probe fixed for once-per-row support semantics (4th implement row; rows_used/total/typed 3->4) plus matching stub fix in test_validate_sase_core_rs_prompt_tool.py; verified: 66 prediction tests passed/3 skipped, facade 13 passed, validate probe exit 0, ruff clean; just check green except pre-existing patch/stitch lint failure proven byte-identical on clean base (recorded as PROPOSED FOLLOW-UP); epic-symbols clean

## Dependencies

- **Depends on:** [sase-1cj.12.1](sase-1cj.12.1.md) ✓ · ⧖ 2026-09-29
- **Blocks:** [sase-1cj.12.4](sase-1cj.12.4.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cj.12.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1cj.12.3.md) | [sase-1cj.12.3](sase-1cj.12.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@8c97d9b`](https://github.com/sase-org/sase-core/commit/8c97d9b242e2d54f1914fa20db4bde41d6b5c512) | feat(prompt-prediction): add sase\_core prompt prediction module | [sase-1cj.12.3](sase-1cj.12.3.md) | 2026-09-30 10:39:55 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1cj.12.3--3][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1cj.12.4][2] | Need core-perf outcome numbers and follow-ups before recalibration | 1 |
| read-by | [agent:sase-1cj.12.land][3] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1cj.12.3.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.12.4/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.12.land/README.md

<!-- sase:referenced-by:end -->
