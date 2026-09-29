# Bead: sase-1cj.6 — Ghost-text next-word chain on Ctrl+T

[Bead Pages](../README.md) / [sase-1cj](README.md) / sase-1cj.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.2x` · **Assignee:** `sase-1cj.6` · **Size:** medium
**Created:** 2026-09-29 07:14:32 EDT · **Closed:** 2026-09-29 12:38:45 EDT
**Plan:** [202609/prompt\_next\_word\_prediction.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompt_next_word_prediction.md)

## Description

ghost-chain: arm the chain after every word commit, show gated predictions as inline ghost text with a border hint, make Ctrl+T/Alt+F take one word and Ctrl+F/Right/Ctrl+L take all, clear the ghost on every exit, add the next_word config keys, CSS, docs, tests, and PNG goldens.

## Notes

[2026-09-29T16:38:20Z · sase-1cj.6--1] PROPOSED FOLLOW-UP: just check gate `_lint-patch-stitch-terminology` fails on 14 `defect` hits all inside linked sase-core fixture crates/sase_core/tests/fixtures/note_attachment/at_bearing_notes.jsonl (committed at sase-core 39324ac); sase tree has zero hits and no repos/ modifications, so it reproduces identically on the clean base tree

[2026-09-29T16:38:45Z · sase-1cj.6--1] ghost-chain phase complete: fixed mypy attr-defined error by declaring hide_next_word_hint in PromptInputBarStackNavigationMixin TYPE_CHECKING block; mypy clean on the file, 43 phase tests pass (test_prompt_next_word, test_next_word_completion, config schema), full check green through lint(feature flags) with only pre-existing sase-core fixture terminology failure remaining (recorded as follow-up); no epic-symbol leftovers

## Dependencies

- **Depends on:** [sase-1cj.1](sase-1cj.1.md) ✓ · ⧖ 2026-09-29
- **Depends on:** [sase-1cj.5](sase-1cj.5.md) ✓ · ⧖ 2026-09-29
- **Blocks:** [sase-1cj.7](sase-1cj.7.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cj.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1cj.6.md) | [sase-1cj.6](sase-1cj.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`935243f`](https://github.com/sase-org/sase/commit/935243ffe914831edcef7d6415a5fd43cdc50bcd) | feat(ace): next-word prompt completion for sase-1cj.6 | [sase-1cj.6](sase-1cj.6.md) | 2026-09-29 12:41:44 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1cj.6--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1cj.6.md

<!-- sase:referenced-by:end -->
