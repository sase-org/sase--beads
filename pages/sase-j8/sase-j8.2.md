# Bead: sase-j8.2 — Rename the ACE Artifacts sub-tab identifier to stitches

[Bead Pages](../README.md) / [sase-j8](README.md) / sase-j8.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xn](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xn/README.md) · **Assignee:** `sase-j8.2` · **Size:** medium
**Created:** 2026-08-10 16:19:07 EDT · **Closed:** 2026-08-10 17:45:06 EDT
**Plan:** [202608/stitch\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202608/stitch_rename.md)

## Description

subtab-id: rename the ACE Artifacts sub-tab identifier from `commits` to `stitches` across `artifact_tabs.py` and every consumer, including the pane DOM ids and their `styles.tcss` selectors, without changing any displayed text.

## Notes

[2026-08-10T21:44:30Z · sase-j8.2] PROPOSED FOLLOW-UP: just check-full flagged two new reproducible test flakes unrelated to this rename — tests/ace/tui/test_logs_pane.py::test_logs_tab_g_and_shift_g_scroll_detail_extremes and tests/test_bead/test_plus_one_presentation.py::test_post_close_plus_one_badge_marker_search_and_json_agree — neither touches ACE Artifacts/copy-mode/keymaps code; file task beads to investigate and stabilize them, then add to tests/reproducible_flake_baseline.txt.

[2026-08-10T21:45:06Z · sase-j8.2] Renamed the ACE Artifacts sub-tab identifier from commits to stitches in artifact_tabs.py (ArtifactsSubTab/ArtifactsPaneKey literals, DEFAULT_ARTIFACTS_SUBTAB, ARTIFACTS_SUBTAB_ORDER, ARTIFACTS_PANE_IDS, ARTIFACTS_ACCENTS) and every consumer across actions/, commands/, widgets/artifacts/, plus DOM ids (artifacts-commits-pane -> artifacts-stitches-pane, commits-detail-scroll and the 10 pane-internal #commits-* ids -> stitches-* equivalents) and their styles.tcss selectors. No displayed text changed except two auto-derived labels (subtab.title() in patch_onboarding.py and the copy-as-palette 'N marked <subtab>' subtitle) which now correctly read Stitches/stitches as an unavoidable side effect of the identifier itself changing; both PNG goldens (help_guide_changespecs_120x40, copy_as_commits_marked_light_80x30) were regenerated and visually diffed to confirm only that label text moved with no layout corruption. Left keymap action ids (commits_*), the artifacts_commits copy-mode group, and the ace.artifacts.commits config key untouched (config-keys phase, sase-j8.3) but added narrow TODO(sase-j8.3)-tagged bridges in _palette_artifacts.py, _artifacts.py, _keybinding_modes.py, and commands/availability.py so copy-mode/Copy-as-palette functionality for the renamed pane keeps working until that group is renamed. Kept commits_pane.py/CommitsPane/CommitsTimeline and the vcs_log/vcs_list engines untouched per scope boundaries; added stitches->commit to artifact_ref_entries.py's kind map alongside the existing commits/commit legacy keys. Updated ~50 consumer test files (DOM ids, subtab literals, marked-target keys) and added a regression test asserting DEFAULT_ARTIFACTS_SUBTAB == stitches and that ARTIFACTS_SUBTAB_ORDER leads with it. Verified: just check (all lint gates + scoped tests) clean; just test full suite 28565 passed/10 skipped/0 failed; just test-visual 648 passed/1 skipped; just check-full green except its selection-health flake-baseline gate, which flagged two new reproducible flakes in unrelated files (tests/ace/tui/test_logs_pane.py, tests/test_bead/test_plus_one_presentation.py) that don't touch any ACE Artifacts/copy-mode/keymaps code — recorded as a PROPOSED FOLLOW-UP note on this bead.

[2026-08-10T21:45:53Z · sase-j8.2] Renamed ACE Artifacts sub-tab identifier from 'commits' to 'stitches' across artifact_tabs.py and all consumers (actions, commands, widgets, DOM ids, styles.tcss selectors) without changing displayed text, except two auto-derived labels (onboarding panel title-case, copy-as-palette 'N marked stitches' subtitle) whose PNG goldens were regenerated and visually verified. Left keymap action ids, the artifacts_commits copy-mode group, and the ace.artifacts.commits config key untouched (config-keys phase sase-j8.3 scope) with small TODO(sase-j8.3)-tagged bridge shims. Verified: just check clean; full suite 28565 passed/0 failed; visual snapshot suite 648 passed. just check-full green except a pre-existing flake-baseline gate (logs pane, bead badge presentation) unrelated to this diff, recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-j8.3](sase-j8.3.md) ◐ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-j8.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j8.2/README.md) | [sase-j8.2](sase-j8.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c69d163`](https://github.com/sase-org/sase/commit/c69d16378ce32661565654463c19f8dd03c2ac76) | refactor(ace): rename Artifacts commits sub-tab identifier to stitches | [sase-j8.2](sase-j8.2.md) | 2026-08-10 17:47:04 EDT |
