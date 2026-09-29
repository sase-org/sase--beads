# Bead: sase-1cj.11 — Opt-in automatic ghost at word boundaries

[Bead Pages](../README.md) / [sase-1cj](README.md) / sase-1cj.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.2x` · **Assignee:** `sase-1cj.11` · **Size:** small
**Created:** 2026-09-29 07:14:38 EDT · **Closed:** 2026-09-29 14:17:52 EDT
**Plan:** [202609/prompt\_next\_word\_prediction.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompt_next_word_prediction.md)

## Description

auto-mode: add next_word auto, which shows the gated ghost right after a typed space that ends a prose word at end of line, reusing the ghost-chain acceptance and clearing contract.

## Notes

[2026-09-29T18:17:29Z · sase-1cj.11] PROPOSED FOLLOW-UP: just check stops at the patch/stitch terminology gate on sase-core fixture prose (at_bearing_notes.jsonl); reproduces identically on the clean base tree with this phase stashed, unrelated to next-word auto-mode

[2026-09-29T18:17:52Z · sase-1cj.11] auto-mode done: next_word accepts auto (parser, schema, config docs, ace.md); typed space at a prose word end-of-line shows the gated ghost with no leading separator via the ghost-chain contract; after ', ' a ghost may appear, after '. ' never (<s>-only). Verified: 81 focused tests pass (4 new auto pilot tests + helper/parse/contract), 269 adjacent widget tests pass, 4 next-word PNG goldens pass, ruff/mypy/symvision/fmt clean, no epic-symbols left. just check's patch/stitch terminology gate fails identically on the clean base tree (recorded as PROPOSED FOLLOW-UP); full test-scoped lane exceeded the turn time budget.

## Dependencies

- **Depends on:** [sase-1cj.7](sase-1cj.7.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cj.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.11/README.md) | [sase-1cj.11](sase-1cj.11.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`06c77f3`](https://github.com/sase-org/sase/commit/06c77f321ff320a0aa37422126d0ff63ca649a2a) | feat(ace): opt-in automatic next-word ghost at word boundaries for sase-1cj.11 | [sase-1cj.11](sase-1cj.11.md) | 2026-09-29 14:19:51 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1cj.11][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.11/README.md

<!-- sase:referenced-by:end -->
