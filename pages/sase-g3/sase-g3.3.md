# Bead: sase-g3.3 — A named, measured compensating action for a missing or stale contexts baseline

[Bead Pages](../README.md) / [sase-g3](README.md) / sase-g3.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tx](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tx/README.md) · **Assignee:** `sase-g3.3` · **Size:** medium
**Created:** 2026-08-06 08:55:28 EDT · **Closed:** 2026-08-06 10:25:17 EDT
**Plan:** [202608/selection\_soundness.md](https://github.com/sase-org/sase--plans/blob/main/202608/selection_soundness.md)

## Description

compensate: `context-baseline-missing` and `context-baseline-stale` are recorded but are absent from `FULL_SUITE_RULES` and widen nothing, so roughly half of scoped runs narrow silently; choose and implement a compensating action on the backtest's measured recall evidence, and record it as a named rule.

## Notes

[2026-08-06T14:23:31Z · sase-g3.3] PROPOSED FOLLOW-UP: tools/selection_backtest run outside the venv reports every commit as `empty-ground-truth` — `find_tests_touching` swallows the `coverage` ImportError (correct for selection, silently null for a measurement harness), so `tools/selection_backtest --limit 150` printed a 0-commit report that reads like a data problem; the harness should refuse to run when coverage is not importable.

[2026-08-06T14:24:01Z · sase-g3.3] PROPOSED FOLLOW-UP: cached contexts baselines are ranked by mtime alone, so a thin local baseline displaces a fuller CI one — 6b0976bcb.sqlite on athena has 14,349 contexts / 7.3 MB against 96183d71b.sqlite's 58,770 / 49 MB, and resolve_baseline prefers the thin one; rank or reject on recorded coverage breadth, not recency.

[2026-08-06T14:24:29Z · sase-g3.3] PROPOSED FOLLOW-UP: tests/test_plan_display.py::test_malformed_header_block_leaves_authored_metadata_visible fails on a clean master tree at 4651ed199 (validation_ok is False for a malformed header block) — reproduced with the working tree stashed, so it predates this phase; likely fallout from fa8fc69e4.

[2026-08-06T14:24:43Z · sase-g3.3] PROPOSED FOLLOW-UP: the `_app_layout.py` shape is still only half covered — widely-executed-but-shallowly-imported modules keep 42 of 91 covering test files out of the depth-3 closure, and directory-mirror expansion is not the answer (tests/ace/tui/** is 35.7% of the suite, above the escalation ratio); a targeted rule for that shape is the remaining option (epic plan candidate 3).

[2026-08-06T14:24:52Z · sase-g3.3] PROPOSED FOLLOW-UP: `just selection-health` now reports 1 false negative (tests/ace/tui/widgets/test_prompt_codeblock_highlight.py::test_codeblock_band_replaces_cursor_line_fill_but_not_cursor, head fa8fc69e46c4) excluded by a scoped run that HAD a contexts baseline — this phase compensates for a missing baseline and does not address it; triage whether it is a real miss or the known load-sensitive flake family.

[2026-08-06T14:25:17Z · sase-g3.3] Chose depth+1 (epic plan candidate 1) on measured evidence and shipped it as the named rule no-baseline-depth-boost: when the contexts baseline is missing or stale, the closure walks one extra hop instead of escalating; the rule is deliberately NOT in FULL_SUITE_RULES (a baseline is absent in 20 of 39 recorded scoped runs, so escalating would send half the lane to the full suite). select_tests now consults contexts before the closure so baseline status can set the depth, and the manifest gained effective_depth (schema 2 -> 3). MEASURED with just selection-backtest --limit 150 --include-descendant-baseline --baseline 96183d71b at 4651ed199, 63 commits with usable ground truth (3 faithful ancestor replays, 60 approximate descendant ones), closure-only arm: mean recall 96.0% -> 99.2%, p10 85.3% -> 100%, worst 23.5% -> 81.3%, blind-spot commits 13 -> 5, missed test files 116 -> 11 (91% of the blind spot recovered). Re-running the backtest AFTER the change reproduces those numbers through the real code path with no-baseline-depth-boost in the closure arm's rules and the union arm (baseline present) unchanged at 6.4% median / 23 escalations, confirming the boost applies only when there is no usable baseline. COST: selection size roughly doubles when no baseline is cached (median 6.4% -> 8.8% of the suite, p90 11.9% -> 21.2%; src/sase/agent_lanes.py 110 -> 255 files, 1117 -> 2514 tests, 57s -> 164s serial on athena), replayed escalation rate 23/63 -> 28/63 on whole-commit historical diffs; contract-set-only changes (the median scoped run, 34 files) are unaffected because they seed no closure. ACCEPTANCE on the plan's sharpest case: a real edit inside src/sase/ace/tui/_app_layout.py's compose body with contexts forced absent recovers 27 of the 69 previously missed covering test files (recall 24.2% -> 53.8% of 91) at 14.2% of the suite, still scoped. Candidate 2 (directory-mirror) measured and REJECTED: tests/ace/tui/** alone is 831 files = 35.7% of the suite, above the 0.25 ratio, so it degenerates into a full run. VERIFIED: 160 targeted tests pass (selection engine, contexts, select_tests CLI, backtest, health, scoped summary); five new tests pin the rule, its composition with the rename/delete hop, and that it never forces the full suite; just lint clean; just check-full green apart from two failures unrelated to this change - tests/test_plan_display.py::test_malformed_header_block_leaves_authored_metadata_visible reproduces on a stashed clean tree, and tests/ace/tui/test_agent_bulk_kill_edit.py::test_bulk_waiting_agents_mount_forced_artifact_prompts passes in isolation and in an earlier full run (known load-sensitive flake family). docs/development.md documents the rule and the before/after table. Changes are staged in the working tree, not committed.

[2026-08-06T14:26:00Z · sase-g3.3] no-baseline-depth-boost rule: reverse-import closure walks one hop deeper when the coverage-contexts baseline is missing or stale, instead of escalating. Backtest over 63 commits (closure-only arm): mean recall 96.0% -> 99.2%, p10 85.3% -> 100%, worst 23.5% -> 81.3%, blind-spot commits 13 -> 5, missed files 116 -> 11; median selection 6.4% -> 8.8%. Union arm (baseline present) unchanged. 160 targeted tests pass; just lint clean; just check-full green except two failures reproduced on a stashed clean tree / known flake family, both recorded as PROPOSED FOLLOW-UP notes.

## Dependencies

- **Depends on:** [sase-g3.1](sase-g3.1.md) ✓ · ⧖ 2026-08-06
- **Blocks:** [sase-g3.5](sase-g3.5.md) ✓ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-g3.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-g3.3/README.md) | [sase-g3.3](sase-g3.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b4c4c18`](https://github.com/sase-org/sase/commit/b4c4c182e1a68037fed639215c4d35ebbeab7e15) | feat(test-selection): walk one hop deeper when no contexts baseline is usable | [sase-g3.3](sase-g3.3.md) | 2026-08-06 10:26:47 EDT |
