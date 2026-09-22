# Bead: sase-16h.1 — Make an agent an ownership root and always export the wrapper marker

[Bead Pages](../README.md) / [sase-16h](README.md) / sase-16h.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pf](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pf.md) · **Assignee:** `sase-16h.1` · **Size:** medium
**Created:** 2026-09-22 13:05:39 EDT · **Closed:** 2026-09-22 13:52:00 EDT
**Plan:** [202609/tool\_e15\_enforced\_adoption.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e15_enforced_adoption.md)

## Description

ownership-roots: scrub executor-ownership variables at every agent launch, ignore an inherited monitor/proc id under SASE_AGENT, always export SASE_TOOL_NAME and SASE_TOOL_PROJECT_ROOT, and carry a monitor's starter agent into its recorded runs.

## Notes

[2026-09-22T17:51:18Z · sase-16h.1] PROPOSED FOLLOW-UP: just check scoped lane shows 3 pre-existing failures unrelated to ownership-roots (TUI geometry 100!=160, shard-table drift 4339 vs 3513 committed, plugins batch path) — detail in tool run 924b504b9b0d1dea494942efa6bb771c

[2026-09-22T17:52:00Z · sase-16h.1] ownership-roots done: scrub_executor_ownership_env wired into launch_spawn/admission_coordinator/condition_runtime; resolve_ownership drops inherited monitor/proc/parent ids under SASE_AGENT; child_env always exports SASE_TOOL_NAME/PROJECT_ROOT; monitor starter carried via SASE_TOOL_RUN_AGENT with begin_tool_run fallback. Tests: 15 focused + 73 tool + 134 agent + 11 monitor-start pass; ruff/mypy/symvision clean; epic-symbols empty. just check (run 924b504b) shows only 3 pre-existing failures (TUI x2, shard drift 826 files vs my 1 new file). Epic launcher verified to read SASE_MONITOR_ARTIFACTS_DIR in own process only.

## Dependencies

- **Blocks:** [sase-16h.2](sase-16h.2.md) ◐ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16h.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16h.1/README.md) | [sase-16h.1](sase-16h.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b33732a`](https://github.com/sase-org/sase/commit/b33732a41d3b981e515c5db06cc57e2382ad526d) | feat(ownership): scrub executor ownership env at agent-launch boundaries | [sase-16h.1](sase-16h.1.md) | 2026-09-22 13:56:02 EDT |
