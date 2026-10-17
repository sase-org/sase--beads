# Bead: sase-1lh.7.3 — Fix nested drop pointers that resolve anchor\_target through the source anchor map

[Bead Pages](../README.md) / [sase-1lh.7](sase-1lh.7.md) / sase-1lh.7.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1lh.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lh.land.md) · **Assignee:** `sase-1lh.7.3` · **Size:** small
**Created:** 2026-10-16 16:46:20 EDT · **Closed:** 2026-10-16 17:00:14 EDT
**Plan:** [202610/sase\_1lh\_landing\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_1lh_landing_repair.md)

## Description

docs-split-anchor: stop tools/docs_split from rewriting a dropped nested section's explicit anchor_target through the source page's anchor map, and pin it with a regression test.

## Notes

[2026-10-16T20:59:57Z · sase-1lh.7.3] PROPOSED FOLLOW-UP: docs-gen-check fails on clean base (stale docs/reference/cli/*.md vs current CLI --help; recipe docs-gen-check line 523 exit 1) — regenerate CLI reference docs

[2026-10-16T21:00:14Z · sase-1lh.7.3] Fixed nested drop pointers in tools/docs_split: explicit anchor_target pointers now bypass the source anchor_map (new explicit flag on _GeneratedPointer), so reference/parent.md gets Moved to [Reference](index.md#overview). Verified: new regression test fails pre-fix and passes post-fix; strengthened multi-target nested test uses reference/, guides/, howtos/ dirs with exact relative links; 12/12 tests/test_docs_moves.py pass; tools/typecheck_extensionless_tools clean; just lint exit 0. sase tool run check blocked only by pre-existing docs-gen-check CLI-docs drift that fails identically on clean base (recorded as PROPOSED FOLLOW-UP). epic-symbols: none left.

## Dependencies

- **Blocks:** [sase-1lh.7.4](sase-1lh.7.4.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lh.7.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lh.7.3/README.md) | [sase-1lh.7.3](sase-1lh.7.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e41b209`](https://github.com/sase-org/sase/commit/e41b209b24642553524de0beac2de6f9eee9cea5) | fix(docs): keep explicit anchor\_target on nested drop pointers in docs\_split | [sase-1lh.7.3](sase-1lh.7.3.md) | 2026-10-16 17:01:45 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1lh.7.3][1] | check full bead including notes | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lh.7.3/README.md

<!-- sase:referenced-by:end -->
