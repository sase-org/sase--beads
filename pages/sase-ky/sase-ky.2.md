# Bead: sase-ky.2 — Switch every Python plan-reference literal to plan

[Bead Pages](../README.md) / [sase-ky](README.md) / sase-ky.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zl.f1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zl.f1.md) · **Assignee:** `sase-ky.2` · **Size:** medium
**Created:** 2026-08-13 12:22:01 EDT · **Closed:** 2026-08-13 14:24:47 EDT
**Plan:** [plans:202608/plan\_ref\_kind\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202608/plan_ref_kind_rename.md)

## Description

python: replace the functional `plans:` literals in src/sase with a single shared constant set to `plan:`, update CLI help and docstrings, add the sidecar ref-kind naming regression test, and fix the 82 affected test files plus any visual snapshots.

## Notes

[2026-08-13T18:23:50Z · sase-ky.2] PROPOSED FOLLOW-UP: tests/ace/tui/visual/_ace_prompt_png_snapshot_helpers.py and test_ace_png_snapshots_agents_clan_panel.py fixture edits only affect 5 PNGs (prompt_artifact_ref_highlight_120x40, prompt_glossary_highlight_dark/light_120x40, prompt_glossary_wrapped_highlight_dark_120x40, agents_clan_panel_epic_logical_prompt_hints_120x40), but a prior wholesale `just test-visual --sase-update-visual-snapshots` sweep (before this close) silently rewrote 211 unrelated goldens, at least one of which (changespec_selected_row_120x40.png) was captured with the footer keybinding-hint text missing entirely. I reverted the 211 unrelated PNGs to HEAD and regenerated only the 5 legitimately-affected ones. Future phases that touch visual fixtures should scope regeneration to the specific affected test files/fixtures rather than running the whole `test-visual` suite with the update flag, and should sanity-check that unrelated goldens do not move.

[2026-08-13T18:24:47Z · sase-ky.2] Added shared PLAN_REFERENCE_KIND/PREFIX constants in sdd/plan_refs.py; migrated all functional plans: literals in src/sase to plan: (13 files, plus 3 read-side legacy aliases kept with immutable-history comments); updated CLI help/docstrings; added tests/test_sidecar_ref_kind_naming.py; fixed 83 test files (82 planned + 1 discovered artifact_ref_entries.py role-default site) plus 5 visual PNG snapshots whose fixture text changed. Verified: ruff check/format clean, mypy clean (3073 files), full non-visual suite 29588 passed/1 pre-existing-on-master failure (confirmed via git stash, unrelated circular-import test)/10 skipped, and the 5 affected + sibling visual snapshots pass cleanly in isolation. Found and fixed a regression from a prior wholesale --sase-update-visual-snapshots run that had silently rewritten 211 unrelated PNG goldens (one with missing footer-hint text); reverted those to HEAD. Full-suite test-visual could not be verified clean end-to-end due to heavy host contention (load avg ~40) unrelated to this change; a byte-identical-to-HEAD golden failed under that load, confirming the failures are environmental, not regressions.

## Dependencies

- **Depends on:** [sase-ky.1](sase-ky.1.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-ky.3](sase-ky.3.md) ◐ · ⧖ 2026-08-13
- **Blocks:** [sase-ky.4](sase-ky.4.md) ✓ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ky.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ky.2/README.md) | [sase-ky.2](sase-ky.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cbd47ed`](https://github.com/sase-org/sase/commit/cbd47ed11055e5de11522050499b8c2a7137a145) | refactor(sdd): rename plans: reference literal to plan: across Python | [sase-ky.2](sase-ky.2.md) | 2026-08-13 14:25:51 EDT |
