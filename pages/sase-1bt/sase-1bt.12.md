# Bead: sase-1bt.12 — Remove ace\_tool\_runs, add goldens, inspect live, and bench

[Bead Pages](../README.md) / [sase-1bt](README.md) / sase-1bt.12

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tc.md) · **Assignee:** `sase-1bt.12` · **Size:** medium
**Created:** 2026-09-27 18:32:51 EDT · **Closed:** 2026-09-28 13:33:46 EDT
**Plan:** [202609/tool\_runs\_tui\_surfaces.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_runs_tui_surfaces.md)

## Description

cutover: bench j/k and idle ticks with the flag on and off, delete the flag's Off branches and close its flag bead, generate and inspect deterministic goldens for every surface, and inspect live captures of real runs.

## Notes

[2026-09-28T16:53:11Z · sase-1bt.12] PROPOSED FOLLOW-UP: tests/test_config_schema.py::test_default_config_matches_public_schema fails on the clean base tree too (ace.keymaps.tool_runs rejects run_tool/stop_run added by sase-1bt.11); regenerate the keymaps schema block

[2026-09-28T17:33:46Z · sase-1bt.12] Cutover done. Bench (large-list j/k baseline, flag off vs on): next p95 49.81->21.95ms, prev 39.38->22.20ms, panel-nav 51.61->64.53 / 81.52->80.46ms — no regression. Flag ace_tool_runs fully removed (26 source sites, flag.py, registry, schema; flag bead sase-1bv closed). 26 deterministic PNG goldens added in test_ace_png_snapshots_tool_runs.py, all inspected, 9/9 pass x3 runs. Defects found+fixed: admin detail ANSI leak (Text passthrough), monitor availability clobber, picker 0-runs merge (message arg + n_runs), picker omits 0 calls. Verified: 15k+ unit tests pass, mypy/ruff/symvision/flag-checks clean. Pre-existing test_config_schema keymaps failure recorded as follow-up (reproduces on clean base).

## Dependencies

- **Depends on:** [sase-1bt.11](sase-1bt.11.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bt.13](sase-1bt.13.md) ◐ · ⧖ 2026-09-27
- **Depends on:** [sase-1bt.8](sase-1bt.8.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1bt.9](sase-1bt.9.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bt.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bt.12/README.md) | [sase-1bt.12](sase-1bt.12.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`02ff491`](https://github.com/sase-org/sase/commit/02ff49120fe5dae7773f5424e99045fcd9c4e25a) | feat(ace-tui): cut over ToolRun surfaces, retire ace\_tool\_runs (sase-1bt.12) | [sase-1bt.12](sase-1bt.12.md) | 2026-09-28 13:36:04 EDT |
