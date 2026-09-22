# Bead: sase-16n.1 — sase-core project tag lexer, resolver, expander, and bindings

[Bead Pages](../README.md) / [sase-16n](README.md) / sase-16n.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pl](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pl.md) · **Assignee:** `sase-16n.1` · **Size:** medium
**Created:** 2026-09-22 18:48:45 EDT · **Closed:** 2026-09-22 19:43:03 EDT
**Plan:** [202609/project\_tags.md](https://github.com/sase-org/sase--plans/blob/main/202609/project_tags.md)

## Description

core-tags: add the sase_core project_tag module (tag scanning with literal-zone skipping, anchored-position detection, case-insensitive resolution with suggestions, in-place expansion to VCS refs, completion trigger and selection-apply), the v5 catalog wire types, and Python bindings.

## Notes

[2026-09-22T23:43:03Z · sase-16n.1] core-tags done: new sase_core::project_tag module (scan/resolve/expand/trigger/apply, 19 tests), v5 catalog wire (VcsProjectCatalogWire + entry key/tag/accent_index/current, v1-v4 compat tests), D1 trigger in token.rs with wrapper, vcs_candidates rewired to in-place D7 accept (ported goldens), 5 project_tag_* bindings with char-offset round-trip tests, LSP loader accepts v1-v5. sase tool run check green; epic-symbols clean. Note: no existing core edit-distance helper fit suggestions (fuzzy_match can't rank transpositions like +ssae->+sase), so resolve uses a small local Levenshtein ranker.

## Dependencies

- **Blocks:** [sase-16n.3](sase-16n.3.md) ◐ · ⧖ 2026-09-22
- **Blocks:** [sase-16n.4](sase-16n.4.md) ◐ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16n.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.1/README.md) | [sase-16n.1](sase-16n.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16n.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.1/README.md

<!-- sase:referenced-by:end -->
