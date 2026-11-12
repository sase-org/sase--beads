# Bead: sase-1sd.3 — Stop done monitors with stale followup\_pending from owning beads forever (sase-1re)

[Bead Pages](../README.md) / [sase-1sd](README.md) / sase-1sd.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1bp](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1bp.md) · **Assignee:** `sase-1sd.3` · **Size:** medium
**Created:** 2026-11-12 05:26:16 EST
**Plan:** [202611/next\_seven\_salvage\_and\_unstrand.md](https://github.com/sase-org/sase--plans/blob/main/202611/next_seven_salvage_and_unstrand.md)

## Description

monitor-ownership: a monitor member that is done but still reports followup_pending=true (stale next_action, no followup_outcome) reduces to owned/monitor in sase-core stranded_work/classify.rs owner_kind() forever, hiding the bead from STRANDED and the recovery reconciler. Root-cause why the follow-up never settled, then bound ownership using actual delivery/recovery facts, distinguishing a dead abandoned follow-up from a queued successor, a live monitor, and settlement grace. Needs a sase-core change and pin move.

## Dependencies

- **Depends on:** [sase-1sd.2](sase-1sd.2.md) ◐ · ⧖ 2026-11-12
- **Blocks:** [sase-1sd.4](sase-1sd.4.md) ◐ · ⧖ 2026-11-12
