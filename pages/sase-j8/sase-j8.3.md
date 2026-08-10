# Bead: sase-j8.3 — Rename user-configurable commits keymap and config keys

[Bead Pages](../README.md) / [sase-j8](README.md) / sase-j8.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xn](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xn/README.md) · **Assignee:** `sase-j8.3` · **Size:** medium
**Created:** 2026-08-10 16:19:41 EDT · **Closed:** 2026-08-10 18:50:01 EDT
**Plan:** [202608/stitch\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202608/stitch_rename.md)

## Description

config-keys: rename the `commits_*` app keymap actions to `stitches_*`, the `artifacts_commits` copy-mode group to `artifacts_stitches`, and the `ace.artifacts.commits` config block to `ace.artifacts.stitches`, each with a deprecated legacy name that still loads and warns.

## Notes

[2026-08-10T22:49:41Z · sase-j8.3] PROPOSED FOLLOW-UP: just check-full flake-baseline gate fails on two reproducible flakes unrelated to this phase (tests/ace/tui/test_logs_pane.py::test_logs_tab_g_and_shift_g_scroll_detail_extremes, tests/test_bead/test_plus_one_presentation.py::test_post_close_plus_one_badge_marker_search_and_json_agree). Neither test references commits/stitches; file/fix the flake-baseline entries so check-full is unblocked for landing.

[2026-08-10T22:50:01Z · sase-j8.3] Renamed the ten commits_* app keymap actions to stitches_* (app_keymaps.py, metadata.py, bindings.py, availability.py, _app_metadata.py, commits_rendering.py, help modal) with legacy aliases in _LEGACY_APP_KEY_ALIASES; renamed the artifacts_commits copy-mode group to artifacts_stitches with a generalized {legacy: canonical} alias table in _migrate_copy_group_aliases(); renamed ace.artifacts.commits config block to ace.artifacts.stitches in schema/default_config/commit_config.py with commits fallback + deprecation warning; updated docs/ace.md and docs/configuration.md; extended tests (test_commits_config.py, test_keymaps_registry_loading.py, test_keymaps_app_bindings.py, copy-palette tests). Verified: just check passed clean (all lint gates + scoped test lane, which auto-escalated to the full suite via the src-data-asset rule and passed). just check-full: all lint gates and the full test-cost run passed; only the orthogonal flake-baseline gate failed, on two pre-existing flakes (test_logs_pane.py, test_plus_one_presentation.py) confirmed unrelated to this phase's diff — recorded as a PROPOSED FOLLOW-UP note.

## Dependencies

- **Depends on:** [sase-j8.2](sase-j8.2.md) ✓ · ⧖ 2026-08-10
- **Blocks:** [sase-j8.4](sase-j8.4.md) ◐ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-j8.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j8.3/README.md) | [sase-j8.3](sase-j8.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7a4b4da`](https://github.com/sase-org/sase/commit/7a4b4daa788b3db9542b593cdd3b7cd7c3e96b69) | refactor(ace): rename commits\_\* keymap actions, artifacts\_commits copy group, and ace.artifacts.commits config to stitches | [sase-j8.3](sase-j8.3.md) | 2026-08-10 18:51:06 EDT |
