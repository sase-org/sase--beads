# Bead: sase-1co.4 — TUI prompt input editing for mid-word alternation

[Bead Pages](../README.md) / [sase-1co](README.md) / sase-1co.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u1.md) · **Assignee:** `sase-1co.4` · **Size:** medium
**Created:** 2026-09-29 16:22:06 EDT · **Closed:** 2026-09-29 18:20:05 EDT
**Plan:** [202609/midword\_alternation.md](https://github.com/sase-org/sase--plans/blob/main/202609/midword_alternation.md)

## Description

tui-alt-editing: in sase, make brace padding and `|` separator normalization recognize mid-word openers. Ignore openers in literal zones, keep an unclosed span to its own line, and let the innermost nested span win. Stop Jinja auto-pairing right after `%{`, then update tests and `docs/ace.md`.

## Notes

[2026-09-29T22:19:53Z · sase-1co.4--1] PROPOSED FOLLOW-UP: just check lint (patch/stitch terminology) fails identically on clean base tree (14 defects all in sase-core fixture crates/sase_core/tests/fixtures/note_attachment/at_bearing_notes.jsonl, unrelated to this bead); needs upstream fixture rewording or audit exemption

[2026-09-29T22:20:05Z · sase-1co.4--1] tui-alt-editing done: brace padding and | normalization recognize mid-word openers, literal zones ignored, unclosed span kept to own line, innermost nested span wins, Jinja auto-pair stops after %{. Focused suite 36 passed. just check fails only on pre-existing patch/stitch audit in sase-core fixture, reproduced identically on clean base (recorded as PROPOSED FOLLOW-UP). epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1co.3](sase-1co.3.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1co.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1co.4.md) | [sase-1co.4](sase-1co.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f02c327`](https://github.com/sase-org/sase/commit/f02c3273e455d36cfa2ef1ff182019d554497a4f) | feat(tui): mid-word alternation editing for alt spans | [sase-1co.4](sase-1co.4.md) | 2026-09-29 18:22:23 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1co.4--1][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1co.5][2] | Need TUI editing rules to mirror in nvim | 1 |
| read-by | [agent:sase-1co.land][3] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1co.4.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1co.5/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1co.land/README.md

<!-- sase:referenced-by:end -->
