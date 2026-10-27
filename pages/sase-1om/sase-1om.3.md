# Bead: sase-1om.3 — Shared authoritative machine capacity report

[Bead Pages](../README.md) / [sase-1om](README.md) / sase-1om.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5e.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5e.linker.w0.md) · **Assignee:** `sase-1om.3` · **Size:** medium
**Created:** 2026-10-26 20:19:44 EDT · **Closed:** 2026-10-27 00:17:07 EDT
**Plan:** [202610/machine\_capacity\_transparency.md](https://github.com/sase-org/sase--plans/blob/main/202610/machine_capacity_transparency.md)

## Description

machine-report: one read-only Python adapter that builds the machine's capacity report from admission's shared scan cache, a fresh liveness probe, active holds, and the Rust snapshot, plus limit provenance, machine label, age, and a bounded rescan policy.

## Notes

[2026-10-27T03:15:28Z · sase-1om.3] sase-1oj.4 landed at e7d9f7a479; this phase reuses the pruned capacity-only scan cache and does not add a published snapshot file (publish_snapshot_file=no).

[2026-10-27T03:15:37Z · sase-1om.3] PROPOSED FOLLOW-UP: test_capacity_blocked_waiter_does_not_park_the_queue_behind_it fails identically on clean master (fake PIDs 100/101/102 dropped by capacity_only dead-PID pruning); leftover of sase-1oj.4 adoption, already recorded on sase-1oj notes #2/#3.

[2026-10-27T03:15:42Z · sase-1om.3] PROPOSED FOLLOW-UP: test_capacity_only_scan_preserves_admission_and_candidate_decisions fails identically on clean master — capacity_only vs full snapshots now differ in accounting rows after core-accounting (sase-1om.2).

[2026-10-27T04:17:07Z · sase-1om.3] Verified MachineCapacityReport: screenshot 5.0/8 with six accounting entries and ACE override provenance; matching-token reuse at any age; token-change inside 30s serves stale scan_current=False; dead PID drops without rescan; older-core missing accounting -> accounting_available=False; invalid weight -> accounting_valid=False with known subtotal; report never takes runner_slots.lock or bumps token; peek_active_agent_holds omits expired holds without rewriting the store; TUI import closure +0 vs master. just check ToolRun b9e3e67615bb0ac97aeba0c9ac56dd36: no NEW failures; 2 KNOWN pre-existing (test_capacity_blocked_waiter_does_not_park_the_queue_behind_it, test_capacity_only_scan_preserves_admission_and_candidate_decisions) recorded as PROPOSED FOLLOW-UP citing sase-1oj. publish_snapshot_file=no; sase-1oj.4 landed at e7d9f7a479.

## Dependencies

- **Depends on:** [sase-1om.2](sase-1om.2.md) ✓ · ⧖ 2026-10-26
- **Blocks:** [sase-1om.4](sase-1om.4.md) ◐ · ⧖ 2026-10-26
- **Blocks:** [sase-1om.5](sase-1om.5.md) ◐ · ⧖ 2026-10-26
- **Blocks:** [sase-1om.6](sase-1om.6.md) ◐ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1om.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1om.3/README.md) | [sase-1om.3](sase-1om.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`dd9e740`](https://github.com/sase-org/sase/commit/dd9e740aec9bfb6efaf3ed26d59d8116d444760a) | feat(runner-slots): add read-only machine capacity report | [sase-1om.3](sase-1om.3.md) | 2026-10-27 00:18:41 EDT |
