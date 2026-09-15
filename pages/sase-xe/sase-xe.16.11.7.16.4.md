# Bead: sase-xe.16.11.7.16.4 — Gateway version skew is visible, and the upgrade runbook says to restart

[Bead Pages](../README.md) / [sase-xe.16.11.7.16](sase-xe.16.11.7.16.md) / sase-xe.16.11.7.16.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.01](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.01.md) · **Assignee:** `sase-xe.16.11.7.16.4` · **Size:** small
**Created:** 2026-09-14 16:25:34 EDT · **Closed:** 2026-09-15 08:03:17 EDT
**Plan:** [202609/fleet\_ghost\_rows\_readcompat.md](https://github.com/sase-org/sase--plans/blob/main/202609/fleet_ghost_rows_readcompat.md)

## Description

gateway-skew-loudness: surface remote gateway service/contract version skew in `sase machine status` output (hello already carries service versions) so an outdated target gateway is visible instead of hiding behind "hello ok", and extend docs/remote_dispatch.md with the restart-after-upgrade requirement for supervised gateways, whose Restart=on-failure units keep running the old binary after an install upgrade.

## Notes

[2026-09-15T12:03:17Z · sase-xe.16.11.7.16.4] Implemented machine status gateway/service skew visibility: hello service_versions and capability schema now flow into MachineStatus, human and JSON status output report remote versions plus skew against local sase/sase-core-rs/fleet-contract schema, and docs/remote_dispatch.md documents restarting supervised gateways after upgrades. Verified focused baseline before edits, focused pytest/ruff after edits, just check, and sase bead epic-symbols reported no leftovers.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-xe.16.11.7.16.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-xe.16.11.7.16.4/README.md) | [sase-xe.16.11.7.16.4](sase-xe.16.11.7.16.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`801e985`](https://github.com/sase-org/sase/commit/801e98578b5c954150726f8f84946007a80ba468) | fix(dispatch): surface gateway version skew | [sase-xe.16.11.7.16.4](sase-xe.16.11.7.16.4.md) | 2026-09-15 08:05:23 EDT |
