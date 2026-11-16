# Bead: sase-1t2.13 — Boundary chaos test, crash convergence, and hand-off inventory guard

[Bead Pages](../README.md) / [sase-1t2](README.md) / sase-1t2.13

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1ct](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ct.md) · **Assignee:** `sase-1t2.13` · **Size:** medium
**Created:** 2026-11-15 20:00:12 EST
**Plan:** [202611/agent\_hijack\_dependability.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack_dependability.md)

## Description

chaos: a scripted fakey session (agent, sleep monitor, agent) that fires hijack at every checkpoint and requires HIJACKED, latched, or a defined redirect, never a generic refusal; crash-between-steps convergence tests; and a static guard test that fails when a new successor-launch path lacks a latch checkpoint.

## Dependencies

- **Depends on:** [sase-1t2.10](sase-1t2.10.md) ◐ · ⧖ 2026-11-15
- **Depends on:** [sase-1t2.11](sase-1t2.11.md) ◐ · ⧖ 2026-11-15
- **Blocks:** [sase-1t2.14](sase-1t2.14.md) ◐ · ⧖ 2026-11-15
- **Depends on:** [sase-1t2.9](sase-1t2.9.md) ✓ · ⧖ 2026-11-15

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:ef][1] | Check cross-epic coordination between hijack epic sase-1t2 and TUI perf epic sase-1t3 | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ef/README.md

<!-- sase:referenced-by:end -->
