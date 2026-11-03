# Bead: sase-1pj.6 — Idempotent adoption, crash reconciliation, and re-adopt

[Bead Pages](../README.md) / [sase-1pj](README.md) / sase-1pj.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5f.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5f.linker.w0.md) · **Assignee:** `sase-1pj.6` · **Size:** large
**Created:** 2026-10-28 20:28:59 EDT · **Closed:** 2026-11-01 14:29:29 EST
**Plan:** [202610/staged\_handoffs.md](https://github.com/sase-org/sase--plans/blob/main/202610/staged_handoffs.md)

## Description

adoption-recovery: make adoption idempotent for every kind, reconcile staged handoffs whose runner died after finalization, and add a re-adopt command for handoffs held by failed finalization.

## Notes

[2026-11-01T19:30:01Z · sase-1pj.6.1.land--1] Parent-phase verification: its scoped objectives are covered by closed child epic sase-1pj.6.1 and all eight of that epic's phases: idempotent adoption for every handoff kind, reconciliation after a staged origin runner dies, and an explicit re-adopt command for held handoffs. The child epic close note records the landed phase commits, core pin ancestry, integration, focused tests, and check ToolRun. No --epic-symbol entries for sase-1pj.6. returned no entries. The child close command also closed this parent phase automatically; this note records the requested phase-specific verification. No containing epic or other ancestor was closed.

## Dependencies

- **Depends on:** [sase-1pj.1](sase-1pj.1.md) ✓ · ⧖ 2026-10-28
- **Depends on:** [sase-1pj.3](sase-1pj.3.md) ✓ · ⧖ 2026-10-28
- **Depends on:** [sase-1pj.4](sase-1pj.4.md) ✓ · ⧖ 2026-10-28
- **Depends on:** [sase-1pj.5](sase-1pj.5.md) ✓ · ⧖ 2026-10-28
- **Blocks:** [sase-1pj.8](sase-1pj.8.md) ✓ · ⧖ 2026-10-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.6.md) | [sase-1pj.6](sase-1pj.6.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pj.6.1.2][1] | Need governing epic decisions for this recovery phase | 1 |
| read-by | [agent:sase-1pj.6.1.4][2] | Need outer epic DECISIONS that this child epic must honor | 1 |
| read-by | [agent:sase-1pj.6.1.7][3] | Need parent phase scope and decisions for this child | 1 |
| read-by | [agent:sase-1pj.6.1.land--1][4] | Verify the parent adoption-recovery phase status and recorded close note after child epic close | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.6.1.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.6.1.4/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.6.1.7/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.6.1.land.md

<!-- sase:referenced-by:end -->
