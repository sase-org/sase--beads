# Bead: sase-l6.6 — Land the epic

[Bead Pages](../README.md) / [sase-l6](README.md) / sase-l6.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zw](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zw.md) · **Assignee:** `sase-l6.6` · **Size:** small
**Created:** 2026-08-13 15:25:20 EDT · **Closed:** 2026-08-14 08:01:09 EDT
**Plan:** [202608/sase\_context\_incremental.md](https://github.com/sase-org/sase--plans/blob/main/202608/sase_context_incremental.md)

## Description

land: re-measure the full budget against the trace phase baseline in a real terminal, file the named follow-ups with /sase_new_task, and close the epic with an honest reading of what each phase bought.

## Notes

[2026-08-14T12:01:09Z · sase-l6.6] Re-measured the full budget in a real terminal on athena, workspace sase_11, master HEAD 2b64c5582 (all 5 implementation phases landed), against the same recipe phase `trace` established (tests/perf/bench_detail_header_summary.py --include-home, driving the production tui_trace spans; docs/perf_runbook.md).

PER-RESOLVER COLD/WARM (ms), home_real, 20 non-clan agents, baseline (2026-08-13, sase-l6.1, trace-only) vs after (2026-08-14, all 5 phases):

  resolver              cold_p50  before->after   cold_max  before->after   warm_p50  before->after
  skill_uses              203.2 -> 4.8               232.2 -> 13.3            6.3 -> 8.9
  memory_reads               7.5 -> 7.5              152.6 -> 114.1         145.9 -> 5.8
  artifact_file_paths       92.1 -> 3.4              793.8 -> 81.7           90.5 -> 3.2
  plan_enrichment             0.2 -> 0.1              171.7 -> 1.4             0.2 -> 0.1
  slow_tool_sources           0.2 -> 1.9              123.3 -> 100.8          24.3 -> 1.9
  wait_bead_statuses           0.0 -> 0.0              956.9 -> 0.0             0.0 -> 0.0
  (delta_entries/opened_workspaces/xprompts/linked_delta/bead_display: ~0 both times)

artifact_file_paths breakdown (where the time inside it goes): list_indexed_artifact_files p50 dropped from ~1.7-1.9s (sase-l6.1's own baseline note; the real index had grown past the plan's 7.7MB figure) to 8.5ms in a clean re-run today -- a ~200x reduction, and it is now identical cold vs warm, confirming defect 1 (the one resolver with literally no cache) is fixed. synthesize_default_artifact_files (never touched by this epic, always uncached, does its own done.json/agent_meta.json/plan_path.json reads) measured noisily across runs (6.5ms p50 in a clean 10-agent/3-run pass vs an 80ms outlier in a busier sample taken while this host had a concurrent Rust release build and several other agents running) -- consistent with the load-noise caveat sase-l6.1 already recorded for this host, not a regression.

One new finding outside the epic's three named stores: agent_page_url measured 400-800ms cold AND warm whenever the 20-agent sample includes a page-publishing 'Done' agent (0.0ms in the original baseline only because no such agent was sampled that day). Root-caused and filed as sase-lw (see below) -- an uncached per-call registry snapshot, not something any of sase-l6's five phases touched or introduced.

REAL-TERMINAL VERIFICATION (sase ace --tmux, tmux send-keys/capture-pane, live ~/.sase data, ~46 agents / 3 running):

- First paint: SASE CONTEXT (with whatever lane is free/cached) was present in the very first captured frame after a selection change (~50ms poll), consistent with phase `immediate`'s zero-I/O synchronous cheap-path render -- no separate worker round trip observed for that content.
- Complete section: batch timings read from the live trace confirm phase `stream`'s cheapest-first, coalesced-publish behavior (this land pass's own capture: first-ever cold selection in the process published 3 batches totaling ~98ms; already-warm-in-process selections settled between <1ms and ~40ms per batch). This land pass's own tmux-driven navigation did not cleanly isolate one-key-per-agent transitions to get a clean per-key p50/p95 (the cursor stayed on one clan/tribe container across several key presses), so for the authoritative batch-latency figures I'm relying on phase sase-l6.4's own real-terminal capture, recorded in its close note: batch 1 (free/in-memory lanes) ~0.2-0.7ms, batch 2 (store-backed lanes) 12-41ms warm / 300ms-1.2s cold. That is the honest per-batch number; this land pass corroborates the *shape* (fast free batch, slower store-backed batch) but not independently a tighter number.
- Steady-state enrichment CPU, one stationary selection, 60s real time: build_detail_header_summary parent spans totaled 47 calls / 445ms of duration across the 60s window (0.74% of the window), and only 1 of the 9 possible lanes (bead_display) actually re-resolved on the stationary selection -- the other 8 stayed cached, confirming defect 3 (the old blanket 1s TTL that re-ran all twelve resolvers every repaint) is gone; this is revalidation of one lane, not full recomputation. tui_stalls.jsonl gained 0 new entries during the window. Total process CPU over the same 60s was ~81% of one core (utime+stime), but tracing shows that is dominated by ace.provider_snapshot (456 calls) and widget.agent_list.patch_agent_row (378 calls) -- live agent-list churn from this host's 3 concurrently-running agents with ticking elapsed timers, unrelated to SASE CONTEXT enrichment and out of this epic's scope. Reporting both numbers because the plan asked for "steady-state enrichment CPU" specifically and the raw process-CPU number alone would overstate what this epic controls.

