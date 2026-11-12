# Bead: sase-1sd.3 — Stop done monitors with stale followup\_pending from owning beads forever (sase-1re)

[Bead Pages](../README.md) / [sase-1sd](README.md) / sase-1sd.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1bp](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1bp.md) · **Assignee:** `sase-1sd.3` · **Size:** medium
**Created:** 2026-11-12 05:26:16 EST · **Closed:** 2026-11-12 09:33:50 EST
**Plan:** [202611/next\_seven\_salvage\_and\_unstrand.md](https://github.com/sase-org/sase--plans/blob/main/202611/next_seven_salvage_and_unstrand.md)

## Description

monitor-ownership: a monitor member that is done but still reports followup_pending=true (stale next_action, no followup_outcome) reduces to owned/monitor in sase-core stranded_work/classify.rs owner_kind() forever, hiding the bead from STRANDED and the recovery reconciler. Root-cause why the follow-up never settled, then bound ownership using actual delivery/recovery facts, distinguishing a dead abandoned follow-up from a queued successor, a live monitor, and settlement grace. Needs a sase-core change and pin move.

## Notes

[2026-11-12T14:33:11Z · sase-1sd.3] Root-cause of live examples: (A) settle_turn_claim_and_followup skipped launch AND outcome recording when shell_state=stopped, leaving stale next_action with followup_outcome absent — sase-s5.land--mon (stopped, settled=true, next_action, no outcome). (B) sase-1ih.2--mon-0 supervisor died mid-run (monitor_settled=false, turn_state=running, no done.json), so collector never saw an outcome. (C) sase-ru.6 monitors launched follow-ups and stay owned via the live successor. (D) sase-kp.land--mon is gone from the name registry. owner_kind() treated followup_pending and stale turn_state as forever ownership without requiring process_live/remote.

[2026-11-12T14:33:21Z · sase-1sd.3] TASK RESOLVED: sase-1re — owner_kind now requires process_live||remote for monitor/gate turn_state/followup_pending; a dead abandoned pending follow-up strands as followup_failed; a live pending monitor, a queued successor, and settle grace stay owned. Stopped settlement records followup_outcome=suppressed without launching. Pin moves through host completion; sase-1re itself stays open for the land agent.

[2026-11-12T14:33:28Z · sase-1sd.3] PROPOSED FOLLOW-UP: Never-settled running monitors after supervisor death — sase-1ih.2--mon-0 is still running with monitor_settled=false, stale next_action, and no done.json; the classifier now strands the dead member, but settlement never ran so the artifact stays half-written.

[2026-11-12T14:33:35Z · sase-1sd.3] PROPOSED FOLLOW-UP: sase-kp.land--mon missing from the name registry — the original live example cannot be re-observed; land should confirm whether kp still needs a stranded recovery pass.

[2026-11-12T14:33:50Z · sase-1sd.3] Verified sase-1re: owner_kind requires process_live||remote for monitor/gate turn_state/followup_pending; dead abandoned pending strands as followup_failed; live pending, queued successor, and settle grace stay owned. Stopped settlement records followup_outcome=suppressed without launching. sase-core stranded_work 36 tests + 2 binding tests; sase tool run check 1b4a90f3d5a49a4cb863b62e0a56bd2b pass; sase-core check 3c57ae3dae94ae111b52351aea680b78 pass; epic-symbols none leftover. Pin via host completion. Did not close sase-1re or parent epic.

## Dependencies

- **Depends on:** [sase-1sd.2](sase-1sd.2.md) ✓ · ⧖ 2026-11-12
- **Blocks:** [sase-1sd.4](sase-1sd.4.md) ◐ · ⧖ 2026-11-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sd.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sd.3/README.md) | [sase-1sd.3](sase-1sd.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@afc64b1`](https://github.com/sase-org/sase-core/commit/afc64b102dcdaf3cbb10cfd9c3b741b35fc94fb6) | fix(stranded\_work): stop dead monitors with stale followup\_pending from owning beads | [sase-1sd.3](sase-1sd.3.md) | 2026-11-12 09:37:23 EST |
