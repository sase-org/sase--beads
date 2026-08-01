# Bead: sase-d9.5 — Clan commits lane and commit view hints

[Bead Pages](../README.md) / [sase-d9](README.md) / sase-d9.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.r3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.r3/README.md) · **Assignee:** `sase-d9.5` · **Size:** medium
**Created:** 2026-08-01 12:39:20 UTC · **Closed:** 2026-08-01 14:27:08 UTC
**Plan:** [202608/clan\_summary\_view\_hints.md](https://github.com/sase-org/sase--plans/blob/main/202608/clan_summary_view_hints.md)

## Description

commits: aggregate member commits from already-loaded step output into a new COMMITS context lane and register each rendered commit as a commit-view hint so the clan document supports the commit viewer, raw diff opening, and SHA copying.

## Notes

[2026-08-01T14:11:09Z · sase-d9.5] PROPOSED FOLLOW-UP: Fix existing pyscripts Rule 2 placement violation — tests/ace/tui/widgets/test_agent_display_clan_context_hints.py references tools/sase_bead while tests/ace/tui/tools/ is the closer allowed directory, causing just check to stop after Ruff and mypy.

[2026-08-01T14:24:06Z · sase-d9.5] PROPOSED FOLLOW-UP: Stabilize suite-gate SIGKILL integration test under parallel load — tests/test_suite_gate_integration.py::test_scaled_suite_runs_share_capacity_and_release_after_sigkill timed out in the 11-worker full suite but passed alone in 20.86s.

[2026-08-01T14:24:21Z · sase-d9.5] PROPOSED FOLLOW-UP: Reconcile bead rich-ANSI closed-phase golden — tests/test_bead/test_cli_show_style.py::test_show_closed_phase_with_markdown_rich_ansi_snapshot reproducibly differs only in existing Rich ANSI reset/background codes (for example bold versus bold+default-background), unrelated to clan commit rendering.

[2026-08-01T14:27:08Z · sase-d9.5] Verified clan COMMITS aggregation de-duplicates shared SHAs with member attribution, renders pre-enrichment in fold order, registers only commit-view hints at level 3, and routes selections to the commit modal/raw diff editor. Focused commit tests pass; Ruff, mypy, Symvision, SASE/plan validation pass; dedicated visual suite passes (400 passed, 1 skipped). Full suite reached 25239 passed with two unrelated failures recorded as proposed follow-ups, and the pre-existing pyscripts placement failure was also recorded.

[2026-08-01T14:28:25Z · sase-d9.5] Verified clan COMMITS lane ordering, SHA deduplication with multi-member attribution, pre-enrichment rendering, level-3 commit hint routing, 32 focused tests, 400 passed/1 skipped visual tests, Ruff, mypy, Symvision, and plan validation; full suite reached 25,239 passed/7 skipped with two unrelated failures documented as proposed follow-ups.

## Dependencies

- **Depends on:** [sase-d9.3](sase-d9.3.md) ✓
- **Blocks:** [sase-d9.7](sase-d9.7.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-d9.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-d9.5/README.md) | [sase-d9.5](sase-d9.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`1b29a74`](https://github.com/sase-org/sase/commit/1b29a74183de99e9e50cec95b1287e7188511939) | feat(ace): add clan commit context lane | [sase-d9.5](sase-d9.5.md) | 2026-08-01 14:29:20 |