TARGET CHECK: "context content on the first paint" -- met (zero-I/O immediate paint, phase l6.5). "a complete section within roughly 100ms warm" -- met for warm-in-process selections (mostly <40ms per this pass and phase l6.4's own capture); a genuinely cold first selection can still take several hundred ms to ~1.2s on the store-backed batch per sase-l6.4's own cold figures, which is expected (a cold-cache first touch was never the target) and is exactly what follow-up sase-lu proposes to characterize properly since none of this epic's numbers, including these, are cold-OS-page-cache measurements. "steady-state enrichment work that is revalidation rather than recomputation" -- met (see above).

WHICH DEFECTS EACH PHASE ACTUALLY REMOVED (honest read):
1. Three whole-store parses repeated per agent -- REMOVED by sase-l6.2 (stores). artifact_file_paths cold p50 92ms->3.4ms, and critically stopped scaling with agent count (process-wide snapshot cache, not per-agent).
2. All-or-nothing rendering -- REMOVED by sase-l6.3 (lanes, structural) + sase-l6.4 (stream, user-visible). Section now renders partial lanes cheapest-first with a pending affordance instead of waiting on all twelve resolvers.
3. 1s blanket TTL re-running all resolvers every repaint -- REMOVED by sase-l6.3's per-lane freshness policy. This land pass's own 60s stationary-selection trace is direct confirmation: 1 of 9 lanes revalidates, not 9.
4. Nothing survives the panel (show_empty clears everything) -- NOT ADDRESSED (was explicitly deferred to a follow-up in the original plan). Filed as sase-lt.

FOLLOW-UP OUTCOMES (all via /sase_new_task from this land phase):
- sase-lr (new, size large): prune/rotate the three append-only stores. RELATED note added to sase-kh (a same-theme but different-file prune task from epic sase-k3).
- sase-ls (new, size large): move the artifact-file index into sase-core's Rust indexed storage. RELATED notes added to sase-lr and sase-kh.
- sase-lt (new, size medium): scope show_empty()'s cache clear to the deselected agent instead of wiping every agent's resolved lanes.
- sase-lu (new, size medium): measure cold-cache enrichment cost; every figure this epic has (including this land pass's) is warm-page-cache only. RELATED note added to sase-kj (same gap, epic sase-k3).
- sase-lv (new, size medium): audit non-TUI callers of read_artifact_file_index (artifact_cli/prune.py, axe/run_agent_exec_finalize_artifacts.py, artifact_file_reclaim.py) for their own call patterns now that a cache exists to lean on.
- sase-lw (new, size medium; not plan-named, discovered during this land pass's re-measurement): resolve_agent_page_url has no cache and re-scans the whole agent-name registry on every call, 400-800ms whenever the selected agent publishes a page. RELATED to closed sase-c7, which fixed the same get_reserved_family_names()-uncached problem for a different call site (bulk bead-page-association publication) that does not cover this one.
- sase-le (+1 corroborated, not new): phase sase-l6.4's order-dependent test_prompt_panel_header.py flake is an exact duplicate of an already-open task; added independent reproduction evidence.
- sase-lm (+1 corroborated, not new): phase sase-l6.5's 'TaskSubmitError: task wire schema mismatch' (63 failures) is an exact duplicate of an already-open task (sase-core-rs floor lag); added independent reproduction evidence. Not currently reproducing in this workspace (just check passed clean here today), consistent with that task's own finding that it depends on which sase-core-rs build is linked.
- sase-l6.1's stale --epic-symbol whitelist report (bead sase-kz.5, Snippet* symbols) and sase-l6.2/l6.3's symvision unused-public-function report (stream_and_parse_messages_json_output) -- both CONFIRMED ALREADY RESOLVED on current master: grep of Justfile's _lint-symvision recipe shows zero --epic-symbol entries today, and this land pass's own `just check` run passed lint (symvision) clean. No new task needed for either.

VERIFICATION: `just check` (scoped) green today at HEAD 2b64c5582 -- fmt, ruff, mypy, pyscripts, test-waits, changelog, terminology, symvision, toobig, SASE validation, committed-plans, and the scoped test lane all passed with no failures. Did not re-run the full `just check-full` (28k+ tests) myself since this land phase made no code changes and every implementation phase (sase-l6.1 through sase-l6.5) already recorded its own full-suite verification with only the now-triaged pre-existing issues above; today's clean scoped `just check` on the fully-landed tree, well after all five phases merged, is consistent with nothing having regressed since.

## Dependencies

- **Depends on:** [sase-l6.1](sase-l6.1.md) ✓ · ⧖ 2026-08-13
- **Depends on:** [sase-l6.2](sase-l6.2.md) ✓ · ⧖ 2026-08-13
- **Depends on:** [sase-l6.3](sase-l6.3.md) ✓ · ⧖ 2026-08-13
- **Depends on:** [sase-l6.4](sase-l6.4.md) ✓ · ⧖ 2026-08-13
- **Depends on:** [sase-l6.5](sase-l6.5.md) ✓ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-l6.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-l6.6/README.md) | [sase-l6.6](sase-l6.6.md) | 0 |
