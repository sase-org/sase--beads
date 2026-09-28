# Bead: sase-1c1.11 — Fix the real perf-floors regressions

[Bead Pages](../README.md) / [sase-1c1](README.md) / sase-1c1.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ti](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ti.md) · **Assignee:** `sase-1c1.11` · **Size:** medium
**Created:** 2026-09-28 07:09:38 EDT · **Closed:** 2026-09-28 12:33:28 EDT
**Plan:** [202609/master\_ci\_green\_and\_0\_18\_release.md](https://github.com/sase-org/sase--plans/blob/main/202609/master_ci_green_and_0_18_release.md)

## Description

perf-floors: shorten the tmux socket directory (sase-18w), bring the smoke_sase_tool_runs harness cases up to the current tool-run contract, and fix the cached prompt-panel hint render regression behind the view-hints floor.

## Notes

[2026-09-28T15:29:39Z · sase-1c1.11--2] PROPOSED FOLLOW-UP: tests/test_config_schema.py::test_default_config_matches_public_schema again failed in final ToolRun 7009c2ce306e02d9445c25c3eeacc17e; the full parallel test lane reported 19 failed, 49,571 passed, and 19 skipped. Triage classified this run no_new_failures (18 KNOWN, 1 FLAKY). This workspace has no default-config or schema edits. Clean-base evidence: existing closed bead sase-u1 records the same node failing in the clean-tree full run 20260824T195813Z-ad9ed74aff24 (2 failures), and serially passing on master f56cf4333; sase-u1 links related process-global-state epic sase-j7 for triage.

[2026-09-28T16:33:28Z · sase-1c1.11--4] Implemented the tmux socket shortening and tool-run smoke contract updates; optimized cached prompt hint rendering (view-hints floor 2.606 ms; focused deck set 97 passed). Rust health, slow tests, phase 7, launch, agent disk-load, plugin catalog, and bead perf checks passed. Final check lint passed; full parallel test lane exited 1 with only 18 KNOWN and 1 FLAKY failure, including the config-schema flake tracked by sase-u1 and sase-j7. No phase epic symbols remain.

## Dependencies

- **Blocks:** [sase-1c1.13](sase-1c1.13.md) ◐ · ⧖ 2026-09-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1c1.11](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1c1.11.md) | [sase-1c1.11](sase-1c1.11.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5b68fd9`](https://github.com/sase-org/sase/commit/5b68fd9729fb751f379d8209bff70d72dbc5e109) | fix(perf): clear prompt hint regression and perf floors | [sase-1c1.11](sase-1c1.11.md) | 2026-09-28 12:36:10 EDT |
