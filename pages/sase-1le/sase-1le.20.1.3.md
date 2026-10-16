# Bead: sase-1le.20.1.3 — Whole-page move tool and the upgrading history home

[Bead Pages](../README.md) / [sase-1le.20.1](sase-1le.20.1.md) / sase-1le.20.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1le.20](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.20.md) · **Assignee:** `sase-1le.20.1.3` · **Size:** medium
**Created:** 2026-10-16 08:04:35 EDT · **Closed:** 2026-10-16 09:09:35 EDT
**Plan:** [202610/docs\_decompose.md](https://github.com/sase-org/sase--plans/blob/main/202610/docs_decompose.md)

## Description

move-tool: add tools/docs_move for whole-page moves, pilot it on acknowledgements.md, and pilot the hardened docs_split by splitting content_layout.md into Reference and the new reference/upgrading/ hub.

## Notes

[2026-10-16T13:09:30Z · sase-1le.20.1.3] PROPOSED FOLLOW-UP: Fix clean-base extensionless-tool mypy failures (4 in tools/docs_split and 5 in tools/render_keymap_macro_reference; all 9 reproduced identically from HEAD). The render_keymap errors are also recorded on sase-1le.20.1.1 note #1; no matching task bead was found. This phase check was run 8a453fd586cae5562c792347b1336057.

[2026-10-16T13:09:35Z · sase-1le.20.1.3] Added and tested tools/docs_move; moved acknowledgements.md and split content_layout.md into Reference and Upgrading with nav, indexes, redirects/stub, and URL metadata updated. Verified: focused move/split tests 9 passed, Ruff passed, just fix succeeded, docs lint passed, strict docs build and URL contract passed. The aggregate check failed only on nine extensionless-tool mypy errors reproduced identically from clean HEAD; recorded as a proposed follow-up. epic-symbols reported no leftovers.

## Dependencies

- **Depends on:** [sase-1le.20.1.1](sase-1le.20.1.1.md) ✓ · ⧖ 2026-10-16
- **Blocks:** [sase-1le.20.1.10](sase-1le.20.1.10.md) ◐ · ⧖ 2026-10-16
- **Blocks:** [sase-1le.20.1.12](sase-1le.20.1.12.md) ◐ · ⧖ 2026-10-16
- **Depends on:** [sase-1le.20.1.2](sase-1le.20.1.2.md) ✓ · ⧖ 2026-10-16
- **Blocks:** [sase-1le.20.1.4](sase-1le.20.1.4.md) ✓ · ⧖ 2026-10-16
- **Blocks:** [sase-1le.20.1.7](sase-1le.20.1.7.md) ◐ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.20.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.3/README.md) | [sase-1le.20.1.3](sase-1le.20.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a0ad470`](https://github.com/sase-org/sase/commit/a0ad4700459b7e8df330e2d66713495814227efb) | feat(docs): add whole-page move tooling and upgrading hub | [sase-1le.20.1.3](sase-1le.20.1.3.md) | 2026-10-16 09:10:54 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1le.20.1.3][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.3/README.md

<!-- sase:referenced-by:end -->
