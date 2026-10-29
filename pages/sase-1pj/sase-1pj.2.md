# Bead: sase-1pj.2 — Handoff descriptor and carry disposition in the finalizer wire

[Bead Pages](../README.md) / [sase-1pj](README.md) / sase-1pj.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5f.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5f.linker.w0.md) · **Assignee:** `sase-1pj.2` · **Size:** large
**Created:** 2026-10-28 20:28:58 EDT
**Plan:** [202610/staged\_handoffs.md](https://github.com/sase-org/sase--plans/blob/main/202610/staged_handoffs.md)

## Description

handoff-wire: add a handoff descriptor to the sase-core finalizer context, a carry repository decision legal only for same-workspace handoffs, the prepared-intent rule, host-synthesized carry, commit-finalizer support, and the revision pin move.

## Notes

[2026-10-29T15:43:58Z · sase-1pj.2.1.4] PREPARED-BRIDGE RESERVATION CONTRACT: persist these facts in the staged record payload *before* publishing the staged record; do not bind at staging time. Payload keys: prepared_intent_ref (artifact ref, local ref, or intent id accepted by load_prepared_completion) and prepared_reservation {staged_id, monitor_id, request_fingerprint, command} matching PreparedReservationWire. staged_id is the staged record UUID; command is the exact argv that will start; the intent stays in lifecycle state prepared until spawn binds it. Adapter: src/sase/finalizers/prepared_coverage.py. This child does not launch, reserve, or bind ToolRuns and does not change monitor/start_flow.py.

## Dependencies

- **Depends on:** [sase-1pj.1](sase-1pj.1.md) ✓ · ⧖ 2026-10-28
- **Blocks:** [sase-1pj.3](sase-1pj.3.md) ◐ · ⧖ 2026-10-28
- **Blocks:** [sase-1pj.4](sase-1pj.4.md) ◐ · ⧖ 2026-10-28
- **Blocks:** [sase-1pj.5](sase-1pj.5.md) ◐ · ⧖ 2026-10-28
- **Blocks:** [sase-1pj.7](sase-1pj.7.md) ◐ · ⧖ 2026-10-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.2.md) | [sase-1pj.2](sase-1pj.2.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pj.2.1.2][1] | Need parent DECISIONS and closed phase notes | 2 |
| read-by | [agent:sase-1pj.2.1.3][2] | Need parent epic decisions and cross-phase boundaries | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.2.1.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.2.1.3/README.md

<!-- sase:referenced-by:end -->
