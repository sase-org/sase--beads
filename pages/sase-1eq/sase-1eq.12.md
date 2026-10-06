# Bead: sase-1eq.12 — Finish the xprompt-to-macro core flip and land sase-1eq

[Bead Pages](../README.md) / [sase-1eq](README.md) / sase-1eq.12

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.land.md) · **Assignee:** `sase-1eq.12.land`
**Created:** 2026-10-05 10:21:52 EDT
**Plan:** [202610/land\_xprompts\_to\_macros.md](https://github.com/sase-org/sase--plans/blob/main/202610/land_xprompts_to_macros.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/land_xprompts_to_macros.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/land_xprompts_to_macros.md

<!-- sase:links:end -->

## Description

sase-core's check is green again after the contract flip, sase-core and sase no longer emit pre-flip xprompt wire spellings outside durable legacy readers and flag-gated sunset inputs, and the macro docs infographic shows macro names, so the sase-1eq land agent can close the rename epic.

## Notes

[2026-10-05T17:43:37Z · sase-1gt.land] DISCOVERED ISSUE: sase-1gt lander at master 1c9a2cd5df independently reproduces tests/test_macro_terminology.py::test_macro_docs_and_memory_avoid_xprompt_terms (1 failed, 3.25s). Proposing beads: sase-1gt.2 note #1, sase-1gt.3 note #1, sase-1gt.4 note #2. The causal infographic phase sase-1eq.12.3 commit b6114d4f95 added historical old-to-new xprompt labels in docs/images/macro-resolution-infographic.prompt.md without matching exact-line entries in tests/_macro_terminology_docs.py:_MACRO_DOCS_ALLOWLIST. The PNG is relabeled, but its prompt record now trips the rename guard. Reword the record with macro-only labels or classify exact historical lines in the allowlist and its category guard. This belongs to this still-active rename epic, not CI-repair epic sase-1gt; no new task.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.12.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.12.land/README.md) | [sase-1eq.12](sase-1eq.12.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1gt.land][1] | Need active causal epic before routing infographic terminology regression | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1gt.land/README.md

<!-- sase:referenced-by:end -->
