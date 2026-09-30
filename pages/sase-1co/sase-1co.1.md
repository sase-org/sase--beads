# Bead: sase-1co.1 — Core launch grammar for mid-word and nested alternation

[Bead Pages](../README.md) / [sase-1co](README.md) / sase-1co.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u1.md) · **Assignee:** `sase-1co.1` · **Size:** medium
**Created:** 2026-09-29 16:22:02 EDT · **Closed:** 2026-09-29 16:47:28 EDT
**Plan:** [202609/midword\_alternation.md](https://github.com/sase-org/sase--plans/blob/main/202609/midword_alternation.md)

## Description

core-grammar: in sase-core, let `%{` open anywhere outside literal zones while `%(`/`%alt(` keep the boundary rule. Also fix the nested-alternation panic, keep glued `%` directives parseable, stop the model shortcut gluing onto an opener, and add tests.

## Notes

[2026-09-29T20:47:28Z · sase-1co.1] core-grammar done in sase-core: %{ opens mid-word while %(/%alt( keep the boundary rule; nested alternation expands per-branch with no panic (a %{x %{p|q} | y} b -> 3 slots); glued % branches gain parseable spacing; model shortcut leaves a space before %{; 17 new/updated tests; sase tool run check green (run 9ad0d6042abb851043d122bea8f5a4df, ~208s)

## Dependencies

- **Blocks:** [sase-1co.2](sase-1co.2.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1co.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1co.1/README.md) | [sase-1co.1](sase-1co.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@1160ea4`](https://github.com/sase-org/sase-core/commit/1160ea41c14fef59c872aee2be3375e872c97642) | feat(launch): support mid-word and nested %{...} alternation | [sase-1co.1](sase-1co.1.md) | 2026-09-29 16:48:27 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1co.1][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1co.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1co.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1co.land/README.md

<!-- sase:referenced-by:end -->
