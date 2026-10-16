# Bead: sase-1le.20.1.9 — Move beads, plans, goals, Patches, and ProjectSpec into reference/work-units/

[Bead Pages](../README.md) / [sase-1le.20.1](sase-1le.20.1.md) / sase-1le.20.1.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1le.20](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.20.md) · **Assignee:** `sase-1le.20.1.9` · **Size:** medium
**Created:** 2026-10-16 08:04:37 EDT · **Closed:** 2026-10-16 11:55:45 EDT
**Plan:** [202610/docs\_decompose.md](https://github.com/sase-org/sase--plans/blob/main/202610/docs_decompose.md)

## Description

work-units-move: split beads.md and sdd.md and move goals.md, change_spec.md, and project_spec.md into reference/work-units/ with a hub.

## Notes

[2026-10-16T15:55:20Z · sase-1le.20.1.9] PROPOSED FOLLOW-UP: Triage with the identical clean-base proposal in sase-1le.20.1.13 note #5: ToolRun e659cb6f6ad709c2766f4a87ec3d4da8 passes formatting through Ruff, then fails on the same nine extensionless-tool mypy errors; loading HEAD docs_split into the same typecheck reproduces byte-identical output. No task bead tracks these nine; sase-18q is a separate mypy failure in tools/sase_core_wheel_cache.

[2026-10-16T15:55:45Z · sase-1le.20.1.9] Completed the work-unit page splits and moves, hub, navigation, compatibility stubs, and named source/test references. Verified strict docs build and URL contract (1,976 URLs), git diff --check, and no epic-symbol leftovers. sase tool run check passes through Ruff, then fails on nine extensionless-tool mypy errors; running the same typecheck with HEAD's unchanged docs_split reproduces the identical errors. Recorded the existing proposal reference in this bead's notes.

## Dependencies

- **Blocks:** [sase-1le.20.1.15](sase-1le.20.1.15.md) ◐ · ⧖ 2026-10-16
- **Blocks:** [sase-1le.20.1.18](sase-1le.20.1.18.md) ✓ · ⧖ 2026-10-16
- **Depends on:** [sase-1le.20.1.8](sase-1le.20.1.8.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.20.1.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.9/README.md) | [sase-1le.20.1.9](sase-1le.20.1.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5937cbc`](https://github.com/sase-org/sase/commit/5937cbc13066562a9a4b235831e76574e46e37ee) | docs(reference): split work unit documentation | [sase-1le.20.1.9](sase-1le.20.1.9.md) | 2026-10-16 11:57:26 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1le.20.1.9][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.9/README.md

<!-- sase:referenced-by:end -->
