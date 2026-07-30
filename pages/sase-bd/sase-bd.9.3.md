# Bead: sase-bd.9.3 — Make the declared core floor honest

[Bead Pages](../README.md) / [sase-bd.9](sase-bd.9.md) / sase-bd.9.3

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-bd.9.3` · **Size:** small
**Created:** 2026-07-30 20:15:19 UTC · **Closed:** 2026-07-30 21:04:42 UTC
**Plan:** [202607/bead\_close\_integrity\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_close_integrity_landing.md)

## Description

floor-bump: raise the `sase-core-rs` window to the newly published release, refresh the lockfile and the declared-minimum test, and prove in a clean venv that the minimum satisfies every required binding and can read a store containing note-append events.

## Notes

[2026-07-30T21:04:42Z · sase-bd.9.3] Updated pyproject.toml, uv.lock, and the declared-minimum telemetry test to carry published sase-core-rs 0.15.0 with range >=0.15.0,<0.16.0. Verified in a fresh Python 3.12 venv with only sase-core-rs==0.15.0 from PyPI: tools/check_sase_core_rs_bindings reports all 230 bindings present, tools/smoke_sase_core_rs_telemetry passes, and sase_core_rs.bead_show reads live beads sidecar entry sase-bd.3 from a store containing note_appended events. Also verified python3 tools/smoke_sase_core_rs_telemetry --print-minimum pyproject.toml prints 0.15.0, .venv/bin/python tools/validate_sase_core_rs_version --pyproject pyproject.toml --published-minimum exits 0, focused pytest tests/test_sase_core_rs_telemetry_smoke_tool.py passes, and just install passes. Full just check passed fmt/lint through symvision/toobig, then failed only in final SASE validation on unrelated existing issues: init skills --check wants 5 provider skill overwrites and plan links validate reports 202607/prompts/commit_vars_finalizer.md missing ../commit_vars_finalizer.md.

## Dependencies

- **Depends on:** [sase-bd.9.2](sase-bd.9.2.md) ✓
- **Blocks:** [sase-bd.9.5](sase-bd.9.5.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-bd.9.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-bd.9.3/README.md) | [sase-bd.9.3](sase-bd.9.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`f115e8f`](https://github.com/sase-org/sase/commit/f115e8f7adac806b0545e5718948f01e55ecd1e5) | build(deps): require sase-core-rs 0.15.0 | [sase-bd.9.3](sase-bd.9.3.md) | 2026-07-30 21:06:38 |
