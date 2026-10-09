# Bead: sase-1i5.9.1.2.1.7 — Prove Master Gate and a fresh Full CI on the release tip

[Bead Pages](../README.md) / [sase-1i5.9.1.2.1](sase-1i5.9.1.2.1.md) / sase-1i5.9.1.2.1.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1i5.9.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1i5.9.1.2.md) · **Assignee:** `sase-1i5.9.1.2.1.7` · **Size:** medium
**Created:** 2026-10-08 14:54:15 EDT
**Plan:** [202610/release\_master\_and\_full\_ci.md](https://github.com/sase-org/sase--plans/blob/main/202610/release_master_and_full_ci.md)

## Description

ci-proof: observe the integrated master SHA, repair remaining deterministic CI failures, dispatch and monitor Full CI, and record successful same-SHA run URLs and freshness for the assigned phase's resumed owner.

## Notes

[2026-10-09T01:23:29Z · sase-1i5.9.1.2.1.7] ci-proof progress: tip SHA d0b6e2e9 == origin/master. Master Gate run 37866305965 on tip is queued (backlog: 1 in_progress + 3 queued). Queued Full CI 37864697731 is on older SHA 96dd8ed2, NOT usable as same-SHA proof; fresh Full CI must be dispatched after Master Gate green. Repaired 3 remaining deterministic reds seen on run 37866305965-predecessor 37864302074 (SHA 56db7704): (1) :auto completion description/hint stale vs intentional core-contract change 0ac86ad40c -> updated test_directive_completion_candidates.py to core copy (exact-equality kept); (2) macro-terminology guard: pinned ("tests/test_plugin_commands_mount.py", xprompt) + per-file reason (retired spelling stays reserved; literal from plugin-commands feature b9693bc695); (3) tab-walk race: mount grammar-recheck rebuild + history-load workers reset the open menu mid-walk (proven by instrumented probe; index varied 17/18/23/31) -> pinned spec key in _panel, history_file isolation + history_loaded quiescence in tab test, docstring count unpinned. Already-green-at-tip needing no edit: both -a/--agent metavar help tests (cli-beads fix landed), test_matrix_archived_plan_via_links_panel. Verified: focused 12 tests green, full test_completion_fixes.py 20/20, tab test stable 5x, sase bead epic-symbols clean, ruff fmt fixed. sase tool run check re-run 5f172aa1 in flight when handed to monitor. Uncommitted repairs in workspace await host landing.

[2026-10-09T02:12:26Z · sase-1i5.9.1.2.1.7--1] Joined check 5f172aa1 triage: all 5 NEW + 1 FLAKY pass in isolation sequential (-n0): settlement_retention handoff (db-locked under loadavg~21), global-state-leak snapshot, monitor_supervise idle-timeout, residual-freeze soak, config-pane toast + j/k nav. Load-induced xdist flakes, no code fix; re-run of full check needed on new tip to confirm.

[2026-10-09T02:12:33Z · sase-1i5.9.1.2.1.7--1] PROPOSED FOLLOW-UP: harden 6 load-flaky tests (settlement_retention handoff db-locked retry, global-state-leak snapshot race, monitor_supervise 15s liveness, residual-freeze soak, config-pane toast/j-k nav WaitForScreenTimeout) against high-parallel-load flakes; all green in isolation on base and with repairs.

[2026-10-09T02:12:48Z · sase-1i5.9.1.2.1.7--1] Master moved d0b6e2e9 -> 62f25600 (dev-core-prep, install-only files). Workspace re-tipped to 62f25600 with 4-file repairs intact. Focused 94 green on new tip: terminology guard (new files comply), directive-completion, completion_fixes incl tab-walk, parser-help + verify-cli metavar. Master Gate 37868175381 red with 7: 3 repaired areas + 4 CI-only (metavar x2, codex reaped, shift-tab) that PASS on clean base d0b6e2e9 (stash-proven) -> CI-shard-env-specific, not blocking.

[2026-10-09T02:12:54Z · sase-1i5.9.1.2.1.7--1] PROPOSED FOLLOW-UP: Master Gate CI-shard-only reds (test_memory_help_marks_primary..., test_verify_help_documents_flags showing -a NAME without --agent; test_descendant_processes_are_reaped; test_shift_tab_round_trip) pass on clean base locally but fail in sharded CI on 62f25600 and d0b6e2e9 runs; needs shard-env (py3.12/runner/plugin-set) reproduction.

[2026-10-09T02:35:09Z · sase-1i5.9.1.2.1.7--2] Master moved 62f25600 -> a8bcf227 (models: claude-haiku-5-5, zero overlap with 4 repaired files); workspace re-tipped, repairs intact. Focused 74 green on new tip: terminology guard, directive-completion, completion_fixes, verify-cli, parser-help-helpers. Prior full check 0bba719e passed on 62f25600+repairs. Master Gate 37874328312 on a8bcf227 in_progress; handing its watch to a monitor, Full CI still to dispatch fresh after green.

[2026-10-09T02:44:25Z · sase-1i5.9.1.2.1.7--3] Master Gate 37874328312 on a8bcf227 finished red: 6 failed tests across shards 4/5/6. Triage: (1) 3 are repaired-area failures fixed by the 4-file uncommitted repairs - test_directive_completion_includes_representative_descriptions, test_macro_string_literals_avoid_xprompt_terms, test_tab_through_every_subcommand_reaches_the_last_with_a_highlight - all 3 re-verified green just now on tip+repairs; expected red on base since CI runs without workspace repairs. (2) 2 are known CI-shard-only metavar reds (test_memory_help_marks_primary_command_and_init_alias, test_verify_help_documents_flags) per notes 4-5, base-identical. (3) test_beads_sync_reports_visible_and_missing (PENDING vs MISSING) passes locally 4x including clean-base stash run plus 3x full-file runs - load-flaky, not deterministic. No NEW deterministic in-scope causes; no edits made, no check re-run needed. Master still a8bcf227 (ls-remote confirmed); repairs intact. Gate not green so no Full CI dispatched; bead stays open.

[2026-10-09T02:44:32Z · sase-1i5.9.1.2.1.7--3] PROPOSED FOLLOW-UP: harden tests/ace/tui/test_link_follow_seam.py::test_beads_sync_reports_visible_and_missing against CI-shard load flakes. It returned PENDING instead of MISSING for a missing bead under xdist parallel load on Master Gate 37874328312 (shard 6), but passes serially 4x locally including on clean base; smells like an async snapshot-resolution race similar to the note-3 load flakes.

## Dependencies

- **Depends on:** [sase-1i5.9.1.2.1.1](sase-1i5.9.1.2.1.1.md) ✓ · ⧖ 2026-10-08
- **Depends on:** [sase-1i5.9.1.2.1.2](sase-1i5.9.1.2.1.2.md) ✓ · ⧖ 2026-10-08
- **Depends on:** [sase-1i5.9.1.2.1.3](sase-1i5.9.1.2.1.3.md) ✓ · ⧖ 2026-10-08
- **Depends on:** [sase-1i5.9.1.2.1.4](sase-1i5.9.1.2.1.4.md) ✓ · ⧖ 2026-10-08
- **Depends on:** [sase-1i5.9.1.2.1.5](sase-1i5.9.1.2.1.5.md) ✓ · ⧖ 2026-10-08
- **Depends on:** [sase-1i5.9.1.2.1.6](sase-1i5.9.1.2.1.6.md) ✓ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1i5.9.1.2.1.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1i5.9.1.2.1.7.md) | [sase-1i5.9.1.2.1.7](sase-1i5.9.1.2.1.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ab55fcb`](https://github.com/sase-org/sase/commit/ab55fcb5f3a6baaa98a356a4b61ff8f76dbadcb9) | test(ci-proof): repair completion, terminology, and tab-walk assertions for release tip | [sase-1i5.9.1.2.1.7](sase-1i5.9.1.2.1.7.md) | 2026-10-08 22:46:36 EDT |
