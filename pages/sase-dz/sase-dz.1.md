# Bead: sase-dz.1 — Raise the published sase-core-rs floor to 0.17.8

[Bead Pages](../README.md) / [sase-dz](README.md) / sase-dz.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rm](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rm/README.md) · **Assignee:** `sase-dz.1` · **Size:** small
**Created:** 2026-08-02 10:45:45 UTC · **Closed:** 2026-08-02 11:06:03 UTC
**Plan:** [202608/ci\_green\_restoration.md](https://github.com/sase-org/sase--plans/blob/main/202608/ci_green_restoration.md)

## Description

core-floor: bump the pyproject dependency window so the published-core smoke lane installs a sase-core-rs release that actually exposes every binding this repo calls, and refresh the recorded lock specifier to match.

## Notes

[2026-08-02T11:03:48Z · sase-dz.1] PROPOSED FOLLOW-UP: Stabilize bead mutation contention regression test - during this phase, full just test failed tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout under 24-worker load; single-process rerun passed.

[2026-08-02T11:06:03Z · sase-dz.1] Raised sase-core-rs floor to 0.17.8 in pyproject.toml/uv.lock and updated the smoke-tool expectation; verified validate_sase_core_rs_version --published-minimum, PyPI 0.17.8 binding smoke for all 245 scanned bindings, uv lock --check, targeted smoke-tool pytest, and single-process contention rerun. just check passes fmt/lint but stops at known plan links validate failure owned by publish-migration.

## Dependencies

- **Blocks:** [sase-dz.6](sase-dz.6.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-dz.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-dz.1/README.md) | [sase-dz.1](sase-dz.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`10843b5`](https://github.com/sase-org/sase/commit/10843b52209eb76d35040b3212800fe2e5cfd66b) | build(deps): raise sase-core-rs floor to 0.17.8 | [sase-dz.1](sase-dz.1.md) | 2026-08-02 11:09:11 |
