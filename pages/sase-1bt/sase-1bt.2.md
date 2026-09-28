# Bead: sase-1bt.2 — Per-run detail projection with stage timeline and witness counts in sase-core

[Bead Pages](../README.md) / [sase-1bt](README.md) / sase-1bt.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tc.md) · **Assignee:** `sase-1bt.2` · **Size:** medium
**Created:** 2026-09-27 18:32:36 EDT · **Closed:** 2026-09-27 20:27:18 EDT
**Plan:** [202609/tool\_runs\_tui\_surfaces.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_runs_tui_surfaces.md)

## Description

core-run-detail: add tool_run_detail, which returns one run's brief, safe argv, millisecond-normalized stages, the reference run's expected stages, triage items with cross-run and cross-agent witness counts, child runs, log metadata, and pruning facts, with its binding.

## Notes

[2026-09-28T00:26:39Z · sase-1bt.2] PROPOSED FOLLOW-UP: sase-core just check clippy gate fails on clean base tree (rust-1.98 lints too_many_arguments at launch_scratch_liveness.rs:300 and manual_repeat_n at :477); needs allow/refactor so the gate is green again

[2026-09-28T00:27:18Z · sase-1bt.2] tool_run_detail landed in sase-core with PyO3 binding: brief+display_argv, ms stages with per-stage class counts, reference expected stages (live or settled-early only), witnessed triage items (NEW/UNKNOWN/unlabeled/KNOWN/FLAKY, locators capped at 3, limit 50/200, window 7d/30d), child briefs, log metadata without private argv, detail_pruned. Verified: just fmt+fast clean, 171 sase_core tool_run tests and 8 sase_core_py telemetry tests pass incl. 6 new detail tests and the binding round-trip. just check gate still fails only on 2 pre-existing clippy lints in untouched launch_scratch_liveness.rs (recorded as PROPOSED FOLLOW-UP); no epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-1bt.1](sase-1bt.1.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bt.7](sase-1bt.7.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bt.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bt.2/README.md) | [sase-1bt.2](sase-1bt.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@830e900`](https://github.com/sase-org/sase-core/commit/830e9003ea4139a58fc907aae8f301f652e1657e) | feat(tool-run): add tool\_run\_detail projection with stage timeline and witness counts | [sase-1bt.2](sase-1bt.2.md) | 2026-09-27 20:29:47 EDT |
