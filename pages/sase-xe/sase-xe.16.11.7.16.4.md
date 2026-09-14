# Bead: sase-xe.16.11.7.16.4 — Gateway version skew is visible, and the upgrade runbook says to restart

[Bead Pages](../README.md) / [sase-xe.16.11.7.16](sase-xe.16.11.7.16.md) / sase-xe.16.11.7.16.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.01](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.01.md) · **Assignee:** `sase-xe.16.11.7.16.4` · **Size:** small
**Created:** 2026-09-14 16:25:34 EDT
**Plan:** [202609/fleet\_ghost\_rows\_readcompat.md](https://github.com/sase-org/sase--plans/blob/main/202609/fleet_ghost_rows_readcompat.md)

## Description

gateway-skew-loudness: surface remote gateway service/contract version skew in `sase machine status` output (hello already carries service versions) so an outdated target gateway is visible instead of hiding behind "hello ok", and extend docs/remote_dispatch.md with the restart-after-upgrade requirement for supervised gateways, whose Restart=on-failure units keep running the old binary after an install upgrade.
