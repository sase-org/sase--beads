# Bead: sase-142.4 — Prove it on athena with real node arrivals and close sase-13i.4

[Bead Pages](../README.md) / [sase-142](README.md) / sase-142.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-13i.4.f0.f0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-13i.4.f0.f0.md) · **Assignee:** `sase-142.4` · **Size:** medium
**Created:** 2026-09-20 12:14:23 EDT · **Closed:** 2026-09-20 16:48:49 EDT
**Plan:** [202609/epic\_panel\_new\_node\_flicker.md](https://github.com/sase-org/sase--plans/blob/main/202609/epic_panel_new_node_flicker.md)

## Description

verify-new-nodes-on-athena: soak a landed SHA under the host's real state while deliberately creating nodes that join the @epic tribe, assert the harness invariants from traces and live captures, then close sase-13i.4 with the evidence or record precisely why it still cannot close.

## Notes

[2026-09-20T20:09:14Z · sase-142.4] SOAK SETUP (in progress, bead NOT closed yet). Landed SHA under test: 7442af7afc8be0f547f6337c756cb296fabf833c (== origin/master at 15:56 EDT; contains 2df2137e0f paint log, 686851c9e3 collapsed-panel mode, 7442af7afc row insert + one-frame width). Traced TUI runs in its own tmux session sase142soak (window @124) from a pinned clone ~/.sase/perf/sase-142.4-soak-src (PYTHONPATH=<clone>/src, so a later master fast-forward cannot change the code mid-soak; TUI title v0.17.1+983.g7442af7af), env SASE_TUI_TRACE=1 SASE_TUI_TRACE_PATH=~/.sase/perf/sase-142.4-soak-tui_trace.jsonl, real persisted state (filter NOT machine:apollo, group by status, split @default/@epic/@job, @job collapsed - confirmed on the baseline screenshot ~/.sase/perf/sase-142.4-shots/epic_baseline_pre_arrivals.png). Soak clock started ts=1789934840 (16:07:20 EDT); 30-min mark is ts=1789936640 (16:37:20 EDT). The user interactive TUI (pid 1591739) was not touched. ATTEMPT 1 ABORTED by my own mistake: I launched the first soak TUI without SASE_TUI_SCREENSHOT_DIR and behind a tee pipeline, so the SIGUSR2 that sase screenshot --window sends killed it (default action) at 16:04:46; its 5-min trace is kept as sase-142.4-soak-aborted-first-launch-tui_trace.jsonl and is not evidence. Relaunch uses exec env ... sase tui with SASE_TUI_SCREENSHOT_DIR set and the tmux window option @sase_screenshot_dir set, so sase screenshot --window sase142soak works. ANALYZER: python3 ~/.sase/perf/sase-142.4-analyze.py <trace> [--since TS] [--until TS] [--json OUT] (stdlib only; inlines the CI harness invariant checkers verbatim). NEXT: staggered cheap agents in tribe epic are requested through /sase_run (LaunchApproval); the resumed requester finishes the soak (>=30 min, arrivals observed), captures the after screenshot, runs the analyzer, and closes sase-13i.4 or records why not.

[2026-09-20T20:46:21Z · sase-142.4--1] PROPOSED FOLLOW-UP: display_row_insert is unreachable for real arrivals on athena - 0 attempts in a 38-min soak with 7 @epic arrivals. _try_refresh_agents_display_incremental (_display.py ~300-308) rejects on _by_status_display_membership_changed / diff_touches_workflow_tree before try_insert_rows runs, and sase-run agents with a #git/#gh workflow are AgentType.WORKFLOW families that _is_plain_leaf_row also declines. Decide: admit plain-add / family-parent inserts (gate per panel rather than globally), or restate the criterion as full-rebuild-with-stable-widgets and prove that instead

[2026-09-20T20:46:47Z · sase-142.4--1] PROPOSED FOLLOW-UP: 21 of 50 non-startup full rebuilds hit unchanged panel occupancy with a non-stale_grouping_mode reason (status_membership_change 9, panel_membership_change 7, workflow_tree_change 5; sources mostly inflight_poll/watcher/auto_refresh). stale_grouping_mode is fixed (0), but the plan's 'zero full rebuilds on unchanged occupancy' still fails literally. Investigate the 7 panel_membership_change same-occupancy rebuilds first (diff.duplicate_identity path) and whether status changes inside a bucket need a full rebuild

[2026-09-20T20:47:14Z · sase-142.4--1] PROPOSED FOLLOW-UP: launch-admission time waits never elapse after the coordinator process changes. launch_admission_runtime._resolve_time_wait uses started=waiting_since.get(id, now) but _waiting_since is filled only when the running engine applies a wait action (launch_admission_engine.py:208); a respawned coordinator sees journaled 'waiting' units, never re-applies wait, so now >= now+duration is never true. Evidence: request launch-9f88f3bc-98e0-470e-8579-051d8ea53f6e, %w(time=8m/16m/24m) units 4-6 stayed 'waiting' 29+ min (coordinator pid 3679084 idle in poll sleep; earlier sidecar pid 3670491). Seed waiting_since from the journal's waiting record timestamp

[2026-09-20T20:47:40Z · sase-142.4--1] PROPOSED FOLLOW-UP: soak probe 0od (project home, ace-run 20260920161333) failed 'Failed to prepare workspace' after 'Updating workspace to origin/master...' in home_12 and holds workspace #12 until dismissed in the TUI; probes 0ob/0oc on other workspaces succeeded. Root cause of the home-workspace update failure not investigated (see ~/.sase/workflows/202609/home_ace-run-260920_161333.txt); dismiss 0od in sase tui to release #12

[2026-09-20T20:48:07Z · sase-142.4--1] PROPOSED FOLLOW-UP: a live-arrival soak needs a plain-leaf probe if display_row_insert is to be exercised: probes launched via sase run picked up #git:home and rendered as workflow families (x5 rows), so they can never hit the plain-leaf insert path. Only 2 of 6 requested probes (0ob, 0oc) ran; the 7 @epic arrival frames also include real host agents

[2026-09-20T20:48:49Z · sase-142.4--1] Ran the athena soak on landed SHA 7442af7afc (pinned clone, separate traced TUI in tmux sase142soak, real state, user TUI untouched): 2284s window, 136502 records, 364 paint frames, before/after/end screenshots captured. Proven: 0 stale_grouping_mode fallbacks, 0 panel-count dips, @epic never missing from 52 refresh_panel_widgets spans, harness invariants inv1/2/3/4/6 hold across 20 arrival windows (7 @epic). NOT proven: display_row_insert = 0 successes, 0 attempts; all 7 @epic arrivals were display_full_rebuild (status_membership_change 5, workflow_tree_change 2) because the outer gates in _display.py reject before try_insert_rows runs, and sase-run probes are workflow families. 21 of 50 rebuilds hit unchanged occupancy with non-stale reasons. sase-13i.4 therefore NOT closed; evidence noted on it and 5 PROPOSED FOLLOW-UP notes recorded here (insert unreachable, residual same-occupancy rebuilds, admission time-wait bug that left probes 4-6 unlaunched, probe 0od workspace failure, plain-leaf probe need). Only probes 0ob/0oc ran cleanly.

## Dependencies

- **Depends on:** [sase-142.1](sase-142.1.md) ✓ · ⧖ 2026-09-20
- **Depends on:** [sase-142.2](sase-142.2.md) ✓ · ⧖ 2026-09-20
- **Depends on:** [sase-142.3](sase-142.3.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-142.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-142.4.md) | [sase-142.4](sase-142.4.md) | 0 |
