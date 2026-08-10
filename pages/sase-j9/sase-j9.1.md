# Bead: sase-j9.1 — Add the \`-\` panel fold sweep with a per-panel reverse

[Bead Pages](../README.md) / [sase-j9](README.md) / sase-j9.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xo](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xo/README.md) · **Assignee:** `sase-j9.1` · **Size:** medium
**Created:** 2026-08-10 17:20:51 EDT · **Closed:** 2026-08-10 18:50:00 EDT
**Plan:** [202608/agents\_panel\_fold\_sweep.md](https://github.com/sase-org/sase--plans/blob/main/202608/agents_panel_fold_sweep.md)

## Description

sweep: add a configurable `collapse_panel_folds` action bound to `-` that saturates every open lane, clan, and top-level grouping banner in the focused tribe panel in one press, remembers exactly what it closed in a session-local per-panel record, and re-expands that record when the panel has nothing left to collapse. Works from whole-panel focus, from a row selection, and in merged layout. Resync the footer, command palette, help modal, and docs.

## Notes

[2026-08-10T22:48:42Z · sase-j9.1] PROPOSED FOLLOW-UP: isolate_panels (=) has no _KEY_ALIASES glyph entry like the new collapse_panel_folds (-) got — a user override spelled "=" is rejected by is_valid_key today. Add "=": "equals_sign" to _KEY_ALIASES in src/sase/ace/tui/keymaps/key_validation.py to close the same latent gap this phase fixed for "-".

[2026-08-10T22:48:59Z · sase-j9.1] PROPOSED FOLLOW-UP: just check-full flake-baseline gate (just selection-health --fail-on-new-flake) reports 2 pre-existing reproducible flakes unrelated to this phase: tests/ace/tui/test_logs_pane.py::test_logs_tab_g_and_shift_g_scroll_detail_extremes and tests/test_bead/test_plus_one_presentation.py::test_post_close_plus_one_badge_marker_search_and_json_agree. File task beads to fix or acknowledge these before an epic land next needs a clean just check-full.

[2026-08-10T22:49:15Z · sase-j9.1] PROPOSED FOLLOW-UP: while regenerating PNG goldens for this phase, found tests/ace/tui/visual/snapshots/png/prompt_stack_g_prefix_hints_120x40.png was already stale (unrelated to fold sweep) — its g-prefix hint list still showed the retired "gX save as local xprompt" instead of "gt new snippet...", presumably a golden the snippet-target-pane-lifecycle work (ba77762e6) missed updating. I refreshed it as part of just test-visual; worth auditing that landing for other missed goldens.

[2026-08-10T22:49:30Z · sase-j9.1] PROPOSED FOLLOW-UP: the new footer probes _panel_has_collapsible_folds / _panel_fold_sweep_restore_available (src/sase/ace/tui/actions/agents/_display_detail_footer.py) run unconditionally on every Agents-tab footer update, unlike sibling probes (lane/clan/group) which skip when tools_visible. Per the epic plans risk note, if SASE_TUI_PERF=1 j/k p95 regresses past 16ms on a large roster, memoize the probe on (id(self._agents), panel_key, panel_fold_version_signature(...)) as described in plans/202608/agents_panel_fold_sweep.md.

[2026-08-10T22:50:00Z · sase-j9.1] Implemented the - (collapse_panel_folds) panel fold sweep: PanelFoldSweepRecord model + FoldStateManager.restore_levels, new AgentPanelFoldSweepMixin (src/sase/ace/tui/actions/agents/_folding_panel_sweep.py) wired into the AgentTreeFoldingMixin chain, full keymap/command-palette/help-modal plumbing, footer collapse-folds/restore-folds chips, and docs (ace.md, agent_families.md). Made two _folding_clans.py helpers public (resolve_panel_clan_collapse_target, selected_enclosing_clan_fold_key) to satisfy symvision's private-cross-import rule. Verified: just install; just check (all lint gates + scoped tests) green; just check-full's real test run (test cost) passed, with only the unrelated flake-baseline meta-gate failing on 2 pre-existing flaky tests (noted as follow-up, not caused by this change); just test-visual green after regenerating 105 Agents-tab footer-reflow PNG goldens (spot-checked several diffs pixel-by-pixel to confirm churn is confined to the new footer chip, plus one incidental fix of an already-stale unrelated golden). New tests/ace/tui/test_agent_panel_fold_sweep.py (14 tests) covers whole-panel/row-focus/merged-layout sweep, restore with FoldLevel round-trip, sibling-panel isolation, ambiguous-owner skipping, per-panel record independence, retirement on panel death, and the reverse's liveness filter; existing keymap/command/footer test suites updated for the new binding.

[2026-08-10T22:50:44Z · sase-j9.1] Implemented the - panel fold sweep (collapse_panel_folds) with per-panel reverse restoration; verified via just check, just check-full, and just test-visual (105 goldens regenerated, spot-checked).

## Dependencies

- **Blocks:** [sase-j9.2](sase-j9.2.md) ◐ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-j9.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j9.1/README.md) | [sase-j9.1](sase-j9.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`62a4dde`](https://github.com/sase-org/sase/commit/62a4ddeb5feb6d5990921b113a0c776519df6096) | feat(ace): add \`-\` panel fold sweep with per-panel reverse | [sase-j9.1](sase-j9.1.md) | 2026-08-10 18:52:37 EDT |
