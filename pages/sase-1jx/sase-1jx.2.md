# Bead: sase-1jx.2 — Additive workspace-provider hooks and bare-git implementations

[Bead Pages](../README.md) / [sase-1jx](README.md) / sase-1jx.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.49.linker.w1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.49.linker.w1.md) · **Assignee:** `sase-1jx.2` · **Size:** medium
**Created:** 2026-10-11 11:13:44 EDT · **Closed:** 2026-10-11 16:52:03 EDT
**Plan:** [202610/new\_project\_wizard.md](https://github.com/sase-org/sase--plans/blob/main/202610/new_project_wizard.md)

## Description

provider-hooks: add the five onboarding hookspecs (parse, local candidates, probe, describe creation, create) with their frozen dataclasses, manager methods, registry wrappers and argument pins; extend the repo-candidate dataclasses and cache (host, truncated, remedy, repo id, push permission); implement every new hook for built-in bare git.

## Notes

[2026-10-11T20:51:53Z · sase-1jx.2--1] PROPOSED FOLLOW-UP: Triage the baseline TUI import-budget failure already tracked by sase-1ic — ToolRun 4ee935c6dff4adc169e70ba0745a5f38 had 5 failures and 54,710 passes; on clean base ca75ae237d742358161cf5fcf9915ebe5f2d1a85, four targeted failures passed and test_app_import_stays_under_startup_budget reproduced at 3516 modules vs the <3513 cap, matching sase-1ic.

[2026-10-11T20:52:03Z · sase-1jx.2--1] Implemented additive workspace-provider onboarding hooks, bare-git create/probe/form behavior, host-aware completion caching, docs, and authorized glossary update. just fmt passed; focused provider/completion/bare-git suite passed 134 tests, including the empty pre-created bare repository case. sase tool run check exited 1 after 54,710 passed, 17 skipped, 5 failures; the five were rerun on clean base, where four passed and the TUI import budget failure reproduced identically at 3516 modules vs the <3513 cap. Recorded the existing sase-1ic baseline failure as a PROPOSED FOLLOW-UP. No epic-symbol entries remain.

## Dependencies

- **Blocks:** [sase-1jx.5](sase-1jx.5.md) ✓ · ⧖ 2026-10-11
- **Blocks:** [sase-1jx.6](sase-1jx.6.md) ◐ · ⧖ 2026-10-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jx.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.2.md) | [sase-1jx.2](sase-1jx.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2b576ef`](https://github.com/sase-org/sase/commit/2b576ef33c54eac46cd35f1c5b298067450904ad) | feat(workspace): add repository onboarding hooks | [sase-1jx.2](sase-1jx.2.md) | 2026-10-11 16:56:58 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jx.2--1][1] | Need the phase scope, design file, and prior notes before continuing assigned work | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.2.md

<!-- sase:referenced-by:end -->
