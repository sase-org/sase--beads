# Bead: sase-1lh.2 — Fix the deterministic visual-test failures

[Bead Pages](../README.md) / [sase-1lh](README.md) / sase-1lh.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.10q](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.10q.md) · **Assignee:** `sase-1lh.2` · **Size:** medium
**Created:** 2026-10-16 13:00:19 EDT · **Closed:** 2026-10-16 14:27:26 EDT
**Plan:** [202610/v0\_18\_0\_green\_ci\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_0_green_ci_release.md)

## Description

visual-drift: repair the two goldens that fail on every run and the CI-only agents-deck readiness timeouts.

## Notes

[2026-10-16T18:17:08Z · sase-1lh.2] Visual failure classification from the 10 newest Full CI visual-test jobs (runs 38906709061, 38903716043, 38889630938, 38865993057, 38864749608, 38853338778, 38842775619, 38829475896, 38824095334, 38809974453), plus local reproduction:
- DETERMINISTIC golden drift: help_guide_axe_120x40 (220px; intended text change in axe_onboarding.py via 8676f92f2f) and agents_lane_neighbors_above_context_160x50 (1709px; intended NEIGHBORS divider removal via d5efed6535). Both fail every run that reaches comparison, locally and in CI (newest run 38906709061 shows exactly these two). Fixed by regenerating both goldens after inspecting actuals.
- DETERMINISTIC-AT-HEAD golden drift (newer than newest CI run): agents_llm_calls_panel_populated_120x40 (6057px; fixture path docs/llms.md -> docs/reference/providers/models.md via e297cefb8e, llms.md is now a move-stub). Reproduced locally, golden regenerated.
- INTERMITTENT readiness timeout: test_renamed_generic_agent_session_root_png_snapshot fails 7 of the 10 runs with Timed out waiting for Main view visibly applies the selected reply card (diagnostics always main_active=context/view_active=reply/pending=None/scroll_y=0). test_agents_session_lane_neighbors_png_snapshot shares the same helper and wait. Root cause: post-landing Main re-delivery clamps scroll to 0, scroll watcher derives Context and permanently overwrites stored selection; old wait could never recover. Fixed in tests/ace/tui/visual/_ace_agents_png_snapshot_helpers.py (semantic wait + bounded re-drive, same 15s budget) with regression test tests/ace/tui/test_main_deck_reply_steal_recovery.py (fails on old helper with CI-identical diagnostics, passes on new).
- OLDER-SHA drift sets (node_finder*, agents_clan_panel_swarm*, agents_archive_help_120x40, artifacts_split_selected_*, artifacts_plans_filter_bar_prefilled_120x40 in runs 38829475896/38824095334): not present at HEAD; resolved by commits already on master. No action.

[2026-10-16T18:26:45Z · sase-1lh.2] PROPOSED FOLLOW-UP: just _lint-pyscripts Rule 1 fails identically on clean base (site/reference/automation/tools/index.html unreferenced; docs-epic fallout)

[2026-10-16T18:26:51Z · sase-1lh.2] PROPOSED FOLLOW-UP: zsh completion PTY smoke (test_alias_sbd_completes_static_bead_tree) timed out once at 5s under host load1~40+, passes unloaded; consider evidentiary retry or load-aware budget

[2026-10-16T18:26:58Z · sase-1lh.2] PROPOSED FOLLOW-UP: consider a parked-reader guard so a same-subject Main re-delivery cannot move the spread scroll/selection while the user reads Reply (this phase only hardened the test readiness wait; app behavior unchanged)

[2026-10-16T18:27:26Z · sase-1lh.2] visual-drift done. Goldens: regenerated agents_lane_neighbors_above_context_160x50 (intended d5efed6535 divider scoping), help_guide_axe_120x40 (intended 8676f92f2f text), agents_llm_calls_panel_populated_120x40 (intended e297cefb8e fixture path); targeted --check clean twice incl TZ=UTC. Readiness: root-caused the reply-card timeout (post-landing re-delivery clamps scroll, watcher overwrites stored selection; old wait unrecoverable) and hardened select_navigable_main_card/show_reply_card with a semantic wait + bounded re-drive (15s budget unchanged); new tests/ace/tui/test_main_deck_reply_steal_recovery.py fails on old helper with CI-identical diagnostics and passes on new; pressured slice green. sase tool run check: all lint gates pass (incl fixed test-waits pragma); remaining reds reproduce on clean base (docs-gen-check per sase-1lh.4 note, _lint-pyscripts, 4 docs-epic reds owned by sase-1lh.1) plus one zsh PTY load-flake that passes unloaded; filed as PROPOSED FOLLOW-UP notes.

## Dependencies

- **Blocks:** [sase-1lh.6](sase-1lh.6.md) ◐ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lh.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lh.2/README.md) | [sase-1lh.2](sase-1lh.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2e94255`](https://github.com/sase-org/sase/commit/2e94255b214d151ffea0f2e5642657b3b328b5e0) | fix(visual): repair deterministic visual-test failures (sase-1lh.2) | [sase-1lh.2](sase-1lh.2.md) | 2026-10-16 14:29:07 EDT |
