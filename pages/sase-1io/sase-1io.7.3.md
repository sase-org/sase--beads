# Bead: sase-1io.7.3 — Clear the Full CI-only failures

[Bead Pages](../README.md) / [sase-1io.7](sase-1io.7.md) / sase-1io.7.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1io.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1io.land.md) · **Assignee:** `sase-1io.7.3` · **Size:** medium
**Created:** 2026-10-09 06:48:49 EDT · **Closed:** 2026-10-09 08:58:34 EDT
**Plan:** [202610/finish\_release\_v0\_18\_0.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_release_v0_18_0.md)

## Description

full-ci-fixes: triage and regenerate or repair the drifted PNG goldens that keep the visual-test lane red, and fix any other Full CI-only red on the tip.

## Notes

[2026-10-09T11:07:23Z · sase-1io.7.3] Full CI triage (run 37909515949 at e2efd56242): visual-test 27 drifted PNGs (11 agents_final_* ~0.006-0.018%, 3 agents_retry_e2e_* 0.07-0.17%, 3 agents_waiting_epic_follow_* 116px each, jump_panel_expanded 0.59%, renamed_generic_session_root 0.25%, artifacts_beads_idle_query, custom_gate_task_triage 7.6%, mini_macro_location_flow_finder 6.0%, model_picker_usage_hints, 2 models_panel_alias_picker_reordered, range_dark, timeband_past_light 1.8%). Test legs: tint test failed on OLD assertion pre-6c783599c1 (fixed at tip; hatch verified against Textual 8.0.1 source, Color.ansi preserved; Master Gate tip run 37917980867 all 8 shards green incl. this test on py3.12/8.0.1); prompt_key_perf is KNOWN sase-gate-fixes scope; tail-ghost is known flake sase-1ib, not reproducible locally (serial + 5x -n4 + 1x -n7 all green). Lint toobig fixed at tip (test_run_dev.py 92 lines). Master Gate lint Symvision residual is KNOWN sase-gate-fixes scope (tip run 37917980867 lint red only on _lint-symvision:328). Local full visual pass at tip: 1291 passed, 2 convergence timeouts (arrival_dot, fixed_page_cards Reply-card waits) both green on retry -> load flakes, not regressions. Regenerating goldens at tip via monitored just fix-tui-screenshots next.

[2026-10-09T11:07:42Z · sase-1io.7.3] PROPOSED FOLLOW-UP: tail-ghost flake test_typing_space_inside_parens_shows_tail_ghost failed again on Full CI 3.13 leg (run 37909515949, same [^T] word signature as sase-1ib); 6/6 local reruns green (serial, -n7, 5x -n4) so no local repro — needs sase-1ib owner attention, not a phase fix

[2026-10-09T11:34:51Z · sase-1io.7.3--1] Golden inspection (run 65e8fe13, 6 updated / 1021 unchanged / 0 created / 0 stale): all 6 PNG pixels opened and approved — custom_gate_task_triage 114714 material px (~7.6pct, task-text content drift as triaged), renamed_generic_session_root 3746px (~0.25pct, timestamps; Reply cards AGENT REPLY/AGENT(0)/AGENT(code) present), tab_strip_stale_host 120px, model_picker_usage_hints 79px, models_panel_alias_picker_reordered 71px + narrow 76px — all tiny, coherent, no missing UI. Capture flakes test_agents_deck_blocks_paged_newest/older (Reply-card 15s timeouts) both green on serial retry; arrival_dot/fixed_page_cards passed first try. Full just test-visual --check routed to verify monitor (exceeds inline ceiling); close bead only after it is green.

[2026-10-09T12:16:35Z · sase-1io.7.3--2] Visual --check triage: 1293 passed, 3 drifted (all pixel-inspected, no missing UI). timeband_past_light pinned-now deterministic header shift (~27k px) and jump_panel_expanded SASE CONTEXT header addition (~8.9k px) are intentional code drifts approved for regen; renamed_generic_session_root 1/2-vs-2/2 Reply pager-index race is capture nondeterminism (serial lands 1/2, parallel flaked to 2/2 once) - do NOT chase by regenerating, follow-up if it recurs. arrival_dot 15s Reply timeout flake green on serial retry (9.95s pass). Scoped regen of the 2 deterministic goldens plus full --check routed to monitor (rust setup rebuild slow under load).

[2026-10-09T12:58:18Z · sase-1io.7.3--3] PROPOSED FOLLOW-UP: Agents deck Reply-card 15s waits flake under parallel load (test_agents_deck_view_split_narrow, test_agents_deck_blocks_arrival_dot failed 2x full --check, all green on serial retry 9-13s); consider longer wait or reduced contention for Reply waits

[2026-10-09T12:58:34Z · sase-1io.7.3--3] Full visual lane triaged at tip: scoped regen applied only timeband_past_light_120x40 (pinned-now header shift, pixels approved); jump_panel_expanded_two_sections byte-identical, no update needed. 7 regenerated goldens left uncommitted for host finalizer. Two full --check runs: 1291 passed, 1 skipped, 0 golden mismatches; only failures are known Reply-card 15s load flakes (split_narrow, arrival_dot), both green on serial retry (13.0s, 9.17s). epic-symbols none. Prior triage stands: tint/toobig fixed at tip, tail-ghost and Symvision lint out of scope, Reply flake filed as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-1io.7.5](sase-1io.7.5.md) ◐ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1io.7.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1io.7.3.md) | [sase-1io.7.3](sase-1io.7.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`aced694`](https://github.com/sase-org/sase/commit/aced694adcf7c9b97e64938e7ec34cb0d27bb254) | test(visual): regenerate golden snapshots for timeband and ACE panels | [sase-1io.7.3](sase-1io.7.3.md) | 2026-10-09 09:01:10 EDT |
