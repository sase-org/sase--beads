# Bead: sase-xe.16.11.7.16.2 — Capability-set validation honors claimed v1 read-compatibility

[Bead Pages](../README.md) / [sase-xe.16.11.7.16](sase-xe.16.11.7.16.md) / sase-xe.16.11.7.16.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.01](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.01.md) · **Assignee:** `sase-xe.16.11.7.16.2` · **Size:** medium
**Created:** 2026-09-14 16:25:30 EDT
**Plan:** [202609/fleet\_ghost\_rows\_readcompat.md](https://github.com/sase-org/sase--plans/blob/main/202609/fleet_ghost_rows_readcompat.md)

## Description

caps-readcompat: in sase-core fleet_contract.rs, stop rejecting older-but-readable capability sets — the normalized-equality check must ignore the schema_version stamp that CapabilitySetWire::normalized rewrites to the current version — audit the file for the same normalize-then-strict-equality pattern on other versioned wires, and add regression tests proving a v1 summary envelope yields rows instead of fleet_envelope_invalid while unnormalized content is still rejected. Full core checks including PyO3.
