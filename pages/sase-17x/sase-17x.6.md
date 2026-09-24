# Bead: sase-17x.6 — Command-line proc plumbing

[Bead Pages](../README.md) / [sase-17x](README.md) / sase-17x.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qs](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qs.md) · **Assignee:** `sase-17x.6` · **Size:** medium
**Created:** 2026-09-24 11:29:25 EDT · **Closed:** 2026-09-24 12:49:05 EDT
**Plan:** [202609/command\_line\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_panel.md)

## Description

proc-plumbing: add `submit_command_line_proc` (a tagged ordinary proc with the output env contract and no operation), an observer exit watch, ref-counted tails, an offset-based `ProcLogCursor`, `ObservedProc.tags` with a Procs `tag:` query field, and an Admin Center proc focus target.

## Notes

[2026-09-24T16:49:05Z · sase-17x.6] proc-plumbing done: submit_command_line_proc with tag/origin/env contract; observer exit watch (ProcExitCompletion) + ref-counted tails (set_detail_proc kept as shim); ProcLogCursor with rotation recovery; ObservedProc.tags plumbed; Procs tag:/origin: fields + docs; proc_focus_target threaded to Procs pane with filter-clear notice. Verified: 182 focused tests + 217 related tests green, ruff/mypy clean, no symvision findings in touched files, no epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-17x.4](sase-17x.4.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17x.7](sase-17x.7.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.6/README.md) | [sase-17x.6](sase-17x.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`70afac5`](https://github.com/sase-org/sase/commit/70afac5176b90b4c7cad6590b4199ad295fc14cb) | feat(cmdline): command-line proc plumbing (sase-17x.6) | [sase-17x.6](sase-17x.6.md) | 2026-09-24 12:50:35 EDT |
