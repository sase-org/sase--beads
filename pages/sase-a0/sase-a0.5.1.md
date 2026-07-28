# Bead: sase-a0.5.1 — Publish the typed-resolution core

[Bead Pages](../README.md) / [sase-a0.5](sase-a0.5.md) / sase-a0.5.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-a0.5.1` · **Size:** small
**Created:** 2026-07-27 17:14:07 UTC · **Closed:** 2026-07-27 17:32:32 UTC
**Plan:** [202607/finish\_sase\_a0.md](https://github.com/sase-org/sase--plans/blob/main/202607/finish_sase_a0.md)

## Description

core-release: publish and verify the next sase-core-rs patch containing the typed close-resolution bindings and compatible bead_close signature.

## Notes

core-release complete. release-plz PR #36 (chore: release v0.11.4) merged on sase-core master; tag v0.11.4 published with 4 wheels + sdist (same artifact matrix as 0.11.3). Release input is 815e2e1 'feat(bead): record typed close resolutions', which supplies bead_needs_resolution_migration, bead_resolution_migration_sql, resolution in bead wire + event records, and bead_close(beads_dir, issue_ids, reason=None, resolution=None, now=None).

Verified in a fresh Python 3.12 venv holding exactly sase-core-rs==0.11.4:
- both migration bindings present;
- inspect.signature(bead_close) == (beads_dir, issue_ids, reason, resolution, now);
- explicit 'done', 'canceled', and 'superseded' closes each round-trip: bead_show reports status=closed with the matching resolution;
- tools/smoke_sase_core_rs_telemetry passes (exit 0);
- tools/check_sase_core_rs_bindings reports all 194 required bindings present (0.11.3 was missing 2).

Published minimum for sase-a0.5.2 is 0.11.4, so the existing <0.12.0 upper bound still holds. No repo file changes in this phase.

## Dependencies

- **Blocks:** [sase-a0.5.2](sase-a0.5.2.md) ✓
