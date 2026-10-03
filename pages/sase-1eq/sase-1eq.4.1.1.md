# Bead: sase-1eq.4.1.1 — Sunset flag and shared compatibility contracts

[Bead Pages](../README.md) / [sase-1eq.4.1](sase-1eq.4.1.md) / sase-1eq.4.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.4.md) · **Assignee:** `sase-1eq.4.1.1` · **Size:** medium
**Created:** 2026-10-03 05:59:57 EDT · **Closed:** 2026-10-03 07:27:53 EDT
**Plan:** [202610/macro\_syntax\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202610/macro_syntax_cutover.md)

## Description

compatibility: create legacy_xprompt_syntax through sase flag new, add the shared Rust config normalization contract and thin Python compatibility facade, and verify both flag states without flipping existing Rust output contracts.

## Notes

[2026-10-03T11:14:20Z · sase-1eq.4.1.1--2] PROPOSED FOLLOW-UP: base-tree symvision flags history_only_node (memory_pane_rail_glance.py) and instruction_display_for_subject_id (memory_pane_instructions.py) on clean base 957513c8e14971fb7b76b53556c667f95b89fa55 via symvision src/sase (exit 1); pre-existing in-file-only public helpers, not from this phase

[2026-10-03T11:27:53Z · sase-1eq.4.1.1--3] compatibility done: flag bead sase-1fj open (legacy_xprompt_syntax retire-by 2027-01-01); 12 Python tests/test_legacy_xprompt_syntax.py both-states pass; 9 Rust macro_syntax tests + binding round-trip + schema --check clean (prior focused evidence); primary just check: only 2 base-proven NEW symvision items remain (history_only_node, instruction_display_for_subject_id, base 957513c8e, FOLLOW-UP noted), retired_xprompt_syntax_message removed via dead-helper deletion; sase-core wrapped check green (CORE_EXIT=0); epic-symbols empty; sase-core-revision.txt pin move left for host finalization

## Dependencies

- **Blocks:** [sase-1eq.4.1.2](sase-1eq.4.1.2.md) ✓ · ⧖ 2026-10-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.4.1.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.4.1.1.md) | [sase-1eq.4.1.1](sase-1eq.4.1.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@4eb40d5`](https://github.com/sase-org/sase-core/commit/4eb40d59089ffe5a10398941971ef5202820cd5d) | feat(compat): shared Rust config normalization contract | [sase-1eq.4.1.1](sase-1eq.4.1.1.md) | 2026-10-03 07:29:09 EDT |
| sase | [`3c1f5c3`](https://github.com/sase-org/sase/commit/3c1f5c313e246d2e97ef694e0c472613f3955313) | feat(compat): sunset flag and shared compatibility contracts | [sase-1eq.4.1.1](sase-1eq.4.1.1.md) | 2026-10-03 07:34:07 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.4.1.1--3][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.4.1.1.md

<!-- sase:referenced-by:end -->
