# Bead: sase-vd.2 — Pre-allocation survives shell follow-up launches

[Bead Pages](../README.md) / [sase-vd](README.md) / sase-vd.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ft](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ft.md) · **Assignee:** `sase-vd.2` · **Size:** medium
**Created:** 2026-08-28 18:06:19 EDT
**Plan:** [202608/one\_workspace\_per\_agent\_family.md](https://github.com/sase-org/sase--plans/blob/main/202608/one_workspace_per_agent_family.md)

## Description

preallocate-shell-followups: record the starter's VCS workflow ref in shell member meta and thread it through `launch_shell_followup`, `spawn_family_successor`, and `spawn_detached_child` so a gate-, monitor-, or proc-shell follow-up whose composed prompt still carries `#gh:`/`#git:` is spawned with the `SASE_<VCS>_PRE_ALLOCATED` env the launcher already knows how to emit, instead of silently re-running VCS setup with no pre-allocation.

## Dependencies

- **Blocks:** [sase-vd.5](sase-vd.5.md) ◐ · ⧖ 2026-08-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-vd.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vd.2/README.md) | [sase-vd.2](sase-vd.2.md) | 0 |
