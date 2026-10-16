# Bead: sase-1le.20.1.4 — Move the Agents tab sections of ace.md to reference/tui/

[Bead Pages](../README.md) / [sase-1le.20.1](sase-1le.20.1.md) / sase-1le.20.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1le.20](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.20.md) · **Assignee:** `sase-1le.20.1.4` · **Size:** medium
**Created:** 2026-10-16 08:04:35 EDT · **Closed:** 2026-10-16 09:44:54 EDT
**Plan:** [202610/docs\_decompose.md](https://github.com/sase-org/sase--plans/blob/main/202610/docs_decompose.md)

## Description

tui-agents-move: move-only partial split of the Agents tab cluster of ace.md (about 35K words) into budget-sized reference/tui/ pages.

## Notes

[2026-10-16T13:25:18Z · sase-1le.20.1.4] PROPOSED FOLLOW-UP: docs_split _unique_anchor emits -N suffixes but MkDocs renders _N, so H1/H2 title collisions need hand-added explicit ids (seen on agent-row-glyphs, agent-statuses, agents-main-deck) -r Recording tool mismatch found during verification

[2026-10-16T13:44:35Z · sase-1le.20.1.4] PROPOSED FOLLOW-UP: sase tool run check fails at lint (mypy) with 9 pre-existing errors in tools/render_keymap_macro_reference (5) and tools/docs_split (4); reproduced identically on clean base a0ad470045, no tracking bead found -r Recording clean-base check failure per phase instructions

[2026-10-16T13:44:54Z · sase-1le.20.1.4] tui-agents-move done: 12 ace.md Agents-tab H2s split into 9 budget-clean reference/tui pages plus hub via docs/_meta/splits/tui_agents.yml; ace.md keeps pointers, moves.yml anchors recorded, TUI nav group and reference/index hub repointed (kept at 400 words). Verified: just fix clean, just docs-lint ok, just docs-check strict build plus URL contract green (455 URLs), focused pytest (tribe terminology, wait-status counts) 21 passed, epic-symbols empty. Full sase tool run check stops at lint(mypy) with 9 errors that reproduce identically on clean base a0ad470045 (recorded as PROPOSED FOLLOW-UP).

## Dependencies

- **Depends on:** [sase-1le.20.1.3](sase-1le.20.1.3.md) ✓ · ⧖ 2026-10-16
- **Blocks:** [sase-1le.20.1.5](sase-1le.20.1.5.md) ◐ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.20.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.4/README.md) | [sase-1le.20.1.4](sase-1le.20.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d8b361b`](https://github.com/sase-org/sase/commit/d8b361b7d709940b42208310d07c215faea2f9f6) | feat(docs): move Agents tab sections of ace.md to reference/tui/ (sase-1le.20.1.4) | [sase-1le.20.1.4](sase-1le.20.1.4.md) | 2026-10-16 09:46:24 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1le.20.1.4][1] | check notes | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.4/README.md

<!-- sase:referenced-by:end -->
