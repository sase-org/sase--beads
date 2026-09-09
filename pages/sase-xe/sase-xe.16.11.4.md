# Bead: sase-xe.16.11.4 — Integrate shared policy, honest discovery, and durable activation

[Bead Pages](../README.md) / [sase-xe.16.11](sase-xe.16.11.md) / sase-xe.16.11.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-xe.16.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.16.land.md) · **Assignee:** `sase-xe.16.11.4` · **Size:** medium
**Created:** 2026-09-09 04:38:29 EDT · **Closed:** 2026-09-09 10:11:51 EDT
**Plan:** [202609/remote\_dispatch\_landing\_remaining.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_landing_remaining.md)

## Description

setup-integration: consume the published core surface through thin adapters, preserve discovery diagnostics in all init entry points, share verified activation with machine add and repair, remove untracked chezmoi fallback, update stale Fleet setup guidance, and ratchet the core pin and published floor.

## Notes

[2026-09-09T14:11:51Z · sase-xe.16.11.4] Consumed the published machine-setup and follow-promotion core surface through thin adapters (classify_tailnet_health, classify_tailnet_discovery, reconcile_machine_enrollments, fleet_followed_batch_family_promotions). Init now uses discover_detailed: missing/failed discovery is exit 1 with diagnostics, while working-provider candidates are kept beside failed-provider diagnostics. Direct add and repair share init activation (deploy/reload/hello); repair retains the still-applied credential until replacement activation succeeds. Scoped chezmoi apply is tracked-only: submit failure does not untracked-apply, wait failure keeps the proc id and reports in-progress. Fleet setup teaches target bootstrap plus canonical `sase machine init`, with rescan guidance when machines already exist. Ratcheted sase-core-revision.txt to a6d40bad16a8 (just ratchet-core-revision) and the published floor to sase-core-rs>=0.32.54 (just ratchet-core-window). Binding collection includes the new names. Verified with just check (escalated to the full suite: core-identity-changed, packaging-config, rename-or-delete). sase bead epic-symbols sase-xe.16.11.4 reported no leftovers.

## Dependencies

- **Depends on:** [sase-xe.16.11.3](sase-xe.16.11.3.md) ✓ · ⧖ 2026-09-09
- **Blocks:** [sase-xe.16.11.5](sase-xe.16.11.5.md) ◐ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.11.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.11.4/README.md) | [sase-xe.16.11.4](sase-xe.16.11.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`20c7b98`](https://github.com/sase-org/sase/commit/20c7b9804577b7db315f42131b5702379f4d1c49) | feat(dispatch): integrate core setup policy and durable activation | [sase-xe.16.11.4](sase-xe.16.11.4.md) | 2026-09-09 10:13:15 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.1p.final][1] | Record the setup-integration scope and its separation from Fleet catalog decoding | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.1p.final/README.md

<!-- sase:referenced-by:end -->
