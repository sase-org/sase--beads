# Bead: sase-1j6.10.5 — Make the healer relaunch, settle, and escalate correctly end to end

[Bead Pages](../README.md) / [sase-1j6.10](sase-1j6.10.md) / sase-1j6.10.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1j6.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1j6.land.md) · **Assignee:** `sase-1j6.10.5` · **Size:** medium
**Created:** 2026-10-10 08:09:08 EDT · **Closed:** 2026-10-10 10:09:15 EDT
**Plan:** [202610/finish\_update\_skew\_auto\_restart.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_update_skew_auto_restart.md)

## Description

healer-relaunch: move the sase-core pin past core-fixes, re-classify with the probe witness so a passing probe relaunches, pass real timestamps, escalate expired deferrals, take over stale claims properly, escalate a replacement's second failure as already_restarted, write in-flight recovery states with ledger_key and episode_id, record real from/to revisions in provenance, scrub the provenance env, order -p targets topologically, and prove it with an un-mocked classifier test.

## Notes

[2026-10-10T14:08:54Z · sase-1j6.10.5--1] PROPOSED FOLLOW-UP: reconcile retired feature-flag definitions with the landing of sase-1jc.7 — ToolRun e25fa0108d01916124d664f590de793f failed rule 7 for closed flags ace_refresh_tokens, admin_center_flags, ref_sync_gesture, and refresh_panel; the identical checker output reproduces on clean base 35a97a0e1e, and this phase did not edit those files.

[2026-10-10T14:09:15Z · sase-1j6.10.5--1] Pinned sase-core at 31544120e776e4d1cc3e5d0932502748d352d749; healer probe reclassification, episode recovery metadata, full refresh revisions, stale takeover, replacement escalation, and bootstrap provenance all verified. Focused tests passed (26). sase tool run check stopped on four closed-flag rule-7 failures, reproduced identically on clean base 35a97a0e1e and recorded as a proposed follow-up. epic-symbols empty.

## Dependencies

- **Depends on:** [sase-1j6.10.1](sase-1j6.10.1.md) ✓ · ⧖ 2026-10-10
- **Depends on:** [sase-1j6.10.2](sase-1j6.10.2.md) ✓ · ⧖ 2026-10-10
- **Depends on:** [sase-1j6.10.3](sase-1j6.10.3.md) ✓ · ⧖ 2026-10-10
- **Blocks:** [sase-1j6.10.6](sase-1j6.10.6.md) ◐ · ⧖ 2026-10-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1j6.10.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1j6.10.5.md) | [sase-1j6.10.5](sase-1j6.10.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ee99123`](https://github.com/sase-org/sase/commit/ee9912307c92a9cb61f236d527fd4e4929c50d6c) | feat(auto-restart): complete healer relaunch and provenance flow | [sase-1j6.10.5](sase-1j6.10.5.md) | 2026-10-10 10:10:49 EDT |
