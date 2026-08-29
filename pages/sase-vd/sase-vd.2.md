# Bead: sase-vd.2 — Pre-allocation survives shell follow-up launches

[Bead Pages](../README.md) / [sase-vd](README.md) / sase-vd.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ft](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ft.md) · **Assignee:** `sase-vd.2` · **Size:** medium
**Created:** 2026-08-28 18:06:19 EDT · **Closed:** 2026-08-28 18:43:58 EDT
**Plan:** [202608/one\_workspace\_per\_agent\_family.md](https://github.com/sase-org/sase--plans/blob/main/202608/one_workspace_per_agent_family.md)

## Description

preallocate-shell-followups: record the starter's VCS workflow ref in shell member meta and thread it through `launch_shell_followup`, `spawn_family_successor`, and `spawn_detached_child` so a gate-, monitor-, or proc-shell follow-up whose composed prompt still carries `#gh:`/`#git:` is spawned with the `SASE_<VCS>_PRE_ALLOCATED` env the launcher already knows how to emit, instead of silently re-running VCS setup with no pre-allocation.

## Notes

[2026-08-28T22:43:58Z · sase-vd.2] Verified pre-allocation survives shell follow-up launches: starter VCS ref is recorded in agent_meta, inherited onto gate/monitor members, and threaded through launch_shell_followup -> spawn_family_successor -> spawn_detached_child. A #gh:-carrying gate-shell follow-up is spawned with SASE_GH_PRE_ALLOCATED=1 and matching _WORKSPACE_NUM/_WORKSPACE_DIR; degraded #0 fallback advertises workspace 0; non-VCS follow-ups set none of the three env vars; older shells recover the ref from the composed prompt via get_embedded_vcs_tag_pattern. just check passed (lint + scoped tests, escalated full suite). No leftover --epic-symbol entries for this phase.

## Dependencies

- **Blocks:** [sase-vd.5](sase-vd.5.md) ◐ · ⧖ 2026-08-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-vd.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vd.2/README.md) | [sase-vd.2](sase-vd.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0235ff0`](https://github.com/sase-org/sase/commit/0235ff059ad3e5e87156508fd10bf43f7dbcade6) | feat(shells): pre-allocate VCS workspace on family follow-up launches | [sase-vd.2](sase-vd.2.md) | 2026-08-28 18:45:13 EDT |
