# Bead: sase-xe.16.11.7.15 — Remote agents render as real agent nodes

[Bead Pages](../README.md) / [sase-xe.16.11.7](sase-xe.16.11.7.md) / sase-xe.16.11.7.15

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.v](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.v.md) · **Assignee:** `sase-xe.16.11.7.15.land`
**Created:** 2026-09-13 18:37:59 EDT
**Plan:** [202609/remote\_agents\_display\_parity.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_agents_display_parity.md)

## Description

Remote agents in the ACE Agents tab are displayed identically to local agents — same family/clan nodes, member shells, counts, timestamps, and project names — except that remote agent nodes carry their host's name, and local nodes never carry a `here` indicator.

## Notes

[2026-09-14T02:06:21Z · sase-zt.6.5.land] INTEGRATION COORDINATION from sase-zt.6.5 landing: post-start remote-row parity work currently serializes queue_weight but omits canonical queue_capacity and explicitness from ResolvedAgentSummaryWire, and _fleet_agents_rows._agent_from_summary therefore cannot preserve the existing cN badge or Capacity detail for remote agents. A directly parented remaining-work child of sase-zt.6.5 will add the core wire fields and consume them after integrating this active family. Please preserve the shared renderer/Agent adapter and avoid introducing a competing capacity parser; the child will adopt your latest family synthesis, host-chip, refresh, and contract changes.

[2026-09-14T19:16:02Z · 0o] DISCOVERED ISSUE: Live Athena→Apollo projection currently collapses to zero rows. Athena is on SASE 0.17.1+641 / sase-core-rs 0.34.28, while Apollo's installed SASE is 0.17.1+628 / core 0.34.26+6 but its user-systemd sase-gateway process has been running since 2026-09-11 and still reports gateway 0.34.9. Authenticated hello succeeds and Apollo serves a catalog reporting 10 logical agents (4 running, 6 waiting), but Athena rejects hosts[0] with fleet_envelope_invalid: 'summary capabilities are not normalized'. The old gateway emits fleet-contract schema-v1 nested capability sets; the newer validator advertises v1 readability but CapabilitySetWire::normalized rewrites schema_version to the current v3 before equality comparison, making the old set fail normalization. Live acceptance must reload/restart Apollo's gateway onto the installed current binary and verify rows return; separately preserve or intentionally revise the claimed v1 read-compatibility behavior so mixed-version hosts do not silently disappear behind a hello-ok status.
