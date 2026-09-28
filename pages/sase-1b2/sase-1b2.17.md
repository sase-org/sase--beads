# Bead: sase-1b2.17 — One card block per run on session containers

[Bead Pages](../README.md) / [sase-1b2](README.md) / sase-1b2.17

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sr](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sr.md) · **Assignee:** `sase-1b2.17` · **Size:** small
**Created:** 2026-09-27 05:49:51 EDT · **Closed:** 2026-09-27 11:15:20 EDT
**Plan:** [202609/agents\_tab\_final\_deck.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_final_deck.md)

## Description

final-run-blocks: give every FINAL card on a session container one CardBlock per shell that ran finalizers, with roster-matched BlockMeta and block ids. Skipped and not-triggered shells appear only in the ledger. The rail, [ / ] and newest landing work in FINAL through the generalized block host.

## Notes

[2026-09-27T10:09:42Z · 0t2] CROSS-EPIC (sase-1b1): if deck views have landed, the block rail's widest tier carries a mode cue: `page N/M` when blocks are paged, `all N` when they are inline. The cue derives from the host's block mode, so expect it on FINAL's run-block rail and include it in the rail-parity tests with Reply. FINAL's block mode is always automatic: it has no deck-view policy and `P` is unavailable, so `forced_block_mode` never applies to it. The full shared rules are in the NOTES on epic sase-1b2.

[2026-09-27T15:14:55Z · sase-1b2.17] PROPOSED FOLLOW-UP: fix pre-existing FINAL-deck test failures test_card_document_decks_is_main_only and test_picker_catalog_covers_every_deck (CARD_DOCUMENT_DECKS/DECK_PICKER_KEYS include FINAL while the tests expect Main-only/cycle-only sets; both fail identically on the clean base tree)

[2026-09-27T15:15:20Z · sase-1b2.17] final-run-blocks done: Overview+instance cards hold one CardBlock per active/ran/interrupted run with Reply-identical block ids and roster-matched BlockMeta; skipped/not-triggered only in ledger; [/], rail incl. page/all cue, newest landing and FINAL sticky verified by 14 new tests; all 68 FINAL tests, ruff and mypy clean; 2 deck-test failures + symvision findings reproduce identically on base (recorded as PROPOSED FOLLOW-UP)

## Dependencies

- **Depends on:** [sase-1b2.15](sase-1b2.15.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1b2.16](sase-1b2.16.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1b2.18](sase-1b2.18.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b2.17](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b2.17/README.md) | [sase-1b2.17](sase-1b2.17.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`01994b5`](https://github.com/sase-org/sase/commit/01994b5299f28f6076de73ae17dd0f41985085bd) | feat(final-deck): one card block per run on session containers | [sase-1b2.17](sase-1b2.17.md) | 2026-09-27 11:19:32 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c][1] | Mapping sase-1b2 phase dependency graph for value report | 1 |
| read-by | [agent:sase-1b2.17][2] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1b2.land][3] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b2.17/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b2.land/README.md

<!-- sase:referenced-by:end -->
