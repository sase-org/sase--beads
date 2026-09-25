# Bead: sase-19o.1 — Registry rebuilds keep in-flight claims

[Bead Pages](../README.md) / [sase-19o](README.md) / sase-19o.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0s9](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0s9.md) · **Assignee:** `sase-19o.1` · **Size:** medium
**Created:** 2026-09-25 13:51:10 EDT
**Plan:** [202609/bead\_work\_registry\_drift\_resilience.md](https://github.com/sase-org/sase--plans/blob/main/202609/bead_work_registry_drift_resilience.md)

## Description

registry-inflight-claims: make rebuild_name_registry() (both the optimistic _commit_rebuild_locked path and the _rebuild_name_registry_locked fallback) carry forward prior local artifact-backed claims whose artifact dir is identity-pending (bootstrap agent_meta.json only, no name/clan/session yet) while its runner process is alive, re-derive entries for dirs whose named metadata landed after the unlocked scan, and keep dropping claims whose dir is gone, dead, or names a different identity. Share one per-artifact derivation helper between the full scan and the carry-forward. Add regression tests for the incident sequence.

## Dependencies

- **Blocks:** [sase-19o.3](sase-19o.3.md) ◐ · ⧖ 2026-09-25
