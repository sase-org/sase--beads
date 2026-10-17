# Bead: sase-1m3.5 — Runs facet over the existing agent\_stats fold

[Bead Pages](../README.md) / [sase-1m3](README.md) / sase-1m3.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.1s.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.1s.linker.w0.md) · **Assignee:** `sase-1m3.5` · **Size:** small
**Created:** 2026-10-16 22:05:23 EDT · **Closed:** 2026-10-17 03:26:20 EDT
**Plan:** [202610/sase\_stats\_project.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_stats_project.md)

## Description

core-runs: fill the Runs facet and Patch rows by calling `agent_stats::query_run_stats` once, adding a code-repos-only run-commit count, and prove the numbers match today's Projects tab.

## Notes

[2026-10-17T07:25:50Z · sase-1m3.5] PROPOSED FOLLOW-UP: skipped decisions-web record (stats_decision_record=no) — stats count each fact at its durable source, and footers stamp only underivable facts

[2026-10-17T07:25:59Z · sase-1m3.5] PROPOSED FOLLOW-UP: sase-core clippy 1.95 nonminimal_bool deny in project_onboarding/classify.rs:500-502 (sase-1an) — sase tool run check exits 101 on the clean-base expression; classify.rs is unchanged

[2026-10-17T07:26:20Z · sase-1m3.5] Filled the Runs facet: additive agent_stats excluded_commit_repo_names skips record-repo meta_commits in project/Patch folds (empty set matches today's counts); query_run_stats is called once per project_stats query; if_runs, unregistered rows, missing-index, and a fixture oracle vs query_run_stats all pass. sase tool run check in sase-core is blocked only by clean-base clippy sase-1an.

## Dependencies

- **Blocks:** [sase-1m3.10](sase-1m3.10.md) ◐ · ⧖ 2026-10-16
- **Blocks:** [sase-1m3.11](sase-1m3.11.md) ◐ · ⧖ 2026-10-16
- **Depends on:** [sase-1m3.4](sase-1m3.4.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1m3.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1m3.5/README.md) | [sase-1m3.5](sase-1m3.5.md) | 0 |
