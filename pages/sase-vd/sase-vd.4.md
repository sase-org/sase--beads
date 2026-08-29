# Bead: sase-vd.4 — VCS release never frees a workspace the family still holds

[Bead Pages](../README.md) / [sase-vd](README.md) / sase-vd.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ft](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ft.md) · **Assignee:** `sase-vd.4` · **Size:** medium
**Created:** 2026-08-28 18:06:20 EDT
**Plan:** [202608/one\_workspace\_per\_agent\_family.md](https://github.com/sase-org/sase--plans/blob/main/202608/one_workspace_per_agent_family.md)

## Description

handoff-safe-vcs-release: make the `#git:`/`#gh:` release step identity-checked and handoff-aware -- release only a claim this run's pid still owns, clear only an occupant record naming this run, and skip both entirely when the turn ended by handing off mechanically to a monitor, gate, proc shell, pipe, or plan proposal whose follow-up will continue in the same checkout.

## Dependencies

- **Depends on:** [sase-vd.3](sase-vd.3.md) ✓ · ⧖ 2026-08-28
- **Blocks:** [sase-vd.5](sase-vd.5.md) ◐ · ⧖ 2026-08-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-vd.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vd.4/README.md) | [sase-vd.4](sase-vd.4.md) | 0 |
