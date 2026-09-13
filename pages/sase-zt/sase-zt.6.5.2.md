# Bead: sase-zt.6.5.2 — Pin the integrated core and prove LaunchApproval preserves capacity

[Bead Pages](../README.md) / [sase-zt.6.5](sase-zt.6.5.md) / sase-zt.6.5.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zt.6.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zt.6.land.md) · **Assignee:** `sase-zt.6.5.2` · **Size:** medium
**Created:** 2026-09-13 14:29:57 EDT · **Closed:** 2026-09-13 16:29:17 EDT
**Plan:** [202609/queue\_capacity\_final\_integration.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_capacity_final_integration.md)

## Description

pin-and-launch: ratchet the current core cohort and repair or disprove the reported agent-skill LaunchApproval capacity loss through typed request and dispatch boundaries.

## Notes

[2026-09-13T19:33:35Z · sase-zt.6.5.2--1] PROPOSED FOLLOW-UP: live flag bead sase-zx (agents_deferred_history) has no registry definition past the 24h orphan grace, so just check lint (feature flags) is red — authored by sase-zu.2; sase-101 and sase-107 still warn inside grace

[2026-09-13T20:29:17Z · sase-zt.6.5.2--2] verified main faad5c3dc3f00539ab9ef8441aabf7b9de2153a0, core pin 7f43a996e9393449e838881f907d40fc76d0fdc6 with editable .pth under sase/repos/linked/sase-core, LaunchApproval queue_capacity typed-plan/dispatch path, just check passed; focused pinned tests passed

## Dependencies

- **Depends on:** [sase-zt.6.5.1](sase-zt.6.5.1.md) ✓ · ⧖ 2026-09-13
- **Blocks:** [sase-zt.6.5.3](sase-zt.6.5.3.md) ✓ · ⧖ 2026-09-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zt.6.5.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zt.6.5.2.md) | [sase-zt.6.5.2](sase-zt.6.5.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3224d46`](https://github.com/sase-org/sase/commit/3224d4611d43a88be0ec4849693ee574b1c95ea9) | fix(agent): preserve launch approval queue capacity | [sase-zt.6.5.2](sase-zt.6.5.2.md) | 2026-09-13 16:31:14 EDT |
