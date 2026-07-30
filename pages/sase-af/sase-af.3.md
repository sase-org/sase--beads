# Bead: sase-af.3 — Require the published core and turn the lane on

[Bead Pages](../README.md) / [sase-af](README.md) / sase-af.3

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-af.3` · **Size:** small
**Created:** 2026-07-28 12:54:23 UTC · **Closed:** 2026-07-28 14:46:44 UTC
**Plan:** [202607/lumberjack\_wait\_runners.md](https://github.com/sase-org/sase--plans/blob/main/202607/lumberjack_wait_runners.md)

## Description

enable_code_quality: bump the `sase-core-rs` window in pyproject.toml to the release that carries the Rust change, then set `wait_runners` on the `code_quality` lumberjack in the chezmoi-managed sase_athena.yml.

## Notes

[2026-07-28T14:46:39Z · sase-af.3] Completed phase 3: merged/published sase-core-rs 0.12.2, bumped sase pyproject/uv.lock to require >=0.12.2,<0.13.0, updated the telemetry smoke minimum test, enabled code_quality wait_runners: 0 in the chezmoi-managed athena config and applied it live. Also repaired a stale plan-header provenance artifact that was blocking SASE validation. Verification: just install; just check passed; global and venv lumberjack list show code_quality wait_runners: 0; verbose dry-run for recent_bug_audit[sase] renders %wait(runners=0).

## Dependencies

- **Depends on:** [sase-af.2](sase-af.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-af.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-af.3/README.md) | [sase-af.3](sase-af.3.md) | 2 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`c9978ed`](https://github.com/sase-org/sase/commit/c9978edf4d866fedd32245112b133ac6ad36ef05) | build(deps): require sase-core-rs 0.12.2 (sase-af.3) | [sase-af.3](sase-af.3.md) | 2026-07-28 14:48:59 |
| [`sase--plans@07b4c8b`](https://github.com/sase-org/sase--plans/commit/07b4c8b8add6a95cd16f880b65c4b2f973b94f7b) | docs: repair plan provenance header (sase-af.3) | [sase-af.3](sase-af.3.md) | 2026-07-28 14:50:36 |
