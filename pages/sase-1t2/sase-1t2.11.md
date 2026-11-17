# Bead: sase-1t2.11 — Monitor hijack adapter (closes the screenshot case)

[Bead Pages](../README.md) / [sase-1t2](README.md) / sase-1t2.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1ct](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ct.md) · **Assignee:** `sase-1t2.11` · **Size:** large
**Created:** 2026-11-15 20:00:11 EST · **Closed:** 2026-11-17 04:45:00 EST
**Plan:** [202611/agent\_hijack\_dependability.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack_dependability.md)

## Description

monitor_adapter: running monitor turns become immediate through stop_monitor with a hijack intent; the settlement funnel suppresses --next, holds the workspace, and writes a hijacked done marker for proc-backed and legacy monitors; a settled monitor with a pending follow-up latches. Recovery offers Continue (recorded follow-up with untrusted partial output), Escalate, Re-run command, View, Shell, and Dismiss.

## Notes

[2026-11-16T20:25:20Z · sase-1t2.11] PLANNING HANDOFF: Checked existing work at sase b586776bf3 and the approved epic/research. Shared latch and recovery infrastructure has landed, but monitor eligibility still refuses, settlement has no hijack checkpoint, terminal writers overwrite outcome as monitored, and monitor recovery/rerun remain absent. Authored a seven-phase child epic with parent_bead=sase-1t2.11; both plan validations passed with zero warnings and sase plan propose reported Staged. No implementation files changed and no bead was closed. No epic-symbol entries currently belong to this phase. The child epic land workflow owns phase completion after implementation and verification.

[2026-11-17T08:17:55Z · sase-1t2.11.1.7] COMPLETION EVIDENCE from child land sase-1t2.11.1.7: monitor hijack adapter is enabled and verified. Running monitors decide immediate/adapter=monitor; pending-follow-up monitors latch at boundary=monitor. Recovery Continue/Escalate launch the recorded follow-up with bounded untrusted output in the held workspace; Re-run command starts a new monitor ID for the same argv/cwd. Screenshot fixture resolves tailnet-t.10 to --mon-3 with immediate/monitor. Canaries: continue=1 hijack + 1 same-workspace successor; rerun=1 new monitor in held workspace + 1 eventual follow-up. Reference docs updated (monitor-operations.md hijack section; agent-sessions/workspaces/agents-tab no longer call monitors ineligible). Pin 35904ebd covers every new sase-core contract. epic-symbols clear. Child land will close sase-1t2.11.1.7 only; outer land sase-1t2.14 still owns glossary:agent-hijack.

[2026-11-17T09:45:23Z · sase-1t2.11.1.land] PHASE VERIFIED by the sase-1t2.11.1 land agent; the phase was closed by its child epic's close. All five monitor_adapter items in plan:202611/agent_hijack_dependability.md are present at sase 346d84ce32 plus this landing. (1) sase-core: immediate/adapter monitor for a running monitor, latched/boundary monitor for a settled monitor with a pending follow-up, and monitor recovery rows Continue/Escalate/Re-run command/View/Shell/Dismiss, with Restart/Edit hidden. (2) Stop writes intent and calls stop_monitor for proc-backed and legacy monitors. (3) The settle_claim_and_followup checkpoint suppresses --next, pins and re-owns the exact claim, and writes hijacked plus boundary_outcome across proc_adapter, reconcile and supervise_finish. (4) Continue/Escalate pass bounded, untrusted partial output; Re-run starts a new monitor in the held workspace. (5) The screenshot fixture is flipped to immediate/monitor, sleep-monitor canaries cover continue and rerun, and monitor-operations.md is updated. The landing also fixed the TUI import-budget regression the child introduced. Check ToolRun 5de39afe2e015b68215f220c23cd2824 succeeded. No epic-symbol entries. Outer epic sase-1t2 is left to its own land agent; glossary:agent-hijack stays owned by sase-1t2.14.

## Dependencies

- **Blocks:** [sase-1t2.13](sase-1t2.13.md) ◐ · ⧖ 2026-11-15
- **Depends on:** [sase-1t2.8](sase-1t2.8.md) ✓ · ⧖ 2026-11-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.11](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t2.11.md) | [sase-1t2.11](sase-1t2.11.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:ef][1] | Check cross-epic coordination notes between hijack epic sase-1t2 and TUI perf epic sase-1t3 | 1 |
| read-by | [agent:sase-1t2.11.1.1][2] | Need the parent phase decisions that govern monitor adapter implementation | 1 |
| read-by | [agent:sase-1t2.11.1.7][3] | Need parent phase DECISIONS and land requirements for completion evidence | 1 |
| read-by | [agent:toobig-9v.local_trust_management.0][4] | Check whether the monitor-hijack phase owns the oversized hijack action test file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ef/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.11.1.1/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.11.1.7/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-9v.local_trust_management.0/README.md

<!-- sase:referenced-by:end -->
