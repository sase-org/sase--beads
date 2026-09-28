# Bead: sase-1c1.9 — Split the two oversized modules and clear the masked lint tail

[Bead Pages](../README.md) / [sase-1c1](README.md) / sase-1c1.9

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ti](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ti.md) · **Assignee:** `sase-1c1.9` · **Size:** medium
**Created:** 2026-09-28 07:09:35 EDT
**Plan:** [202609/master\_ci\_green\_and\_0\_18\_release.md](https://github.com/sase-org/sase--plans/blob/main/202609/master_ci_green_and_0_18_release.md)

## Description

toobig-lint-tail: split src/sase/core/tool_run.py and src/sase/tool/executor.py below 1000 lines along existing seams, then run every CI lint-job step in order and fix what validate, validate-committed-plans, and build-check report now that they finally run.

## Notes

[2026-09-28T12:04:03Z · sase-1c1.9] PROPOSED FOLLOW-UP: toobig tests red on 4 pre-existing files over 1000 lines (tests/ace/tui/visual/test_ace_png_snapshots_agents_final.py 1172, test_ace_png_snapshots_agents_sase_context.py 1013, tests/ace/tui/widgets/test_agent_bead_touch_rows.py 1180, tests/tool/test_settlement.py 1048) — identical on clean base, keeps just lint red; green-master owns (visual files to visual-lane, touch-rows to admin-center-tabs; tracks sase-1a9)

[2026-09-28T12:06:55Z · sase-1c1.9] Verified: toobig src green (tool_run.py 1154->572, tool_run_views.py 628, executor.py 1175->683, executor_triage.py 524); ruff check+format clean; mypy clean on all four files; symvision with exact Justfile flags green after removing 10 self-cleaned sase-1bt ToolRun* entries; sase validate green; validate-committed-plans green (5128 files, 0 errors); no --epic-symbol entries for sase-1c1.9. Targeted pytest (tests/tool + tool_runs TUI) shows failure set byte-identical to clean base (6 ledger failures from borrowed-venv binding skew only); full in-venv pytest runs in the verify monitor.

## Dependencies

- **Blocks:** [sase-1c1.13](sase-1c1.13.md) ◐ · ⧖ 2026-09-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1c1.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1c1.9.md) | [sase-1c1.9](sase-1c1.9.md) | 0 |
