# Bead: sase-1b2.16 — Generic instance cards with commit and command enrichers

[Bead Pages](../README.md) / [sase-1b2](README.md) / sase-1b2.16

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sr](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sr.md) · **Assignee:** `sase-1b2.16` · **Size:** medium
**Created:** 2026-09-27 05:49:50 EDT · **Closed:** 2026-09-27 10:18:02 EDT
**Plan:** [202609/agents\_tab\_final\_deck.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_final_deck.md)

## Description

final-instance-cards: render one provider-neutral card per finalizer instance with why/trigger/declared lines, attempt sections (latest or failing expanded), operations, steps, typed evidence, deduped diagnostics, log and protocol hint targets, export and search. Add additive builtin@commit and builtin@command enrichers, proven against a plugin fixture.

## Notes

[2026-09-27T14:17:32Z · sase-1b2.16] PROPOSED FOLLOW-UP: pre-existing check failures reproduce on clean base tree — test_card_document_decks_is_main_only and test_picker_catalog_covers_every_deck (FINAL registration vs deck-cycle tables, likely 1b2.14 follow-up), flaky test_files_ctrl_j_scrolls_page_anchor_to_top, symvision 54 unused (base count), toobig src/sase/tool/executor.py 1175 lines

[2026-09-27T14:18:02Z · sase-1b2.16] Generic instance cards done: new final/instance_card.py (header, why/trigger/declared, attempt fold latest-expanded/older-collapsed, ops+steps with warn summary, typed evidence incl. short-SHA commit-view target, deduped diagnostics with superseded-never-red, logs/protocol v-target lines, calm refused/deferred/not-run blocks, unknown-status neutral dot, width-capped lines) plus final/enrichers.py registry (builtin@commit SHA/bead/deferral table, builtin@command argv+exit lines, plugins none) wired into build_final_deck_document. Verified: 10 new tests pass, 26 shell + status/adapter suites pass, ruff/mypy clean, symvision identical to base (54 pre-existing, 0 new). Pre-existing base failures recorded as PROPOSED FOLLOW-UP. No epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-1b2.14](sase-1b2.14.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1b2.17](sase-1b2.17.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b2.16](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b2.16/README.md) | [sase-1b2.16](sase-1b2.16.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6ad0539`](https://github.com/sase-org/sase/commit/6ad0539cfc5b337c87927b8e0779ef9de8631ce9) | feat(ace-tui): generic FINAL instance cards with commit and command enrichers | [sase-1b2.16](sase-1b2.16.md) | 2026-09-27 10:20:13 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c][1] | Mapping sase-1b2 phase dependency graph for value report | 1 |
| read-by | [agent:sase-1b2.16][2] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b2.16/README.md

<!-- sase:referenced-by:end -->
