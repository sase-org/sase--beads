# Bead: sase-fq.1 — Bump the published sase-core-rs window to 0.18.1

[Bead Pages](../README.md) / [sase-fq](README.md) / sase-fq.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tq](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tq/README.md) · **Assignee:** `sase-fq.1` · **Size:** small
**Created:** 2026-08-05 21:05:38 EDT · **Closed:** 2026-08-05 21:43:05 EDT
**Plan:** [202608/ci\_master\_red\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202608/ci_master_red_recovery.md)

## Description

core-window: raise the pyproject sase-core-rs constraint (and uv.lock) from >=0.17.15,<0.18.0 to >=0.18.1,<0.19.0 so the bead relocation binding sase already calls is guaranteed present.

## Notes

[2026-08-06T01:43:05Z · sase-fq.1] Bumped pyproject.toml/uv.lock sase-core-rs window from >=0.17.15,<0.18.0 to >=0.18.1,<0.19.0 and fixed the now-stale hardcoded 0.17.15 assertion in tests/test_sase_core_rs_telemetry_smoke_tool.py::test_declared_minimum_tracks_pyproject_dependency. Verified: breaking-change audit clean (zero repo hits for the 3 symbols removed in 0.18.0); just install; ruff/mypy/validate_sase_core_rs_version --published-minimum/sase validate all pass (symvision failure on progress_fingerprint is pre-existing, owned by sibling phase sase-fq.2); published-core-minimum-smoke reproduced against a clean venv pinned to sase-core-rs==0.18.1 (smoke_sase_core_rs_telemetry and check_sase_core_rs_bindings both pass, 248/248 bindings present); tests/test_check_sase_core_rs_bindings_tool.py and tests/test_bead/test_sync_conflict_recovery.py pass (11/11). Full just test: first run showed 4 failures - the pyproject-coupled version-string test (now fixed) plus 3 timing-sensitive tests (test_stall_watchdog x2, test_kill_during_retry_wait_stops_before_another_subprocess) that pass individually in isolation, consistent with the epic's documented R6 parallelism-under-load flakiness (unrelated to this change, out of scope for this phase). A second full run timed out due to a concurrent sibling sase workspace (sase_12) saturating the host with its own pytest run, not a regression from this change.

## Dependencies

- **Blocks:** [sase-fq.7](sase-fq.7.md) ◐ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fq.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fq.1/README.md) | [sase-fq.1](sase-fq.1.md) | 0 |
