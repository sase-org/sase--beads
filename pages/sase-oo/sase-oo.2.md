# Bead: sase-oo.2 — Stop asserting zero samples and meaningless shares in Perf latency rows

[Bead Pages](../README.md) / [sase-oo](README.md) / sase-oo.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04y](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04y.md) · **Assignee:** `sase-oo.2` · **Size:** small
**Created:** 2026-08-17 12:01:58 EDT · **Closed:** 2026-08-17 12:43:49 EDT
**Plan:** [202608/statistics\_tab\_accuracy\_round\_two.md](https://github.com/sase-org/sase--plans/blob/main/202608/statistics_tab_accuracy_round_two.md)

## Description

perf-latency: make the By Subsystem Count column render an unknown count as an em dash instead of 0, remove the incommensurable Share denominator for that grouping, and define the Launch hero tile's statistic in the Perf legend.

## Notes

[2026-08-17T16:43:13Z · sase-oo.2] PROPOSED FOLLOW-UP: just check lint (feature flags) fails on live flag bead sase-om with no definition for key completion_refresh_on_update — unrelated to Perf latency; the open flag bead exists but this tree has no matching flag definition.

[2026-08-17T16:43:49Z · sase-oo.2] Verified F1/F2/F10: subsystem rows without a counter now emit count=None and render as an em dash (Workflows/Axe keep populated p50/p95/max); By Subsystem share is 0.0 and the Share column is omitted while By Provider/By Workflow still show Share; Launch legend is 'p95 total launch time' and the help Percentiles (logs) row no longer calls Launch a median. fmt/ruff/mypy/symvision passed; 41 focused tests in test_views_perf, test_statistics_perf, test_statistics_help_modal, and test_statistics_legends_states passed. just check's feature-flag lint failed on unrelated live flag bead sase-om (no completion_refresh_on_update definition); recorded as PROPOSED FOLLOW-UP. Scoped selection escalated to FULL_SUITE because _view_models.py is in the broadening set.

[2026-08-17T16:45:08Z · sase-oo.2] Verified F1/F2/F10: subsystem rows without a counter emit count=None and render as an em dash; By Subsystem omits Share while By Provider/By Workflow still show it; Launch legend is p95 total launch time. fmt/ruff/mypy/symvision passed; 41 focused tests in test_views_perf, test_statistics_perf, test_statistics_help_modal, and test_statistics_legends_states passed.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-oo.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-oo.2/README.md) | [sase-oo.2](sase-oo.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`05325ce`](https://github.com/sase-org/sase/commit/05325ceb727d7fa233af4ec7e6ca041fd829a8a5) | fix(stats): stop inventing Perf latency counts and shares | [sase-oo.2](sase-oo.2.md) | 2026-08-17 12:46:10 EDT |
