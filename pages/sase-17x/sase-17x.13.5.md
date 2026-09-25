# Bead: sase-17x.13.5 — Popup, provider-footer and cache correctness

[Bead Pages](../README.md) / [sase-17x.13](sase-17x.13.md) / sase-17x.13.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17x.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17x.land.md) · **Assignee:** `sase-17x.13.5` · **Size:** medium
**Created:** 2026-09-24 20:28:46 EDT · **Closed:** 2026-09-25 00:13:36 EDT
**Plan:** [202609/command\_line\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_landing_fixes.md)

## Description

completion-fixes: make every candidate reachable through a scrolling popup window and fix the highlight echo guard. Scope and clear the provider footer. Honor per-kind TTLs and invalidate on finish. Recheck the cursor on async results. Fix the hint and heading text.

## Notes

[2026-09-25T04:12:17Z · sase-17x.13.5] PROPOSED FOLLOW-UP: goldens-perf should regenerate every command_line_* golden, not only the two updated here — since worker-hops landed, the grammar-ready refresh renders the empty-state popup (FOR <selection> rows, "63 commands" hint) whenever a visual test opens the panel, so block_selected/declined/denied/doc_peek/earlier_divider/error/foreground/help/running (and the empty/success/submit_failed/typed_ghost/block_expanded ones that timed out here) drift from HEAD. doc_peek also seeds the popup widget directly and now captures a stale "recent · 5 of 5" footer; it should seed via screen._render_popup.

[2026-09-25T04:12:28Z · sase-17x.13.5] PROPOSED FOLLOW-UP: visual command_line tests are load-flaky — _open_panel waits on the real grammar loader (spec subprocess build) and wait_for_visual_idle times out at 30s when the host load is ~35 (block_expanded failed on every attempt, also on the clean base). Pre-seeding an in-process CommandLineGrammar (build_spec + from_spec_json) in the visual _open_panel would remove the subprocess dependency.

[2026-09-25T04:12:37Z · sase-17x.13.5] PROPOSED FOLLOW-UP: tui_perf.md rule 12 (guard flag cleared synchronously in finally) does not work for OptionList: OptionHighlighted is posted and handled after the flag is cleared, so the guard never fires. CommandLinePopup now counts pending echoes per window row and drops messages whose Option is not in the current list; the rule should say so (memory note change, needs the sase_memory_write path).

[2026-09-25T04:12:47Z · sase-17x.13.5] PROPOSED FOLLOW-UP: provider candidates_for has a disk cache (5s TTL for pending_plan, mtime-keyed) that is not invalidated when a command-line block finishes; plan approve X then plan approve <Tab> within the TTL can still offer X even though the screen ProviderCache is invalidated. A bypass/invalidate hook in sase.completion.candidates.cache would close it.

[2026-09-25T04:12:57Z · sase-17x.13.5] PROPOSED FOLLOW-UP: clean-base check failures unrelated to this phase — (1) just _lint-mypy: tools/sase_core_wheel_cache:433 arg-type and :604 var-annotated; (2) just _lint-symvision: 4 unnecessary --epic-symbol sase-18i(DirectApprovalOutcome/DirectApprovalRequest/execute_direct_approval/resolve_direct_approval) entries in the Justfile plus unused CoderPlacement/PlanGateHistory/RetiredGate/normalize_agent_session_query_expr/render_approve_success; (3) tests/test_sase_core_wheel_cache_tool.py:490 fixed-sleep-missing-pragma; (4) 34 test failures identical on the clean base in tests/completion/test_snapshot.py, test_build.py (19 == 18 mutex groups), test_kind_coverage.py, tests/test_query_profile_agents.py, artifacts_contract/test_query_conformance.py, the kill-and-edit/family-relaunch/force-reuse/directives_bead files (agent-session dialect change 3a1d0bab2).

[2026-09-25T04:13:36Z · sase-17x.13.5] Completion-fixes done. Popup renders a scrolling 8-candidate window (headings extra) keeping CompletionPopupState.index and the OptionList highlight in agreement; footer shows the true N of M and one key hint (⇥ complete idle / ⏎ accept in menu). Echo guard replaced by per-row pending-echo counts + option-identity check (the old synchronous flag never fired). Provider footer is derived from the slot's own cache entry (failed => '⚠ <kind> unavailable', empty => 'no <kind>', scoped/cleared on slot change; footer alone shows when no rows). ProviderCache honors VOLATILE_KIND_TTL_SECONDS and is invalidated on block finish (exits.py -> screen.invalidate_provider_cache). _provider_fetch_task rechecks line AND cursor after the await. Idle hint counts top-level commands (63, singular-safe), empty state has RECENT / FOR <sel> · selected <kind> heading rows. Also fixed a real bug found while writing pilot tests: CommandLineInput did not stop/prevent_default a key its popup handler consumed, so Enter with an active menu accepted AND submitted (and Esc in the menu also hid the panel) - now consumed. Verified: 151 tests in tests/ace/tui/command_line pass (new test_completion_fixes.py: 22 pilot/unit tests incl. Tab through all 30 'bead ' subcommands, echo guard, footer scoping, TTL, invalidation, cursor/line-change drop, Enter/Esc); ruff/fmt/keep-sorted/mypy(src) clean; symvision flags none of my symbols; no epic-symbols for this phase; goldens command_line_empty_state and command_line_history_search regenerated and inspected (stable on re-run). Live-render check: throwaway pilot->PNG of 'bead ' + 14 Tabs showed the 8-row window scrolled to 'subcommand · 14 of 30 · fuzzy ⏎ accept' with the highlight visible. Not verified/left alone: other command_line goldens drift from HEAD (grammar-ready empty-state popup) and several visual tests time out under host load ~35 (also on clean base) - recorded as follow-ups for goldens-perf. Full 'sase tool run check' stops at pre-existing clean-base failures (mypy tools/sase_core_wheel_cache, symvision sase-18i epic-symbol entries, test-waits in test_sase_core_wheel_cache_tool.py); just test-scoped ran 47k tests with 35 failures, 34 identical on clean base + 1 load flake that passes on rerun - none in command_line code.

## Dependencies

- **Depends on:** [sase-17x.13.3](sase-17x.13.3.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17x.13.6](sase-17x.13.6.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17x.13.8](sase-17x.13.8.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.13.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.13.5/README.md) | [sase-17x.13.5](sase-17x.13.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`61f88cc`](https://github.com/sase-org/sase/commit/61f88ccd695509b23b5547d9c9901641746fb005) | fix(command-line): scroll popup window, scope provider footer, honor cache TTLs | [sase-17x.13.5](sase-17x.13.5.md) | 2026-09-25 00:14:32 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17x.13.5][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.13.5/README.md

<!-- sase:referenced-by:end -->
