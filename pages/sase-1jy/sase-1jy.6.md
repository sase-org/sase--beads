# Bead: sase-1jy.6 — Persistent scope-key cache so live ticks stat instead of read

[Bead Pages](../README.md) / [sase-1jy](README.md) / sase-1jy.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zo](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zo.md) · **Assignee:** `sase-1jy.6` · **Size:** medium
**Created:** 2026-10-11 11:18:38 EDT · **Closed:** 2026-10-11 18:41:55 EDT
**Plan:** [202610/wait\_checks\_scoped\_view.md](https://github.com/sase-org/sase--plans/blob/main/202610/wait_checks_scoped_view.md)

## Description

scope-key-cache: persist per-artifact scope keys fingerprinted by agent_meta.json stat data, written only by wait_checks and read by runners, so selection costs one stat per artifact instead of one JSON read.

## Notes

[2026-10-11T22:41:42Z · sase-1jy.6--1] PROPOSED FOLLOW-UP: check has 4 pre-existing failures reproducing identically on clean base (git stash): test_project_shown_when_no_patch (expects Project:my_project, gets Project:fake), test_facade_rehydrates_valid_tale_and_ordered_schema (schema order decisions.<id>.corrects vs .answer + bead_id), test_tui_app_import_stays_under_startup_budget (3516 modules vs 3513 cap), test_workflow_snapshot_render_reads_state_once_and_uses_parsed_data (expects Project:sase, gets Project:tmp) — none touch wait/scope-cache files

[2026-10-11T22:41:46Z · sase-1jy.6--1] PROPOSED FOLLOW-UP: check triage listed 3 more NEW items that pass in isolation on both trees (muse_usage_probe missed-mint, settlement_retention supervisor-sigterm, monitor_result persist-waits-for-starter) — load-flaky under full check, not scope-cache related

[2026-10-11T22:41:55Z · sase-1jy.6--1] scope-key cache done: new tests/test_wait_dependency_scope_cache.py 7 pass, neighboring wait suites pass (21 total incl. scoped_views + plan handoffs), ruff+mypy clean on touched files, docs/axe.md documents cache; full check triage: 7 NEW items all unrelated — 4 reproduce identically on clean base (recorded as follow-ups), 3 pass in isolation on both trees (load-flaky)

## Dependencies

- **Depends on:** [sase-1jy.4](sase-1jy.4.md) ✓ · ⧖ 2026-10-11
- **Depends on:** [sase-1jy.5](sase-1jy.5.md) ✓ · ⧖ 2026-10-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jy.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jy.6.md) | [sase-1jy.6](sase-1jy.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d289b66`](https://github.com/sase-org/sase/commit/d289b664a675a7a32f8cdb5540938190021a1580) | feat(wait): persist per-artifact scope-key cache for wait\_checks ticks | [sase-1jy.6](sase-1jy.6.md) | 2026-10-11 18:43:04 EDT |
