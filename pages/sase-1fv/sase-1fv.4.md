# Bead: sase-1fv.4 — Existing-definition fuzzy finder modal

[Bead Pages](../README.md) / [sase-1fv](README.md) / sase-1fv.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0w7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0w7.md) · **Assignee:** `sase-1fv.4` · **Size:** medium
**Created:** 2026-10-04 06:33:04 EDT · **Closed:** 2026-10-04 10:41:53 EDT
**Plan:** [202610/existing\_macro\_snippet\_editing.md](https://github.com/sase-org/sase--plans/blob/main/202610/existing_macro_snippet_editing.md)

## Description

existing-finder: build the pure entry model, entry builders, ranking, and verdict copy for macros and snippets, then build the shared presentation-only finder modal with Rust fuzzy highlighting, status chips, a debounced off-thread preview, and back/cancel results.

## Notes

[2026-10-04T14:40:49Z · sase-1fv.4] PROPOSED FOLLOW-UP: Add docs/configuration.md:5094 to the terminology test allowlist for its unchanged intentional families/ redirect reference; the focused test reproduces on this clean-base file, and no existing bead tracks it.

[2026-10-04T14:41:53Z · sase-1fv.4] Verified 13 targeted model/modal tests, the three finder snapshots, fmt, mypy, and phase symbol audit (no leftovers). The broad check passed all lint/validation gates and ran 31,988 tests before interruption; two failures were known, and the unchanged docs/configuration.md terminology failure was recorded as a PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-1fv.1](sase-1fv.1.md) ✓ · ⧖ 2026-10-04
- **Depends on:** [sase-1fv.2](sase-1fv.2.md) ✓ · ⧖ 2026-10-04
- **Blocks:** [sase-1fv.5](sase-1fv.5.md) ✓ · ⧖ 2026-10-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1fv.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1fv.4/README.md) | [sase-1fv.4](sase-1fv.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4d38e39`](https://github.com/sase-org/sase/commit/4d38e39702e9871be0b0ecfe8d121de6d3afbc82) | feat(tui): add existing-definition finder modal and entry model | [sase-1fv.4](sase-1fv.4.md) | 2026-10-04 10:44:11 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.5.1.4--1][1] | Check whether this bead tracks the reproduced docs/configuration terminology failure | 1 |
| read-by | [agent:sase-1fv.4][2] | Verify the clean-base follow-up note before phase closure | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.5.1.4.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1fv.4/README.md

<!-- sase:referenced-by:end -->
