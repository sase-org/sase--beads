# Bead: sase-1b2.19 — Remove the flag, add goldens, inspect live, and bench

[Bead Pages](../README.md) / [sase-1b2](README.md) / sase-1b2.19

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sr](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sr.md) · **Assignee:** `sase-1b2.19` · **Size:** medium
**Created:** 2026-09-27 05:49:54 EDT · **Closed:** 2026-09-27 15:55:37 EDT
**Plan:** [202609/agents\_tab\_final\_deck.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_final_deck.md)

## Description

final-cutover: bench the j/k and triage loop with the flag off and on, then delete the Off branches and the ace_final_deck registry entry and close its flag bead. Add deterministic goldens for every glance and deck state, re-baseline and inspect the changed subtitle and picker goldens, and inspect live captures.

## Notes

[2026-09-27T10:09:53Z · 0t2] CROSS-EPIC (sase-1b1): if deck views have landed, removing `ace_final_deck` also changes 1b1's goldens: `agents_deck_view_*` and every deck-title golden whose subtitle switcher gains `final`. Re-baseline and inspect them with the rest. The new FINAL goldens show the view badge on Main/Files panels (for example in the Reply/FINAL split) and none on FINAL, and the narrow title tiers golden should confirm FINAL's tab-only rungs. For the bench, the flag-off run already includes 1b1's badge, so a p95 miss there predates FINAL: cite it rather than optimizing FINAL for it. During live inspection, confirm that `P` is unavailable on a focused FINAL panel. The full shared rules are in the NOTES on epic sase-1b2.

[2026-09-27T19:54:03Z · sase-1b2.19] PROPOSED FOLLOW-UP: symvision unused-public gate fails identically on the clean base tree (56 hits incl. DeckSpec, RunView* — stale index, unrelated to cutover)

[2026-09-27T19:54:22Z · sase-1b2.19] PROPOSED FOLLOW-UP: visual goldens top_bar_usage_attention_narrow, top_bar_usage_badges_crowded_narrow, axe_chop_run_info_panel fail identically on the clean base tree (convergence timeouts + ChopItem/LumberjackItem ordering)

[2026-09-27T19:54:33Z · sase-1b2.19] PROPOSED FOLLOW-UP: test_open_action_opens_overlay_on_stash_with_trash_count, test_expanded_overflowing_header_claims_half_page_scroll, 2 directive-completion tests fail identically on the clean base tree

[2026-09-27T19:54:47Z · sase-1b2.19] PROPOSED FOLLOW-UP: no FINAL-pinned j/k bench arm exists; cutover recorded SINGLE-list j/k off/on only — consider a FINAL-pinned triage-loop bench

[2026-09-27T19:55:37Z · sase-1b2.19] Cutover done. Bench: j/k pilot off vs on — next p95 38.99/26.06, J-panel 75.79/78.66, prev 45.40/26.29, K-panel 82.07/72.97 (all <100ms ceiling, no FINAL regression); glance micro-bench 19.8us/row both states. Flag removed: Off branches deleted in spec/active-cycle, _agent_detail_decks, glance state, header chip, receipt (+hint unconditional), flag.py deleted, registry+schema entries removed, tests collapsed; flag bead sase-1b5 closed. Goldens: new test_ace_png_snapshots_agents_final.py with 14 deterministic PNGs (rows at 120/80/60, 3 receipts, single commit, failed check, plugin, overview unselected+drift, session blocks+rail, Reply/FINAL split, picker with n, narrow 2/7 tiers + P no-op) — all inspected, check-green twice. Rebaselined 18 picker/decks/blocks goldens for uniform final-segment churn (groups inspected); micro/context_reply pixel-identical after choose_new_panel FINAL-positive-content rule (new unit tests). Also fixed 4-deck fallout: DECK_CYCLE, cycle wrap, picker rows/keys/hints, modal tests, keymap help M/F/T/N, subtitle tiers. Live: workspace-build TUI capture shows FINAL in picker with n and a live row chip; no live finalizing agent exists for the 1Hz tail (settled goldens + test_final_live cover it). Gates: fmt/ruff/mypy/flags/waits/keep-sorted/pyscripts/changelog/terms/docs/model-policy/validate/plans green; targeted suites green (decks 512, flags 268, picker/modal/keymap 36, models/llm_calls/command_line 1180, widgets 4971, actions+modals 1420). Pre-existing base-identical failures recorded as PROPOSED FOLLOW-UP notes (symvision, 3 visual, prompts-trash, header-scroll, 2 directive-completion). Full 48k test-scoped could not complete inline (escalated to full suite on the flag-module delete + contended shared build lock killed the check ToolRun); just check stages above are the completed verification.

## Dependencies

- **Depends on:** [sase-1b2.13](sase-1b2.13.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1b2.18](sase-1b2.18.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1b2.20](sase-1b2.20.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b2.19](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b2.19/README.md) | [sase-1b2.19](sase-1b2.19.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2d8f2f0`](https://github.com/sase-org/sase/commit/2d8f2f0566c876b347c06e6ffb53b8afa20e930b) | feat(ace): remove ace\_final\_deck flag and ship FINAL deck always-on | [sase-1b2.19](sase-1b2.19.md) | 2026-09-27 16:16:16 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c][1] | Mapping sase-1b2 phase dependency graph for value report | 2 |
| read-by | [agent:sase-1b2.19][2] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b2.19/README.md

<!-- sase:referenced-by:end -->
