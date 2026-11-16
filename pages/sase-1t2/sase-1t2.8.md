# Bead: sase-1t2.8 — Durable hijack latch at agent-turn hand-offs

[Bead Pages](../README.md) / [sase-1t2](README.md) / sase-1t2.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1ct](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ct.md) · **Assignee:** `sase-1t2.8` · **Size:** large
**Created:** 2026-11-15 20:00:10 EST · **Closed:** 2026-11-16 15:16:28 EST
**Plan:** [202611/agent\_hijack\_dependability.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack_dependability.md)

## Description

latch_core: latched ledger state and events in sase-core; the decision returns latched for finalizing turns and staged hand-offs; a Python latch store keyed by target; runner checkpoints at staged-handoff adoption, run end (moot), and retry boundaries; a pre- and post-spawn guard that the follow-up fallback chain cannot swallow; dead-owner reconciliation; a bounded wait with an explicit force-now path; CLI -c/--cancel and -n/--now; and the TUI pending overlay.

## Notes

[2026-11-16T09:07:00Z · sase-1t2.8] PROPOSED FOLLOW-UP: Repair the parent plan research reference — audited reading of research:202611/agent_hijack_dependability/agent_hijack_dependability.md returned missing on this run; planning uses the approved epic contract, which is complete enough to proceed.

[2026-11-16T20:16:48Z · sase-1t2.8.1.land] Closed automatically when child epic sase-1t2.8.1 closed. The sase-1t2.8.1 land agent verified that the child plan delivered every latch_core requirement in this phase's description:
- sase-core latched state and latch/apply_latch/cancel_latch events (c58ecb80/e9b1cf04, contained in pin 969096d0)
- latched decisions for finalizing and staged-pending turns
- target-keyed Python latch store (agent/hijack/latch.py)
- runner checkpoints at staged adoption, run-end moot, and retry
- pre/post-spawn guards with HijackLatchedError re-raised ahead of every fallback
- dead-owner reconciliation in the stale sweep
- explicit force-now after 120s
- CLI -c/--cancel, -e/--explain, -n/--now with exit 3
- TUI pending overlay with cancel/force
Landing evidence is in the sase-1t2.8.1 close note. Checkpoint inventory for chaos is recorded on sase-1t2.13. No --epic-symbol entries for sase-1t2.8. The containing epic sase-1t2 stays with its land agent.

## Dependencies

- **Blocks:** [sase-1t2.10](sase-1t2.10.md) ✓ · ⧖ 2026-11-15
- **Blocks:** [sase-1t2.11](sase-1t2.11.md) ◐ · ⧖ 2026-11-15
- **Depends on:** [sase-1t2.7](sase-1t2.7.md) ✓ · ⧖ 2026-11-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t2.8.md) | [sase-1t2.8](sase-1t2.8.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:ef][1] | Check cross-epic coordination between hijack epic sase-1t2 and TUI perf epic sase-1t3 | 1 |
| read-by | [agent:sase-1t2.8.1.1][2] | Need the parent phase notes and design links | 1 |
| read-by | [agent:sase-1t2.8.1.land][3] | Confirm the parent phase auto-close state after epic close | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ef/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.8.1.1/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.8.1.land/README.md

<!-- sase:referenced-by:end -->
