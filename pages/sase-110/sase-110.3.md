# Bead: sase-110.3 — Ratchet the core pin and dependency floor past the runner surface

[Bead Pages](../README.md) / [sase-110](README.md) / sase-110.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0kl](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0kl.md) · **Assignee:** `sase-110.3` · **Size:** small
**Created:** 2026-09-14 11:33:16 EDT
**Plan:** [202609/agent\_sudo\_requests.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_sudo_requests.md)

## Description

core-pin: ratchet sase-core-revision.txt and the sase-core-rs floor to the release carrying the sudo runner and bindings, keeping binding validators green.

## Notes

[2026-09-14T16:56:45Z · sase-110.3] PROPOSED FOLLOW-UP: Publish and ratchet sudo core binding floor — once the release carrying core commit ab68522 is on PyPI, bump the sase-core-rs floor and flip src/sase/sudo/core.py from the Python fallback seam to the real sudo_manifest_sha256/sudo_derive_risk_badges bindings with validator coverage.

[2026-09-14T17:10:20Z · sase-110.3] PROPOSED FOLLOW-UP: Resolve existing disk-pressure binding skew — committed src/sase/core/disk_pressure.py requires classify_disk_pressure and disk_pressure_wire_schema_version, but current sase-core HEAD ab68522 does not export them, so tools/check_sase_core_rs_bindings is red independent of the sudo pin ratchet.

## Dependencies

- **Depends on:** [sase-110.1](sase-110.1.md) ✓ · ⧖ 2026-09-14
- **Blocks:** [sase-110.4](sase-110.4.md) ◐ · ⧖ 2026-09-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-110.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-110.3/README.md) | [sase-110.3](sase-110.3.md) | 0 |
