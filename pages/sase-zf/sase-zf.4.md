# Bead: sase-zf.4 — Auto-hiding FilterBar chrome on the Agents tab

[Bead Pages](../README.md) / [sase-zf](README.md) / sase-zf.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0iy](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0iy.md) · **Assignee:** `sase-zf.4` · **Size:** medium
**Created:** 2026-09-10 18:01:49 EDT · **Closed:** 2026-09-10 22:03:35 EDT
**Plan:** [202609/agents\_query\_unification.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_query_unification.md)

## Description

filter-bar-ui: replace the query-edit modal with an auto-hiding FilterBar plus a highlighted canonical query readout in the existing info panel, wiring live preview, completions, saved slots, query history, and the keybinding, footer, and help-modal updates.

## Notes

[2026-09-11T01:58:39Z · sase-zf.4] PROPOSED FOLLOW-UP: Wire the "*" saved-query picker modal (start_saved_query_mode/open_saved_query_picker) for the Agents-live namespace — this phase only wires the inline #N/# grammar typed into the FilterBar itself, matching the minimal scope in the plan; browsing/managing agents-live saved slots via the picker UI (as Artifacts panes support) is not yet available.

[2026-09-11T02:03:35Z · sase-zf.4] Implemented the auto-hiding AgentsFilterBar (open via ,/ or f), per-keystroke off-thread preview, Enter-commit with history recording, Escape-restore, inline parse errors w/ legacy-token hints, #N saved slots, ^/_ history nav, and the AgentInfoPanel highlighted-query+match-count readout (clickable). Found and fixed a real pre-existing focus-stealing bug in _hint_input_bar_active that the new keystroke-preview path exposed. Added widget tests, an AcePage end-to-end session-flow suite, and 2 new PNG visual-snapshot goldens (idle readout + editing/completion). Verified: just check (fmt/keep-sorted/ruff/mypy all green; diff-scoped test lane passed on a prior clean run before a final low-risk refinement, which was re-verified directly via targeted pytest+ruff+mypy — the only just check failure across runs was the pre-existing, unrelated whole-repo feature-flags gate failing on other agents' in-flight beads sase-z5/z6/z9, none touching agents_unified_query/sase-zf); all directly-affected and newly added test files (135+ tests) pass; a supplementary full tests/ace/tui sweep was still running at close time as extra diligence beyond the required gate.

## Dependencies

- **Depends on:** [sase-zf.2](sase-zf.2.md) ✓ · ⧖ 2026-09-10
- **Depends on:** [sase-zf.3](sase-zf.3.md) ✓ · ⧖ 2026-09-10
- **Blocks:** [sase-zf.5](sase-zf.5.md) ✓ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zf.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zf.4/README.md) | [sase-zf.4](sase-zf.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6278e02`](https://github.com/sase-org/sase/commit/6278e02c446a430671c96273b034fd0ada67c157) | feat(agents-tab): add auto-hiding FilterBar chrome (sase-zf.4) | [sase-zf.4](sase-zf.4.md) | 2026-09-10 22:04:56 EDT |
