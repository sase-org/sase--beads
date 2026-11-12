# Bead: sase-1sd.6 — Make sase agent restart find crash-killed agents (sase-1qi, ride-along sase-1qr)

[Bead Pages](../README.md) / [sase-1sd](README.md) / sase-1sd.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1bp](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1bp.md) · **Assignee:** `sase-1sd.6` · **Size:** medium
**Created:** 2026-11-12 05:26:16 EST · **Closed:** 2026-11-12 17:07:40 EST
**Plan:** [202611/next\_seven\_salvage\_and\_unstrand.md](https://github.com/sase-org/sase--plans/blob/main/202611/next_seven_salvage_and_unstrand.md)

## Description

agent-identity: a kill or reboot that never writes done.json leaves the TUI showing FAILED while sase agent restart returns not-found, because find_named_agent skips non-done records with dead PIDs (correct for wait resolution, wrong for restart). Give restart a lookup that includes dead-without-done records without deleting the liveness skip waiters rely on. Ride-along per decision qr_ride_along: project process_identity through the sase-core agent scan so the PID-reuse guard stops degrading to PID-only for scanned records.

## Notes

[2026-11-12T22:03:51Z · sase-1sd.6] TASK RESOLVED: sase-1qi — Restart lookup now includes dead agents without done markers for restart planning and cleanup while default lookup and wait resolution retain their existing behavior; targeted restart/lookup tests and the full SASE check passed.

[2026-11-12T22:04:19Z · sase-1sd.6] TASK RESOLVED: sase-1qr — Rust agent scanning now projects process_identity from agent metadata and running markers through the wire and Python binding; schema v37 migration forces cached rows to rescan. Scanner, binding, migration tests and the full sase-core check passed.

[2026-11-12T22:07:40Z · sase-1sd.6] Verified focused restart/lookup/liveness and provider-drain tests passed; full just check passed in the main repo and sase-core; no epic symbols remain.

## Dependencies

- **Depends on:** [sase-1sd.5](sase-1sd.5.md) ✓ · ⧖ 2026-11-12
- **Blocks:** [sase-1sd.7](sase-1sd.7.md) ◐ · ⧖ 2026-11-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sd.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sd.6/README.md) | [sase-1sd.6](sase-1sd.6.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@3416e4e`](https://github.com/sase-org/sase-core/commit/3416e4e24c84db3b6d596c6a4e4ede6d9a77c8cb) | feat(agent-scan): project process identity in scans | [sase-1sd.6](sase-1sd.6.md) | 2026-11-12 17:09:44 EST |
| sase | [`c77ff7e`](https://github.com/sase-org/sase/commit/c77ff7e8f7ed0e645d77d4892bb9745ad9b54ab4) | fix(agent): include dead agents in restart lookup | [sase-1sd.6](sase-1sd.6.md) | 2026-11-12 17:11:46 EST |
