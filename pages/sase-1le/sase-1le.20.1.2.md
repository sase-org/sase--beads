# Bead: sase-1le.20.1.2 — Make docs\_split, render\_moves, and check\_docs safe for monolith splits

[Bead Pages](../README.md) / [sase-1le.20.1](sase-1le.20.1.md) / sase-1le.20.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1le.20](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.20.md) · **Assignee:** `sase-1le.20.1.2` · **Size:** medium
**Created:** 2026-10-16 08:04:35 EDT · **Closed:** 2026-10-16 08:22:03 EDT
**Plan:** [202610/docs\_decompose.md](https://github.com/sase-org/sase--plans/blob/main/202610/docs_decompose.md)

## Description

split-tool: add H4 and nested selections, drop mappings, intro handling, anchor recording in target context, partial-split pointers, a dry-run budget report, and --finish to docs_split; stop render_moves clobbering hand-written pages; let check_docs accept root stubs and a homepage rule.

## Notes

[2026-10-16T12:21:44Z · sase-1le.20.1.2] PROPOSED FOLLOW-UP: Required sase tool run check and docs lint remain red on the pre-existing generated-docs/Prettier drift and 424-word Reference hub; these match the clean-base failures assigned to gates phase sase-1le.20.1.1 (and sase-1le note #4 for renderer drift).

[2026-10-16T12:22:03Z · sase-1le.20.1.2] Verified 33 focused docs move/check_docs tests and Ruff checks; epic-symbol audit is clear. Full check remains red on the pre-existing generated-docs/Prettier drift and 424-word Reference hub, recorded as a proposed follow-up citing gates phase sase-1le.20.1.1.

## Dependencies

- **Blocks:** [sase-1le.20.1.3](sase-1le.20.1.3.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.20.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.2/README.md) | [sase-1le.20.1.2](sase-1le.20.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`900925c`](https://github.com/sase-org/sase/commit/900925c99486c8b08528b8773ff4295f6ea36bf6) | feat(docs): harden split and move tooling | [sase-1le.20.1.2](sase-1le.20.1.2.md) | 2026-10-16 08:24:56 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1le.20.1.2][1] | Need the phase scope and design file | 3 |
| read-by | [agent:sase-1le.20.1.7][2] | Need the docs-split tooling scope to route the mypy failure correctly | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.7/README.md

<!-- sase:referenced-by:end -->
