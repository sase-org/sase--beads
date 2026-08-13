# Bead: sase-l6.1 — Per-lane enrichment telemetry

[Bead Pages](../README.md) / [sase-l6](README.md) / sase-l6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zw](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zw.md) · **Assignee:** `sase-l6.1` · **Size:** small
**Created:** 2026-08-13 15:23:48 EDT · **Closed:** 2026-08-13 16:00:39 EDT
**Plan:** [202608/sase\_context\_incremental.md](https://github.com/sase-org/sase--plans/blob/main/202608/sase_context_incremental.md)

## Description

trace: add a per-lane trace span and a repeatable measurement script for detail-header enrichment, record the baseline in a real terminal, and document the capture recipe so every later phase has a real before/after.

## Notes

[2026-08-13T19:59:57Z · sase-l6.1] PROPOSED FOLLOW-UP: `just check`'s symvision lint gate fails on master (pre-existing, unrelated to this phase): --epic-symbol whitelist entries reference bead sase-kz.5 (SnippetExpansionPlan/SnippetSessionTransition/SnippetSpan/SnippetStop/apply_snippet_session_event/clear_snippet_session/retreat_snippet_session), which is now closed. Remove the stale --epic-symbol entries (see sase/memory/symvision.md) and clean up the affected symbols wherever the whitelist is declared.

[2026-08-13T20:00:39Z · sase-l6.1] Deliverables landed:
- tui_trace spans in build_detail_header_summary (widgets/prompt_panel/_agent_display_header_summary.py): one parent span widget.prompt_panel.build_detail_header_summary (carries agent=cl_name, cache_state=cold|warm process-local marker) plus 12 child spans, one per resolver (xprompts_used, bead_display, plan_enrichment, slow_tool_sources, agent_page_url, linked_delta_groups, artifact_file_paths, memory_reads, skill_uses, opened_workspaces, delta_entries, wait_bead_statuses). Free when SASE_TUI_TRACE unset (reuses the existing tui_trace guard).
- tests/perf/bench_detail_header_summary.py: committed measurement script reproducing the plan's two baseline tables by driving the *same* production spans (not a re-timed copy), against a hermetic in-memory fixture by default and real ~/.sase agents via --include-home. `pytest -s -m slow tests/perf/bench_detail_header_summary.py` passes.
- docs/perf_runbook.md: new "SASE CONTEXT enrichment (detail-header summary)" section documenting the span tree, the cache_state marker, the jq slice recipe, and the bench script invocation.
- tests/ace/tui/widgets/test_agent_display_header_summary_trace.py: unit coverage for disabled-by-default, all 13 spans present when enabled, and cold-then-warm cache_state sequencing.

Baseline captured (2026-08-13, athena, live ~/.sase, 20 non-clan agents via --include-home):
  resolver              cold_p50  cold_max  warm_p50  warm_max (ms)
  skill_uses              203.2     232.2      6.3     219.3
  memory_reads              7.5     152.6    145.9     152.7
  artifact_file_paths      92.1     793.8     90.5     923.6
  plan_enrichment           0.2     171.7      0.2     172.6
  slow_tool_sources         0.2     123.3     24.3      74.5
  delta_entries             0.1      53.2      0.4      36.6
  opened_workspaces         0.2       6.8      0.2       2.6
  xprompts_used             0.1       2.1      0.1      16.1
  linked_delta_groups       0.0       0.0      0.0       0.0
  wait_bead_statuses        0.0     956.9      0.0       0.0
  agent_page_url            0.0       0.0      0.0       0.0
  bead_display              0.0       0.0      0.0       0.0
  agent_commit_groups (standalone, free lane) 0.0 / 0.0
artifact_file_paths breakdown: list_indexed_artifact_files ~1.7-1.9s p50 (real index has grown past the plan's 7.7MB figure), synthesize_default_artifact_files ~67ms, confirming defect 1 (whole-store re-parse) is the dominant cost. Ratios/warm-cold contrast match the plan's own figures; absolute numbers are host-load-noisy as the plan predicts (this host was mid-epic with dozens of concurrent agents).

Real-terminal verification (sase ace --tmux, tmux send-keys/capture-pane, real ~/.sase data):
- Parent+child spans appeared in ~/.sase/perf/tui_trace.jsonl with plausible durations during live navigation (clan-aggregation selections showed 2-8s cold builds — direct evidence of defect 1's N-agents-share-one-parse problem the epic targets).
- ~/.sase/logs/tui_stalls.jsonl stayed quiet throughout the session (last write predates session start; no new stall/hitch rows appended while spans were emitted).
- Disabled-path overhead confirmed near-zero: isolated microbenchmark with all resolvers stubbed showed ~21us/call with SASE_TUI_TRACE unset vs ~360us/call with it set (JSONL write cost, expected only when opted in).

Verification: just fmt, ruff check, mypy (clean on touched files); tests/ace/tui/widgets/ full suite (3540 passed) plus tests/ace/tui/test_tui_trace.py; just test-scoped (1781 passed). `just check` fails only on the pre-existing (confirmed via git stash on master) symvision gate for a stale sase-kz.5 epic-symbol whitelist, unrelated to this change — filed as PROPOSED FOLLOW-UP on this bead for the epic's land agent to triage.

[2026-08-13T20:01:29Z · sase-l6.1] Verifying publication: trace spans, tests, bench script, and docs for sase-l6.1 (per-lane enrichment telemetry) already implemented and closed; confirming this close published.

## Dependencies

- **Blocks:** [sase-l6.2](sase-l6.2.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-l6.3](sase-l6.3.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-l6.6](sase-l6.6.md) ◐ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-l6.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-l6.1/README.md) | [sase-l6.1](sase-l6.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`15cdba4`](https://github.com/sase-org/sase/commit/15cdba4aa619b0367d50a68c45efbe0761f600d3) | feat(ace): add per-lane trace spans for detail-header enrichment | [sase-l6.1](sase-l6.1.md) | 2026-08-13 16:02:19 EDT |
