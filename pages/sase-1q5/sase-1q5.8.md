# Bead: sase-1q5.8 — Mechanical re-measurement and follow-up handoff

[Bead Pages](../README.md) / [sase-1q5](README.md) / sase-1q5.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5k.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5k.linker.w0.md) · **Assignee:** `sase-1q5.8` · **Size:** small
**Created:** 2026-10-30 18:38:12 EDT · **Closed:** 2026-10-31 00:11:31 EDT
**Plan:** [202610/tui\_index\_lock\_speedup.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_index_lock_speedup.md)

## Description

remeasure-kit: teach tui_freeze_report to summarize slow agent loads by index-stage bucket and fallback reason, document the post-fix remeasure and GC decision recipe, and record the evidence-gated follow-ups.

## Notes

[2026-10-31T02:55:21Z · sase-1q5.8] remeasure-kit: tui_freeze_report now summarizes slow full agent loads (rate, index-stage buckets, artifact_source/repair_reason with unrecorded, top sources) from tui_agent_loads.jsonl plus .1 rotation; added docs/contribute/perf-runbook.md recipe "Re-measure after the index-lock fix". Focused tests: tests/test_tui_freeze_report_loads.py + tests/test_tui_freeze_report_tool.py (21 passed). epic-symbols clean. tui_perf.md not edited (tui_perf_rule=no).

[2026-10-31T02:55:26Z · sase-1q5.8] PROPOSED FOLLOW-UP: Re-run the GC track sase-1nc soak on a restarted TUI instance now that sase-1q5 has landed — its earlier soak failures measured this load regression.

[2026-10-31T02:55:31Z · sase-1q5.8] PROPOSED FOLLOW-UP: Run the one-time SASE_TUI_GC_CENSUS=1 census on a restarted instance to attribute residual 8M→19M block growth, before any retention work.

[2026-10-31T02:55:37Z · sase-1q5.8] PROPOSED FOLLOW-UP: Document then split the process-local artifact-index lock into reader and writer locks (research Step 4; evidence-gated).

[2026-10-31T02:55:43Z · sase-1q5.8] PROPOSED FOLLOW-UP: Immutable, versioned Agents read model (research Step 4; evidence-gated).

[2026-10-31T02:55:48Z · sase-1q5.8] PROPOSED FOLLOW-UP: JSON name-registry retention gap (research Step 4; evidence-gated).

[2026-10-31T02:55:54Z · sase-1q5.8] Stranded per-report full source-reconcile walk is not proposed: sase-1q5.4 already scoped reconcile deletions/watermarks to the walked workflow dirs and recorded AFTER wall=2.5s queries=3 for gh_sase-org__sase; earlier phase notes do not treat the walk as remaining work.

[2026-10-31T03:20:41Z · sase-1q5.8--1] just check failed on pyscripts Rule 1 because tools/_tui_freeze_report_loads.py was only imported without the .py basename and the new test file was untracked; added tracked refs in tests/test_tui_freeze_report_tool.py and docs/contribute/perf-runbook.md. pyscripts clean; 21 freeze-report tests passed; epic-symbols clean.

[2026-10-31T04:10:19Z · sase-1q5.8--2] PROPOSED FOLLOW-UP: tests/agents_sync/test_cli_names.py::test_repair_states_dispatches_and_reports_json NameError handle_agents_sync is not defined — KNOWN witness 5bb3b1e84235a7b3172d59e6f5669cbb from just check (tool 411fa721b0b9b807077f93a8bb1ac7d4); leftover of c489e94f1e test split; no owner task bead

[2026-10-31T04:11:31Z · sase-1q5.8--2] remeasure-kit landed: tui_freeze_report slow-load section (index buckets, artifact_source/repair_reason, top sources) plus perf-runbook recipe; 37 freeze-report tests passed; epic-symbols clean; just check 411fa721 no_new_failures (59255 passed, 1 KNOWN test_cli_names handle_agents_sync NameError recorded as follow-up)

## Dependencies

- **Depends on:** [sase-1q5.1](sase-1q5.1.md) ✓ · ⧖ 2026-10-30
- **Depends on:** [sase-1q5.2](sase-1q5.2.md) ✓ · ⧖ 2026-10-30
- **Depends on:** [sase-1q5.3](sase-1q5.3.md) ✓ · ⧖ 2026-10-30
- **Depends on:** [sase-1q5.4](sase-1q5.4.md) ✓ · ⧖ 2026-10-30
- **Depends on:** [sase-1q5.5](sase-1q5.5.md) ✓ · ⧖ 2026-10-30
- **Depends on:** [sase-1q5.6](sase-1q5.6.md) ✓ · ⧖ 2026-10-30
- **Depends on:** [sase-1q5.7](sase-1q5.7.md) ✓ · ⧖ 2026-10-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1q5.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q5.8.md) | [sase-1q5.8](sase-1q5.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1db087e`](https://github.com/sase-org/sase/commit/1db087e108345f1f353be7f1303ec6e6d7439734) | feat(tools): summarize slow agent loads in freeze report | [sase-1q5.8](sase-1q5.8.md) | 2026-10-31 00:13:15 EDT |
