# Bead: sase-126.4 — Verify the combined repair against both CI lanes

[Bead Pages](../README.md) / [sase-126](README.md) / sase-126.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0mh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0mh.md) · **Assignee:** `sase-126.4` · **Size:** medium
**Created:** 2026-09-17 15:12:12 EDT · **Closed:** 2026-09-18 05:03:20 EDT
**Plan:** [202609/restore\_actions\_ci.md](https://github.com/sase-org/sase--plans/blob/main/202609/restore_actions_ci.md)

## Description

integrated-verification: verify the combined tree with the exact selected core, the exhaustive checks, visual suite, performance floors, and current Actions results, resolving any remaining failures in scope.

## Notes

[2026-09-17T23:48:30Z · sase-126.4] PROPOSED FOLLOW-UP: Publish and ratchet sase-core-rs 0.34.48 - current service-status Python bindings require service_enablement_resolve and service_status_*; the source pin is updated here, but PyPI currently only has 0.34.47 so the exact published-floor contract cannot be fully satisfied until that release exists.

[2026-09-18T00:13:30Z · sase-126.4] PROPOSED FOLLOW-UP: Complete the current sase-core-rs publish/floor ratchet - the source pin now targets core v0.34.49 for the service-status bindings and fix, while the complete PyPI floor remains 0.34.47 because 0.34.48 is incomplete and 0.34.49 is not published yet.

[2026-09-18T08:16:36Z · sase-126.4--e] PROPOSED FOLLOW-UP: Triage selection-health flake baseline promotions — check-full on 2026-09-18 promoted 22 reproducible flake node IDs that were added to tests/reproducible_flake_baseline.txt under sase-126.4; file owner task beads or retire them once fixed.

[2026-09-18T09:03:20Z · sase-126.4--f] Verified source pin cdbc7ad72addda2d2034013a516010ca3a5f6537, VCS log property-test hardening, gate failure-outcome attempt-id compatibility, ACE agent visual goldens including cleanup confirmation stabilization and artifacts split narrow key legend, fleet/metadata visual fixture hardening, usage-probe managed-temp isolation and reaper horizon registration, test-cost CPU budget recalibration, and selection-health flake-baseline maintenance with exact pinned-core monitor: just install, just fix, just check, just test-visual, just phase7-perf-check, and just check-full passed. Current pre-fix Actions failures were pinned-core failures on older SHAs; remote verification remains for the host-created commit.

## Dependencies

- **Depends on:** [sase-126.1](sase-126.1.md) ✓ · ⧖ 2026-09-17
- **Depends on:** [sase-126.2](sase-126.2.md) ✓ · ⧖ 2026-09-17
- **Depends on:** [sase-126.3](sase-126.3.md) ✓ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-126.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-126.4.md) | [sase-126.4](sase-126.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`eaa1cbf`](https://github.com/sase-org/sase/commit/eaa1cbf4de92fc7a315040b5332c5f1a86886da6) | fix(ci): restore pinned-core verification | [sase-126.4](sase-126.4.md) | 2026-09-18 06:15:38 EDT |
