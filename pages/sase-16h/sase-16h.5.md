# Bead: sase-16h.5 — Wrap a monitor's command in sase tool run

[Bead Pages](../README.md) / [sase-16h](README.md) / sase-16h.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pf](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pf.md) · **Assignee:** `sase-16h.5` · **Size:** medium
**Created:** 2026-09-22 13:05:43 EDT · **Closed:** 2026-09-22 17:54:07 EDT
**Plan:** [202609/tool\_e15\_enforced\_adoption.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e15_enforced_adoption.md)

## Description

monitor-wrap: upgrade an exact catalog match to a named run and wrap other verify-profile commands ad-hoc, in the proc argv only, behind a monitor.tool_wrap config field, leaving monitor_command and host completion bindings untouched.

## Notes

[2026-09-22T21:53:38Z · sase-16h.5] PROPOSED FOLLOW-UP: symvision flags delete_paths_in_background in src/sase/_linked_repo_workspaces.py (public, used only in-file; pre-existing on this tree, last touched by axe commit 505934a63) — privatize or delete per symvision hierarchy so just check goes green

[2026-09-22T21:54:07Z · sase-16h.5] monitor-wrap landed: proc-argv-only wrap behind monitor.tool_wrap (off|verify|all, default verify) with named catalog upgrade at the monitor cwd root and ad-hoc /bin/sh -c otherwise; monitor_command/execution_argv byte-identical; one running-unwrapped log line per policy decline; SASE_TOOL_BYPASS honored. Verified: 24 new tests in tests/monitor/test_monitor_tool_wrap.py pass (named run records owner monitor + starter, single ad-hoc run, no re-wrap, -f argv intact, auto evidence tail), full tests/monitor (364) + tests/tool/config suites green, ruff/mypy/symvision clean for touched symbols, sase skill init preview clean. just check red only on pre-existing delete_paths_in_background symvision flag (filed as PROPOSED FOLLOW-UP). No epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-16h.4](sase-16h.4.md) ✓ · ⧖ 2026-09-22
- **Blocks:** [sase-16h.6](sase-16h.6.md) ✓ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16h.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16h.5/README.md) | [sase-16h.5](sase-16h.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6167ec4`](https://github.com/sase-org/sase/commit/6167ec42cb1df33bb670ddf3d9c81ea75303a9c2) | feat(monitor): wrap supervised commands in sase tool run | [sase-16h.5](sase-16h.5.md) | 2026-09-22 17:56:24 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16h.5][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16h.5/README.md

<!-- sase:referenced-by:end -->
