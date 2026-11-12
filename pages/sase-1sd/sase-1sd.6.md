# Bead: sase-1sd.6 — Make sase agent restart find crash-killed agents (sase-1qi, ride-along sase-1qr)

[Bead Pages](../README.md) / [sase-1sd](README.md) / sase-1sd.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1bp](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1bp.md) · **Assignee:** `sase-1sd.6` · **Size:** medium
**Created:** 2026-11-12 05:26:16 EST
**Plan:** [202611/next\_seven\_salvage\_and\_unstrand.md](https://github.com/sase-org/sase--plans/blob/main/202611/next_seven_salvage_and_unstrand.md)

## Description

agent-identity: a kill or reboot that never writes done.json leaves the TUI showing FAILED while sase agent restart returns not-found, because find_named_agent skips non-done records with dead PIDs (correct for wait resolution, wrong for restart). Give restart a lookup that includes dead-without-done records without deleting the liveness skip waiters rely on. Ride-along per decision qr_ride_along: project process_identity through the sase-core agent scan so the PID-reuse guard stops degrading to PID-only for scanned records.

## Dependencies

- **Depends on:** [sase-1sd.5](sase-1sd.5.md) ◐ · ⧖ 2026-11-12
- **Blocks:** [sase-1sd.7](sase-1sd.7.md) ◐ · ⧖ 2026-11-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sd.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sd.6/README.md) | [sase-1sd.6](sase-1sd.6.md) | 0 |
