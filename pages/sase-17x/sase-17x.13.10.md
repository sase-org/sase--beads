# Bead: sase-17x.13.10 — Close the \`:\` Command Line landing gaps: hide/hop deadlocks, key and source bugs, stale goldens

[Bead Pages](../README.md) / [sase-17x.13](sase-17x.13.md) / sase-17x.13.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17x.13.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17x.13.land.md) · **Assignee:** `sase-17x.13.10.land`
**Created:** 2026-09-25 08:41:39 EDT · **Closed:** 2026-09-25 21:09:18 EDT
**Plan:** [202609/command\_line\_landing\_gaps.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_landing_gaps.md)

## Description

The `:` Command Line from epics sase-17x and sase-17x.13 hides, hops, and reopens without wedging the app. Every configurable key routes through `ace.keymaps.command_line`. Completion sources return fresh, complete candidates. No state mutation or disk write runs on the wrong thread. `just lint` passes the line-count gate. Every golden this epic changed is regenerated and inspected, and a live walkthrough succeeds end to end, including a screenshot export after hide and reopen.

## Notes

[2026-09-25T13:53:07Z · sase-17m.5.1.6.land] DISCOVERED ISSUE: proposed by sase-17m.5.1.6.2 note #2. Its agents_decks_single_empty, agents_onboarding, and agents_onboarding_no_plugins PNG goldens drift with the 'Command Line: run sase commands without leaving the TUI.' tip, unrelated to the agent-session rename. Your golden phase already owns five onboarding goldens; include these three in that review and accept only explained diffs.

[2026-09-26T01:09:18Z · sase-17x.13.10.land] Landed by sase-17x.13.10.land at master 7cb835953 plus the landing diff below.

