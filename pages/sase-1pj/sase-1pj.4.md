# Bead: sase-1pj.4 — Stage gate, sudo, launch, run, and workflow HITL gates

[Bead Pages](../README.md) / [sase-1pj](README.md) / sase-1pj.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5f.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5f.linker.w0.md) · **Assignee:** `sase-1pj.4` · **Size:** large
**Created:** 2026-10-28 20:28:58 EDT
**Plan:** [202610/staged\_handoffs.md](https://github.com/sase-org/sase--plans/blob/main/202610/staged_handoffs.md)

## Description

gate-staging: split gate-turn creation into CLI-time validate/stage and post-finalizer publish for every gate entry point, keeping %auto gates inline and moving the one-handoff guard ahead of publication.

## Notes

[2026-10-30T09:08:54Z · sase-1pj.4.1.land] READY TO CLOSE after child epic sase-1pj.4.1 closes (sase-1pj.4.1.land): checked the gate-staging scope from plan:202610/staged_handoffs.md against the landed code. The create_gate_turn split into stage/publish uses persisted creator context and request-id replay. %auto stays synchronous with no staged record, and LaunchApproval rejects auto at stage time. One shared entry helper serves gate_handler, sudo cli, launch_handler/launch_request, query_handler/_launch, and workflow_hitl/_gate. The staged descriptor carries request_id and status: staged with no member or notification id, and own-stage sase gate wait is refused. carry_allowed follows workspace mode. No gate-intent marker is written on the staged path. sase_gate/sase_sudo/sase_run use dual-state wording. Both flag states are tested. sase-1pj.4.1's close is routed through host completion (bead_action close) on the commit that removes its last --epic-symbol rows, since the upstream-union guard refuses an in-turn close until that commit reaches origin/master. Once sase-1pj.4.1 shows CLOSED and sase bead epic-symbols sase-1pj.4 is empty, close this phase normally with sase bead close sase-1pj.4; do not close sase-1pj.

## Dependencies

- **Depends on:** [sase-1pj.1](sase-1pj.1.md) ✓ · ⧖ 2026-10-28
- **Depends on:** [sase-1pj.2](sase-1pj.2.md) ✓ · ⧖ 2026-10-28
- **Blocks:** [sase-1pj.6](sase-1pj.6.md) ◐ · ⧖ 2026-10-28
- **Blocks:** [sase-1pj.7](sase-1pj.7.md) ◐ · ⧖ 2026-10-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.4.md) | [sase-1pj.4](sase-1pj.4.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pj.4.1.2][1] | Need parent phase DECISIONS that this child must honor | 1 |
| read-by | [agent:sase-1pj.4.1.3][2] | Need the containing epic's decisions for the assigned child phase | 2 |
| read-by | [agent:sase-1pj.4.1.4][3] | Need containing phase DECISIONS and remaining work notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.4.1.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.4.1.3/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.4.1.4/README.md

<!-- sase:referenced-by:end -->
