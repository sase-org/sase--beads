# Bead: sase-m6.5 — The shared shell and its visual grammar

[Bead Pages](../README.md) / [sase-m6](README.md) / sase-m6.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.01u](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.01u.md) · **Assignee:** `sase-m6.5` · **Size:** large
**Created:** 2026-08-14 17:05:54 EDT · **Closed:** 2026-08-14 23:16:26 EDT
**Plan:** [202608/artifacts\_pane\_contract.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_pane_contract.md)

## Description

shell: build the one chrome every pane renders through, specify and implement the five canonical pane states, and replace drifting provider accents with a deterministic perceptual palette.

## Notes

[2026-08-15T03:16:26Z · sase-m6.5] Phase `shell` implemented per plan: contract-driven Artifacts shell primitives (shell.py: state enum/resolver, header/badge/empty-card/degraded-card/footer renderers), Beads/Files/Plans/Documents wired through the five-state grammar with stale/loading fixes, Stitches footer unified, degraded pane replaced with shared renderer, curated 9-color OKLCH provider palette replacing the 6-color foundation, and docs/artifacts_pane_visual_grammar.md added.

Verification this pass:
- `just install` clean.
- `just check` (fmt/lint/mypy/symvision/toobig/SASE validation/committed plans + scoped tests): all green.
- `just test` (full non-visual suite, 30204 tests): 30204 passed, 10 skipped, 0 failed.
- `just test-visual` (full PNG suite, 677 nodes): investigated all failures individually against a stashed clean-baseline control run.
  - 31 nodes (axe editor modals, notification cards, glossary preview, plan toasts, copy-as palette, at-reference completion) failed only with this diff applied; root cause confirmed via diff-image inspection: the app's default landing view is an Artifacts pane, so its footer chrome (now bold keys + accent + middle-dot separators, matching the plan's unified grammar) is visible in the background of these full-screen fixtures. Confirmed identical, localized diff region across multiple samples. Updated all 31 goldens via --sase-update-visual-snapshots and reconfirmed green.
  - 6 nodes fail identically on a clean stashed origin/master checkout with no diff applied (artifacts_beads_populated / artifacts_beads_reopened_detail: pre-existing `select_entry_target` assertion failure unrelated to rendering; artifacts_files_nested_strip, models_panel_builtin_selection_effort_step, help_panel_keymaps, help_panel_filter: pre-existing sub-1% pixel drift). Left untouched; not caused by this phase.
- `just check-full` could not be run as a single recipe in this non-interactive single-turn session (sase monitor is unavailable here); its coverage was reproduced by running `just check` + full `just test` + full `just test-visual` individually as above.

PROPOSED FOLLOW-UP: file a task bead for the 6 pre-existing baseline failures above (one functional bug in ArtifactsBeadsPane.select_entry_target affecting two beads PNG goldens, plus four small pixel-drift PNG goldens) once back in a context that can create task beads.

## Dependencies

- **Depends on:** [sase-m6.4](sase-m6.4.md) ✓ · ⧖ 2026-08-14
- **Blocks:** [sase-m6.7](sase-m6.7.md) ◐ · ⧖ 2026-08-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m6.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.5.md) | [sase-m6.5](sase-m6.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d19d086`](https://github.com/sase-org/sase/commit/d19d08641246a2b0f9276fded07d93004815d640) | feat(tui): give every Artifacts pane a shared shell and visual grammar | [sase-m6.5](sase-m6.5.md) | 2026-08-14 23:17:01 EDT |
