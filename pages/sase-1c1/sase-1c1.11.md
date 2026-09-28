# Bead: sase-1c1.11 — Fix the real perf-floors regressions

[Bead Pages](../README.md) / [sase-1c1](README.md) / sase-1c1.11

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ti](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ti.md) · **Assignee:** `sase-1c1.11` · **Size:** medium
**Created:** 2026-09-28 07:09:38 EDT
**Plan:** [202609/master\_ci\_green\_and\_0\_18\_release.md](https://github.com/sase-org/sase--plans/blob/main/202609/master_ci_green_and_0_18_release.md)

## Description

perf-floors: shorten the tmux socket directory (sase-18w), bring the smoke_sase_tool_runs harness cases up to the current tool-run contract, and fix the cached prompt-panel hint render regression behind the view-hints floor.

## Notes

[2026-09-28T15:29:39Z · sase-1c1.11--2] PROPOSED FOLLOW-UP: tests/test_config_schema.py::test_default_config_matches_public_schema rejected ace.keymaps.tool_runs after the 97 deck tests passed in a focused run; no default-config or schema files are changed. Existing sase-u1 records the same node failing on a clean tree, and related process-global-state epic sase-j7 should triage current evidence.

## Dependencies

- **Blocks:** [sase-1c1.13](sase-1c1.13.md) ◐ · ⧖ 2026-09-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1c1.11](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1c1.11.md) | [sase-1c1.11](sase-1c1.11.md) | 0 |
