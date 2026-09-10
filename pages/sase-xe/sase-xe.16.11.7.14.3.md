# Bead: sase-xe.16.11.7.14.3 — Publish and adopt the new core surface

[Bead Pages](../README.md) / [sase-xe.16.11.7.14](sase-xe.16.11.7.14.md) / sase-xe.16.11.7.14.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0it](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0it.md) · **Assignee:** `sase-xe.16.11.7.14.3` · **Size:** small
**Created:** 2026-09-10 13:39:05 EDT
**Plan:** [202609/fleet\_stale\_remote\_rows.md](https://github.com/sase-org/sase--plans/blob/main/202609/fleet_stale_remote_rows.md)

## Description

core-ratchet: release the core changes, ratchet the revision pin and dependency floor, just install, and verify the published wheel contains the new surfaces.

## Notes

[2026-09-10T19:59:41Z · sase-xe.16.11.7.14.3] Progress: found release-plz blocked on sase-core master because crates/sase_core_py's packaging pass failed: workspace dependency sase_gateway lacked an explicit version. Patched sase-core Cargo.toml to give sase_gateway the current 0.33.0 path-dependency version alongside sase_core. Verified cargo package --workspace --allow-dirty --no-verify now passes, matching the release-plz manifest failure class. Verified ./scripts/check.sh passes when run with PYO3_PYTHON=/home/bryan/.local/bin/python3.12 and LD_LIBRARY_PATH=/home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib. PyPI still lists only sase-core-rs 0.33.0, so the dependency-floor ratchet cannot be honestly applied until this core release-infra fix lands and release-plz publishes the next wheel.

## Dependencies

- **Depends on:** [sase-xe.16.11.7.14.1](sase-xe.16.11.7.14.1.md) ✓ · ⧖ 2026-09-10
- **Depends on:** [sase-xe.16.11.7.14.2](sase-xe.16.11.7.14.2.md) ✓ · ⧖ 2026-09-10
- **Blocks:** [sase-xe.16.11.7.14.4](sase-xe.16.11.7.14.4.md) ◐ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.11.7.14.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.11.7.14.3/README.md) | [sase-xe.16.11.7.14.3](sase-xe.16.11.7.14.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@93281c3`](https://github.com/sase-org/sase-core/commit/93281c34dabc381a5a8d1cdc5fa285250ece099b) | fix(release): add gateway version metadata for release-plz | [sase-xe.16.11.7.14.3](sase-xe.16.11.7.14.3.md) | 2026-09-10 16:00:50 EDT |
