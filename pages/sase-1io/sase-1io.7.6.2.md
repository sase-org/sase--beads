# Bead: sase-1io.7.6.2 — Fix the dropped Reply-card switch in the Agents deck visual tests

[Bead Pages](../README.md) / [sase-1io.7.6](sase-1io.7.6.md) / sase-1io.7.6.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1io.7.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1io.7.land.md) · **Assignee:** `sase-1io.7.6.2` · **Size:** medium
**Created:** 2026-10-09 14:56:42 EDT · **Closed:** 2026-10-09 16:39:06 EDT
**Plan:** [202610/ship\_v0\_18\_0\_after\_full\_ci\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/ship_v0_18_0_after_full_ci_fixes.md)

## Description

reply-card-race: find and fix why ctrl+j sometimes never switches the Agents deck Main panel to the Reply card under parallel load, and fix any other Full CI-only or Master Gate red on the starting tip.

## Notes

[2026-10-09T20:15:43Z · sase-1io.7.6.2] PROPOSED FOLLOW-UP: Newer-tip Master Gate lint red (symvision private import _reconcile_prompt_with_live_auto_state in src/sase/axe/run_agent_runner_refresh.py, run 37981773957 on commit 6ac3dc734e) is outside this phase tip and belongs to that commit owner

[2026-10-09T20:15:49Z · sase-1io.7.6.2] PROPOSED FOLLOW-UP: tests/ace/tui/visual/_ace_agents_png_snapshot_helpers.py select_main_card still presses ctrl+j in a retry loop; migrate its gate/monitor callers to the single-press show_reply_card helper

[2026-10-09T20:15:55Z · sase-1io.7.6.2] PROPOSED FOLLOW-UP: tests/ace/tui/widgets/decks/test_deck_spread_pilot.py test_main_ctrl_j_in_spread asserts shown in (reply, context); tighten to reply now that the cycle fallback guards the drop

[2026-10-09T20:38:57Z · sase-1io.7.6.2--1] PROPOSED FOLLOW-UP: Full check test-scoped flakes under parallel load — tests/tool/test_inline_escalation.py::test_fast_success_matches_inline (exit 124, 8s soft ceiling timeout on gw8) and tests/tool/test_settlement_retention.py::test_handoff_end_to_end_publishes_one_notification (tool run store busy: database is locked on gw8); both pass in isolation on working tree and clean base (2 passed each), touched=false, unrelated to deck files

[2026-10-09T20:39:06Z · sase-1io.7.6.2--1] Reply-card race fixed and verified: decks unit dir 581 passed, ruff+mypy clean on touched files, both check-red tool tests pass in isolation on working tree and clean base (identical behavior, load-induced flakes: soft-ceiling timeout and sqlite database-is-locked on same gw8 worker, touched=false), all other check stages green (fmt/ruff/mypy/symvision/SASE validation/committed plans), epic-symbols clean

[2026-10-09T20:52:44Z · sase-1io.7.6.3] ship phase sase-1io.7.6.3 fixed the symvision private-import red: reconcile_prompt_with_live_auto_state is now public (was _reconcile_... imported across files since 6ac3dc734e); symvision passes locally

## Dependencies

- **Blocks:** [sase-1io.7.6.3](sase-1io.7.6.3.md) ✓ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1io.7.6.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1io.7.6.2.md) | [sase-1io.7.6.2](sase-1io.7.6.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a36b5c9`](https://github.com/sase-org/sase/commit/a36b5c90ca0322c1ce303dae82beb89681973747) | fix(agents-deck): stop dropping the Reply-card switch under parallel load | [sase-1io.7.6.2](sase-1io.7.6.2.md) | 2026-10-09 16:40:26 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1io.7.6.2--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1io.7.6.2.md

<!-- sase:referenced-by:end -->
