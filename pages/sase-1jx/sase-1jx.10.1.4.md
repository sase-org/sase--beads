# Bead: sase-1jx.10.1.4 — Apply, progress, Ready, and Failed

[Bead Pages](../README.md) / [sase-1jx.10.1](sase-1jx.10.1.md) / sase-1jx.10.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jx.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.10.md) · **Assignee:** `sase-1jx.10.1.4` · **Size:** medium
**Created:** 2026-10-12 04:39:47 EDT · **Closed:** 2026-10-12 07:22:15 EDT
**Plan:** [202610/new\_project\_add\_existing.md](https://github.com/sase-org/sase--plans/blob/main/202610/new_project_add_existing.md)

## Description

apply-ready: submit durable project add, tail its checklist, and finish on Ready or Failed including the init hand-off.

## Notes

[2026-10-12T11:21:56Z · sase-1jx.10.1.4] PROPOSED FOLLOW-UP: tests/ace/tui/test_app_import_budget.py fails 3517 vs 3513 cap with +0 sase.* modules vs merge-base (tools/tui_import_closure --diff); New Project apply modules are not on the TUI app import path. Same pre-existing drift sase-1jx.8 already noted (3518 vs 3513).

[2026-10-12T11:22:15Z · sase-1jx.10.1.4] Durable New Project apply is live: y submits project.add via Attribute app._submit_durable_proc (producer site projects.add, operation=project.add, reload_on_complete=False, dismiss still reloads); Progress tails the proc (250ms poll, pump-free, tails while log.version stays 0); Ready (+/c/enter/i) and Failed (r/t/b) with chrome hints; ok/partial with init next_argv calls run_project_init(NewProjectInitHost, InitScope.for_projects); cancel/error stay on Ready needs_init. 21 unit tests passed; 4 PNG goldens captured. just check 304e841ee465200cdaa4e4309fe90cc4: fmt/ruff/mypy/symvision green; 55105 passed; 1 NEW import-budget 3517 vs 3513 is +0 vs merge-base (PROPOSED FOLLOW-UP, also on sase-1jx.8); remaining failures KNOWN. sase bead epic-symbols sase-1jx.10.1.4: none left. Did not close parent sase-1jx.10.1.

## Dependencies

- **Depends on:** [sase-1jx.10.1.2](sase-1jx.10.1.2.md) ✓ · ⧖ 2026-10-12
- **Depends on:** [sase-1jx.10.1.3](sase-1jx.10.1.3.md) ✓ · ⧖ 2026-10-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jx.10.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.10.1.4/README.md) | [sase-1jx.10.1.4](sase-1jx.10.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`558a45e`](https://github.com/sase-org/sase/commit/558a45eca47b9e44b31c61f5f318333eae899c4f) | feat(tui): add durable New Project apply, Progress, Ready, and Failed | [sase-1jx.10.1.4](sase-1jx.10.1.4.md) | 2026-10-12 07:55:53 EDT |
