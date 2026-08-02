# Bead: sase-e8.3 — Python binding for the payload inventory

[Bead Pages](../README.md) / [sase-e8](README.md) / sase-e8.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ry](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ry/README.md) · **Assignee:** `sase-e8.3` · **Size:** small
**Created:** 2026-08-02 14:04:40 UTC · **Closed:** 2026-08-02 15:04:38 UTC
**Plan:** [202608/commit\_ref\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202608/commit_ref_completion.md)

## Description

core_bridge: expose `artifact_ref_payload_inventory(kind, context)` through `sase_core_rs`, release the sase-core version that carries it, and widen the `sase-core-rs` dependency window so the host can consume it.

## Notes

[2026-08-02T15:03:11Z · sase-e8.3] PROPOSED FOLLOW-UP: Publish the payload-inventory binding release and ratchet sase-core-rs - release-plz owns Cargo versions and PyPI publishing; after the binding lands and a new wheel exists, bump pyproject.toml to require that published floor.

[2026-08-02T15:04:38Z · sase-e8.3] Implemented the sase_core_rs artifact_ref_payload_inventory binding and PyO3 round-trip test; verified cargo fmt --all -- --check, cargo test -p sase_core_py, and validate_sase_core_rs_version local/published checks. Release/dependency ratchet recorded as PROPOSED FOLLOW-UP because release-plz owns PyPI publication.

## Dependencies

- **Depends on:** [sase-e8.2](sase-e8.2.md) ✓
- **Blocks:** [sase-e8.5](sase-e8.5.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-e8.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-e8.3/README.md) | [sase-e8.3](sase-e8.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase-core | [`sase-core@d0e7630`](https://github.com/sase-org/sase-core/commit/d0e763057c1f0b375130004cc581e1fcdaada6e6) | feat(py): expose artifact ref payload inventory | [sase-e8.3](sase-e8.3.md) | 2026-08-02 15:07:10 |
