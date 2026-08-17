# Bead: sase-oo.3 — Make the All time window and empty-window states honest

[Bead Pages](../README.md) / [sase-oo](README.md) / sase-oo.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04y](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04y.md) · **Assignee:** `sase-oo.3` · **Size:** medium
**Created:** 2026-08-17 12:01:59 EDT · **Closed:** 2026-08-17 12:29:23 EDT
**Plan:** [202608/statistics\_tab\_accuracy\_round\_two.md](https://github.com/sase-org/sase--plans/blob/main/202608/statistics_tab_accuracy_round_two.md)

## Description

range-window: replace the epoch-derived All time absolute label, clamp the Overview runs-over-time buckets to the observed data instead of emitting one row per day since 1970, and stop the run-count empty state from hiding log-backed Activity and Plans & Questions data.

## Notes

[2026-08-17T16:28:59Z · sase-oo.3] PROPOSED FOLLOW-UP: `just check`'s `lint (feature flags)` gate is currently red repo-wide: rule 8 reports live flag bead sase-om (key completion_refresh_on_update) has no definition. This is from the unrelated sase-oc shell-completion epic (phases .5/.6/.8 still in_progress), not from Statistics tab work; verified via direct ruff/mypy/pytest runs on the changed files/tests instead of the blocked full `just check`.

[2026-08-17T16:29:23Z · sase-oo.3] F4: resolve_preset('all') no longer derives an absolute label from the epoch sentinel; it now reads 'through {end} · start bounded by retained data' (ranges.py + test_ranges.py assert no 1969/1970). F5: build_overview_view trims leading/trailing zero-run buckets and, when the trimmed sequence exceeds 96 rows, groups adjacent buckets into equal-width chunks (_clamp_overview_buckets in _view_builders.py), with the Overview panel title disclosing aggregation only when it happens (e.g. 'Runs over time · 2-day buckets'); OverviewView.bucket_group_seconds added, feeding the Agents Run sparkline unchanged. F11: the run-count empty-state gate is now per-view (_current_view_is_empty) — activity/plans_questions use their own ActivityView.empty/PlansQuestionsView.empty (log-backed skill/memory/plan/question data), while overview/projects/providers keep the run-derived check; runners/xprompts/perf still self-manage. Empty-state copy is now view-specific via _empty_state_message. Verified: ruff check+format, mypy (src/ only, per pyproject scope) clean on all changed files; pytest tests/stats/ tests/ace/tui/test_statistics*.py (185 tests) and the statistics PNG visual snapshot suite (16, run with -m visual) all pass with zero golden diffs, confirming no unintended regressions for the default/small-range path. Whole-repo 'just check' is blocked repo-wide by an unrelated lint(feature flags) failure from the concurrent sase-oc epic (flag bead sase-om); noted as a PROPOSED FOLLOW-UP on this bead, not caused by this phase.

[2026-08-17T16:30:24Z · sase-oo.3] Verified: F4 (all-time label), F5 (overview bucket clamping), F11 (per-view empty states) implemented and tested; 185 statistics-related pytest tests + 16 PNG visual snapshots pass; ruff/mypy clean on changed files. Unrelated feature-flag lint failure from concurrent sase-oc epic recorded as proposed follow-up.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-oo.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-oo.3/README.md) | [sase-oo.3](sase-oo.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`56dbeb2`](https://github.com/sase-org/sase/commit/56dbeb2f6d9715dc6710eb4ba0e78c9dc408fd0b) | fix(stats): make All time window and empty-window states honest | [sase-oo.3](sase-oo.3.md) | 2026-08-17 12:31:12 EDT |
