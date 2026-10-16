# Bead: sase-1le.20.1.11 — Move scheduler, notifications, monitors, tools, mentors, and sudo pages

[Bead Pages](../README.md) / [sase-1le.20.1](sase-1le.20.1.md) / sase-1le.20.1.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1le.20](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.20.md) · **Assignee:** `sase-1le.20.1.11` · **Size:** medium
**Created:** 2026-10-16 08:04:37 EDT · **Closed:** 2026-10-16 11:16:58 EDT
**Plan:** [202610/docs\_decompose.md](https://github.com/sase-org/sase--plans/blob/main/202610/docs_decompose.md)

## Description

automation-move: split notifications.md, axe.md, monitors.md, and the decision-cited tool.md, and move mentors.md and sudo.md into reference/automation/, with epic-labelled internals going to contribute/.

## Notes

[2026-10-16T15:16:44Z · sase-1le.20.1.11] PROPOSED FOLLOW-UP: Repair the nine unchanged clean-base extensionless-tool mypy errors — the final check reproduces 5 in tools/render_keymap_macro_reference:303-306 and 4 in tools/docs_split:488, 674, 685, 794; same issue is proposed on phase sase-1le.20.1.13 note #1, and no task bead tracks these exact errors (task sase-iw tracks the checker gate).

[2026-10-16T15:16:58Z · sase-1le.20.1.11] Moved notifications, scheduler, monitors, named tools, mentors, and sudo docs into the automation reference/contribute pages; verified just docs-lint and just docs-check pass, git diff --check passes, and epic-symbol scan has no entries. sase tool run check reaches only the unchanged extensionless-tool mypy failures recorded as a proposed follow-up.

## Dependencies

- **Depends on:** [sase-1le.20.1.10](sase-1le.20.1.10.md) ✓ · ⧖ 2026-10-16
- **Blocks:** [sase-1le.20.1.15](sase-1le.20.1.15.md) ✓ · ⧖ 2026-10-16
- **Blocks:** [sase-1le.20.1.19](sase-1le.20.1.19.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.20.1.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.11/README.md) | [sase-1le.20.1.11](sase-1le.20.1.11.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0e667d9`](https://github.com/sase-org/sase/commit/0e667d98c2450663e7c052423a7130e7e8000e2e) | feat(docs): move automation pages into reference | [sase-1le.20.1.11](sase-1le.20.1.11.md) | 2026-10-16 11:18:04 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1le.20.1.11][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.11/README.md

<!-- sase:referenced-by:end -->