STEP 1 - VERIFY (every phase checked against its commit and the code at HEAD):
- .1 split-completion (f51cb300b): screen_completion.py is 697 lines (was 1039), split into cd_completion, completion_probe, and screen_completion_keys; toobig no longer flags it.
- .2 hide-hop-deadlocks (6d9d1b5a0): Esc on an empty line goes through keymaps.hide_panel -> action_hide_panel with no await. hop_to_palette stores the draft, dismisses without awaiting, and call_later opens the palette. _on_key's only await is super()._on_key (AST-asserted). Procs focus is delivered directly. Pending grammar on_ready callbacks are kept in a list, and stale screens no-op.
- .3 key-routing (e01d34651): menu moves on fixed up/down/ctrl-n/ctrl-p/Tab keys, the menu hint reads "esc leave", and hints use compact esc/^R. GAP FOUND AND FIXED: the plan's second history example (same prefix, first up-arrow after an edit skips the newest entry) still failed; reproduced with a real-press pilot. history_step now resets the history cursor whenever a new walk anchor starts; the real-press test covers it and fails without the fix.
- .4 completion-sources (136a3e948): candidates_for(use_disk_cache=False), generation bump plus in-flight task cancel, cd +label/+home via ProjectDisplaySnapshot off-thread, project slots merge the provider, cd - offered last, dotfiles listed on a leading '.', probe stamped at key receipt with a strong task reference.
- .5 ui-thread-state (ea25ee2bf): tip marker written via to_thread; read_proc_for_block runs off-thread and append_proc_block on the UI thread; note_exit no longer double-counts history.
- .6 goldens-walkthrough (9518b31df, committed by hand during the Codex outage, no close note): the doc-peek fixture types 'bead cl' and renders via _render_popup; the history-refresh patch is removed; the never-awaits test covers _render_popup and _render_signature. 23 goldens were regenerated (22 planned plus indexing); agents_decks_single_empty (the note-#1 request) is current at HEAD. Its full test-visual monitor timed out at 30 min and sase-18o/sase-16a were left open, so the land agent finished those items:
  * Full just test-visual (6 min): 1040 passed and 2 failed. Both failures are the sase-18n narrow top-bar timeouts (out of scope).
  * Drift in the rerun without those two nodes: command_line_empty_state was nondeterministic (RECENT rows tied on one last_used second; stamped in host time, not the configured zone). FIXED: the test stamps with datetime.now(get_timezone()) and re-sorts; the golden now reads '2h ago'/'1d ago' newest-first.
  * 12 command_line goldens were racy on the one-time palette tip, which the off-thread marker worker delivers after the test's last render (command_line_success flipped in 1 of 2 runs). FIXED: the visual _open_panel pins palette_tip_show=False. The 12 were regenerated; the pixel diff is limited to the hint row (y 971-993). Then 3/3 consecutive check runs were clean (18 unchanged), and a final full run showed no command_line drift.
  * Unrelated drift routed: agents_fleet_loaded_zero_results/unavailable (ce1336eec deck picker hint) and agents_decks_context_reply_no_files (59bf17d53, sase-17d.12.2) -> new sase-19z; config_center agent-CLI/plugin list drift (5 nodes, varies per run) -> +1 and note on sase-194; agents_auto_approve_workflow_child_alignment 'main 0/1' spread-count flake -> new sase-1a3.
  * Live walkthrough (checkout build, sase screenshot --keep plus tmux): ran bead show sase-17x.13.10 (exit 0); Esc hid the panel, ':' reopened it, and the screenshot export after reopen SUCCEEDED; ';' opened the Command Palette (tmux needs '\;'); the palette ':' hop returned with the kept draft 'bead list --status open'; 'p' on a block opened Admin Center Procs focused on that proc; up/down walked 'bead' history newest-first; 'v' on a running 'tool wait' block opened the pager. It exposed two defects:
    - FIXED (sase-17x family, db99493): live blocks rendered elapsed as an epoch timestamp ('exit 0 · 1790073091.2s') because started_at used time.monotonic while finished_at uses time.time. started_at and elapsed_seconds now use wall time; a new test fails without the fix.
    - ROUTED: 'bead show <Tab>' shows 'no bead' outside agent shells. catalog_sdd._resolve_beads_dir only knows the legacy sdd/beads layout and ignores project. Predates this epic; also breaks shell completion -> new sase-19y (bug, medium).
  * sase-18o closed with the regenerated golden names. sase-16a: its help drift is gone at HEAD, closed. sase-19j (same host-vs-configured-zone stamp bug in test_completion_extras, from fad9b5d03) fixed here and closed.

STEP 2 - INTEGRATE: reviewed every non-epic commit since 08:41. No new awaited dismiss()/pop_screen() in src/sase/ace/tui. action_open_command_palette moved to actions/_base_commands.py (b7c80be91) with its name unchanged, so the hop still resolves. The new tool_failures_* completion kinds are free-text value hints with no provider. The deck-picker 'p' keymap is Agents-scope only and does not collide with block_procs. No integration changes needed.

VERIFICATION: just fix clean. sase tool run check: all lint gates green (ruff, mypy, symvision, flags, terminology). SASE validation failed only on master drift from 49c32e19e (sase-18j.9 did not regenerate sase/memory/README.md). The escalated full lane: 47647 passed, 5 failed, none in touched files: 2 deterministic on clean HEAD (memory README drift; the marker path audit on node_finder_preview_loader from sase-19i.3) and 3 that passed on rerun. tests/ace/tui/command_line: 230 passed. test_completion_extras passes under TZ=UTC and TZ=America/Los_Angeles.

FOLLOW-UP DISPOSITION:
- .3 #1 (agent prompts validate artifact-missing): DECLINED, resolved on master; 'agent prompts validate' reports ok (sase-196.1 / 4214ccc65).
- .4 #1 (5 tests fail after a core rebuild): DECLINED, resolved by dbc94a00b; all 74 tests in those files pass.
- .4 #2 (load flakes): new sase-1a1 (test_run_ace_app_does_not_join_default_executor_worker) and sase-1a2 (test_reverse_range_cycles_backward_wraps_and_reenters_from_custom).
- .5 #1 (flakes): dispatch hello -> +1 sase-13h; pager y-then-label -> +1 sase-z1; the palette-tip off-loop timing flake was already fixed by .4's test_policy_io race fix (DECLINED).
- Land-run discoveries: memory README drift and the toobig violation in tool/executor.py (1113 lines) -> DISCOVERED ISSUE note on sase-18j.10 (the triage 'unknown field failures' wire mismatch is already recorded on sase-18j). The marker-audit failure -> DISCOVERED ISSUE note on sase-19i. The test_monitor_result bounded-wait flakes -> new sase-1a0. test_monitor_supervise_timeout -> +1 sase-lk.
- Observation not filed: up-arrow on an EMPTY line is a no-op because prefix_matches returns [] for an empty prefix. That matches the spec ('filtered by the typed prefix'), and the RECENT popup plus Tab covers recall.
- Epic symbols: none keyed to sase-17x.13.10.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.13.10.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.13.10.land/README.md) | [sase-17x.13.10](sase-17x.13.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`31ba8e4`](https://github.com/sase-org/sase/commit/31ba8e4ddba4f34996c0cde4228435f0b8acb57a) | fix(command-line): land sase-17x.13.10 gaps: history reset, wall-clock elapsed, deterministic goldens | [sase-17x.13.10](sase-17x.13.10.md) | 2026-09-25 21:20:48 EDT |
