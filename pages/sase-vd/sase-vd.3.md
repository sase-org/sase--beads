# Bead: sase-vd.3 — One workspace identity per runner

[Bead Pages](../README.md) / [sase-vd](README.md) / sase-vd.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ft](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ft.md) · **Assignee:** `sase-vd.3` · **Size:** medium
**Created:** 2026-08-28 18:06:19 EDT
**Plan:** [202608/one\_workspace\_per\_agent\_family.md](https://github.com/sase-org/sase--plans/blob/main/202608/one_workspace_per_agent_family.md)

## Description

single-workspace-identity: when a VCS workflow legitimately allocates a workspace for a runner that had none (deferred/`#0` launches), rebind the runner's own workspace identity to it so `done.json`, the checkout occupant record, monitor start, and shell member meta all name the directory the agent actually works in, rather than leaving `workspace_num` pointing at the launcher's slot while only `step_output.meta_workspace` knows the truth.

## Dependencies

- **Depends on:** [sase-vd.1](sase-vd.1.md) ✓ · ⧖ 2026-08-28
- **Blocks:** [sase-vd.4](sase-vd.4.md) ◐ · ⧖ 2026-08-28
- **Blocks:** [sase-vd.5](sase-vd.5.md) ◐ · ⧖ 2026-08-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-vd.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vd.3/README.md) | [sase-vd.3](sase-vd.3.md) | 0 |
