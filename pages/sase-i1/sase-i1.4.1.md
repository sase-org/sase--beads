# Bead: sase-i1.4.1 — Restore the published binding floor

[Bead Pages](../README.md) / [sase-i1.4](sase-i1.4.md) / sase-i1.4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-i1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i1.land/README.md) · **Assignee:** `sase-i1.4.1` · **Size:** small
**Created:** 2026-08-09 09:05:22 EDT · **Closed:** 2026-08-09 09:31:49 EDT
**Plan:** [202608/bead\_search\_regex\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_search_regex_landing.md)

## Description

published-floor: require the already-published regex-capable core, refresh the lock, smoke the minimum wheel, and restore normal-install compatibility.

## Notes

[2026-08-09T13:31:49Z · sase-i1.4.1] Concurrent epic sase-i3.3 (commit b73609337) already raised pyproject.toml/uv.lock sase-core-rs floor to >=0.21.2, fixed tests/test_sase_core_rs_telemetry_smoke_tool.py's hardcoded 0.21.1 assertion, and froze the snooze-test fixture clock. Fast-forwarded local checkout to pick up that commit (working tree diff was byte-identical to what this phase would have produced independently) rather than land a duplicate commit. Verified in this session: (1) tools/smoke_sase_core_rs_telemetry --print-minimum pyproject.toml reports 0.21.2; (2) tools/validate_sase_core_rs_version --published-minimum passes; (3) throwaway-venv smoke installing published sase-core-rs==0.21.2 only, calling bead_search(..., regex=True) against a freshly-built valid beads store, matches both a plain substring query and a ^Alpha regex anchor; (4) just install rebuilds the local sase_core_rs override cleanly; (5) focused tests/main/test_bead_fast_path.py, tests/test_core_facade/test_bead_read.py, tests/test_bead/test_cli_search.py, tests/test_bead/test_project_rust_delegation.py (52 tests) pass via .venv/bin/python -m pytest (preserving the local core override, not bare uv run); (6) just check passes clean (fmt, lint gates, symvision, scoped tests). No local commit was needed since master already contains the exact required change.

## Dependencies

- **Blocks:** [sase-i1.4.3](sase-i1.4.3.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-i1.4.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i1.4.1/README.md) | [sase-i1.4.1](sase-i1.4.1.md) | 0 |
