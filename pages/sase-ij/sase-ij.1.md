# Bead: sase-ij.1 — Derive the telemetry smoke test's expected minimum from pyproject

[Bead Pages](../README.md) / [sase-ij](README.md) / sase-ij.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wq](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wq/README.md) · **Assignee:** `sase-ij.1` · **Size:** small
**Created:** 2026-08-09 15:17:39 EDT · **Closed:** 2026-08-09 15:31:49 EDT
**Plan:** [202608/core\_window\_ratchet.md](https://github.com/sase-org/sase--plans/blob/main/202608/core_window_ratchet.md)

## Description

derive-floor-literal: replace the hardcoded "0.21.3" golden assertion in tests/test_sase_core_rs_telemetry_smoke_tool.py with a value derived from pyproject.toml, so a floor change stops requiring a test edit.

## Notes

[2026-08-09T19:30:05Z · sase-ij.1] PROPOSED FOLLOW-UP: Fix markdown formatting drift in sase/memory/build_and_run.md — just check currently fails fmt-md-check on this pre-existing memory-file formatting issue, and memory files require owner approval to edit.

[2026-08-09T19:31:49Z · sase-ij.1] Updated tests/test_sase_core_rs_telemetry_smoke_tool.py to derive the repo expected minimum from pyproject.toml and added a tmp_path happy-path parse case. Verified: just install; .venv/bin/pytest tests/test_sase_core_rs_telemetry_smoke_tool.py -q (4 passed); .venv/bin/ruff check tests/test_sase_core_rs_telemetry_smoke_tool.py; git diff --check; just test-scoped (399 passed). just check was attempted but stopped on pre-existing fmt-md-check failure in sase/memory/build_and_run.md; recorded as PROPOSED FOLLOW-UP.

[2026-08-09T19:32:56Z · sase-ij.1] Verified just install; focused telemetry smoke test passed; ruff check passed; git diff --check passed; just test-scoped passed with 399 tests. just check was attempted but blocked by pre-existing markdown formatting in sase/memory/build_and_run.md.

## Dependencies

- **Blocks:** [sase-ij.2](sase-ij.2.md) ◐ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ij.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.1/README.md) | [sase-ij.1](sase-ij.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`755987f`](https://github.com/sase-org/sase/commit/755987ff5b42418f6d411eec7373ce524184a0b3) | test: derive telemetry smoke core floor from pyproject | [sase-ij.1](sase-ij.1.md) | 2026-08-09 15:33:31 EDT |
