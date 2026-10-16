# Bead: sase-1le.20.1.8 — Move macros.md and workflow\_spec.md into reference/macros/

[Bead Pages](../README.md) / [sase-1le.20.1](sase-1le.20.1.md) / sase-1le.20.1.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1le.20](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.20.md) · **Assignee:** `sase-1le.20.1.8` · **Size:** medium
**Created:** 2026-10-16 08:04:37 EDT · **Closed:** 2026-10-16 11:03:04 EDT
**Plan:** [202610/docs\_decompose.md](https://github.com/sase-org/sase--plans/blob/main/202610/docs_decompose.md)

## Previously Closed

> ↺ Closed 2026-10-16T14:37:45Z · done
>
> (none)
>
> Reopened 2026-10-16T14:44:34Z by a status update

## Description

macros-move: split macros.md into reference/macros/ pages beside the generated catalogs, move workflow_spec.md to reference/workflows.md, keep the decision-cited macros.md stub, and update the macros.md memory pointer.

## Notes

[2026-10-16T14:36:49Z · sase-1le.20.1.8] PROPOSED FOLLOW-UP: Repair the nine extensionless-tool mypy errors — ToolRun 3089f55d086e99894ce381b61051bb06 still stops at lint (mypy) in tools/docs_split and tools/render_keymap_macro_reference; the identical clean-base failure and absence of a matching task bead are recorded in sase-1le.20.1.3 note #1 and sase-1le.20.1.7 note #1.

[2026-10-16T14:37:45Z · sase-1le.20.1.8] Moved and split the macro and workflow reference docs; strict docs-check passed, focused docs-move tests passed (9/9), generated docs checks and diff whitespace checks passed. just check reaches the documented nine clean-base extensionless-tool mypy errors; recorded as a proposed follow-up. No epic symbols remain.

[2026-10-16T14:44:36Z · bryanbugyi34@gmail.com] I'm not sure if this work is completed or not but the agent that was attempting to work on it failed.

[2026-10-16T15:02:36Z · sase-1le.20.1.8] PROPOSED FOLLOW-UP: Repair the nine extensionless-tool mypy errors that stop ToolRun 100b6781b3a6a78cc360bdf96ce1fd4f at lint (mypy) in tools/docs_split and tools/render_keymap_macro_reference; this reproduces the clean-base failure already recorded in phase note #1, and no matching task bead is known.

[2026-10-16T15:03:04Z · sase-1le.20.1.8] Moved macros.md into reference/macros pages and workflow_spec.md to reference/workflows.md; updated links, nav, stubs, docs map, and the authorized macros memory pointer. just docs-check passed its strict build and all 1,041 URL checks; split destinations are within budget, /macros/#auto-directive resolves, and epic-symbols reports no leftovers. ToolRun 100b6781b3a6a78cc360bdf96ce1fd4f stopped at the nine pre-existing extensionless-tool mypy errors; recorded as a proposed follow-up.

## Dependencies

- **Blocks:** [sase-1le.20.1.17](sase-1le.20.1.17.md) ◐ · ⧖ 2026-10-16
- **Depends on:** [sase-1le.20.1.7](sase-1le.20.1.7.md) ✓ · ⧖ 2026-10-16
- **Blocks:** [sase-1le.20.1.9](sase-1le.20.1.9.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.20.1.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.8/README.md) | [sase-1le.20.1.8](sase-1le.20.1.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`deaa5d2`](https://github.com/sase-org/sase/commit/deaa5d22dd7c0c3f2d5c2497a38882f878c2e03f) | docs(reference): split macro and workflow documentation | [sase-1le.20.1.8](sase-1le.20.1.8.md) | 2026-10-16 11:22:54 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1le.20.1.8][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.8/README.md

<!-- sase:referenced-by:end -->
