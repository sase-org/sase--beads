# Bead: sase-1jx.11 — Projects-tab entry points and integration

[Bead Pages](../README.md) / [sase-1jx](README.md) / sase-1jx.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.49.linker.w1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.49.linker.w1.md) · **Assignee:** `sase-1jx.11` · **Size:** medium
**Created:** 2026-10-11 11:13:49 EDT · **Closed:** 2026-10-12 09:47:20 EDT
**Plan:** [202610/new\_project\_wizard.md](https://github.com/sase-org/sase--plans/blob/main/202610/new_project_wizard.md)

## Description

tui-entry: wire `n` (keymaps, default_config, schema, help), the palette entry and empty-state card, priority-truncated hints, and post-completion reload, selection and launch integration; document the wizard.

## Notes

[2026-10-12T13:47:04Z · sase-1jx.11] PROPOSED FOLLOW-UP: Triage unrelated clean-base failures from just check — agent project-display label assertions already tracked by sase-1k4; 3517-versus-3513 TUI import budget already tracked by sase-1ic; saved-agent-group preview copy assertion still expects 250 most recent dismissed agents while current copy says load recent dismissed agents then filter, with no matching bead found. The parallel todo-highlight failure passed the clean-base targeted rerun and is already tracked as intermittent by sase-xh; the _load_archive_bundle Symvision private-import failure is already tracked under sase-1jm.

[2026-10-12T13:47:20Z · sase-1jx.11] Implemented the Projects-tab New Project entry and integration. Verified just fmt, git diff --check, 227 focused tests, and targeted visual snapshots. The phase-local catalog/help failures from the initial just check were fixed and their focused tests pass. just check still reports unrelated clean-base failures and known Symvision findings recorded in this phase follow-up; epic-symbols was empty.

## Dependencies

- **Depends on:** [sase-1jx.10](sase-1jx.10.md) ✓ · ⧖ 2026-10-11
- **Blocks:** [sase-1jx.12](sase-1jx.12.md) ◐ · ⧖ 2026-10-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jx.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.11/README.md) | [sase-1jx.11](sase-1jx.11.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e4b3a85`](https://github.com/sase-org/sase/commit/e4b3a85f4ea576c97e8ed87b220ba6d5a778cfa0) | feat(ace): add Projects wizard entry and launch flow | [sase-1jx.11](sase-1jx.11.md) | 2026-10-12 09:48:31 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jx.10.1.4][1] | Need status of beads named by stale --epic-symbol rows that just check failed on | 1 |
| read-by | [agent:sase-1jx.11][2] | Need all phase notes and remaining work before implementing | 2 |
| read-by | [agent:sase-1jx.12.1.3--2][3] | Need the revival-preview follow-up bead citation from a sibling phase | 1 |
| read-by | [agent:sase-1jx.9--1][4] | Verify the entry integration phase is the later consumer of the modal and its selection result | 1 |
| read-by | [agent:sase-1ka.1][5] | verify unrelated closed bead behind symvision NEW failure | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.10.1.4/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.11/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.12.1.3.md
[4]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.9.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ka.1/README.md

<!-- sase:referenced-by:end -->
