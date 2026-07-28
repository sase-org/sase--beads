# Bead: sase-a0.2 — Publish sase-core 0.11.3 and raise the declared minimum

[Bead Pages](../README.md) / [sase-a0](README.md) / sase-a0.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-a0.2` · **Size:** small
**Created:** 2026-07-27 16:02:01 UTC · **Closed:** 2026-07-27 16:42:42 UTC
**Plan:** [202607/fix\_ci\_failures.md](https://github.com/sase-org/sase--plans/blob/main/202607/fix_ci_failures.md)

## Description

corefloor: land the open sase-core release so the five `plan_reference_*` bindings reach PyPI, then raise sase's declared `sase-core-rs` floor and its tracking test to the published version.

## Notes

Merged sase-core PR #35 (chore: release v0.11.3, squashed as f023596). release-plz tagged v0.11.3 and published all 5 wheels + sdist to PyPI. Verified against a scratch venv holding the exact declared minimum: tools/smoke_sase_core_rs_telemetry passes and tools/check_sase_core_rs_bindings reports 'sase_core_rs 0.11.3 exposes all 193 bindings required by src/sase' (was 5 missing plan_reference_* bindings on 0.11.2). Raised the floor in pyproject.toml (>=0.11.3,<0.12.0), tests/test_sase_core_rs_telemetry_smoke_tool.py, and uv.lock. All just check steps pass except lint (symvision), which fails on stale sase-9z --epic-symbol entries in the Justfile - pre-existing on clean master and outside this phase's scope.

## Dependencies

- **Blocks:** [sase-a0.4](sase-a0.4.md) ✓
