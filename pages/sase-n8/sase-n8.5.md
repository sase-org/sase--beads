# Bead: sase-n8.5 — Frontend-neutral alias-history adapter

[Bead Pages](../README.md) / [sase-n8](README.md) / sase-n8.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03t](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03t.md) · **Assignee:** `sase-n8.5` · **Size:** medium
**Created:** 2026-08-16 11:32:21 EDT · **Closed:** 2026-08-16 14:20:49 EDT
**Plan:** [202608/launch\_control\_alias\_history.md](https://github.com/sase-org/sase--plans/blob/main/202608/launch_control_alias_history.md)

## Description

adapter: add the presentation-neutral adapter that composes the core query with the configured limit, resolves ProjectSpec keys to configured project names, classifies each run's provenance into direct / via-another-alias / default / unrecorded, and returns typed view models with the group truncation state.

## Notes

[2026-08-16T18:18:28Z · sase-n8.5] PROPOSED FOLLOW-UP: full-suite xdist config flakes — just check escalated (Justfile broadening rule) and failed tests/test_config.py::test_load_config_layers_overlay_detected plus three tests/test_config_cache.py token-gate tests; all four passed in isolation and this phase did not touch config loading.

[2026-08-16T18:19:13Z · sase-n8.5] PROPOSED FOLLOW-UP: panel tab-strip compact test fails in isolation — tests/ace/tui/test_panel_tab_strip_compact.py::test_reflow_to_fit_ladder_picks_tier_by_width stays at tier=full after resize to width 20; unrelated to alias-history adapter, reproduces outside the full suite.

[2026-08-16T18:19:58Z · sase-n8.5] PROPOSED FOLLOW-UP: bead stats CLI golden stale — tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[stats] actual stdout has an extra "Flags: 0" line vs fixtures; unrelated to alias-history adapter and fails in isolation.

[2026-08-16T18:20:49Z · sase-n8.5] Verified frontend-neutral alias-history adapter: load_alias_history defaults limit_per_alias from get_model_alias_history_limit, maps ProjectSpec keys through project_display_name_for (unknown keys fall back to themselves), classifies provenance as direct/default/via @prev/unrecorded including unknown future origins and indirect-regardless-of-origin, preserves per-group truncation/requested/returned counts, derives done/failed/running rollups, and computes unformatted duration_seconds. just lint gates passed (ruff, mypy, symvision after moving used n8 wire symbols off the whitelist and adding sase-n8 epic-symbol entries for the new public view types). Adapter unit tests: 17 passed. just check escalated to the full suite because Justfile is a broadening path (31243 passed, 6 failed, 14 visual-env errors); the four config failures passed in isolation, and the two isolation-reproducible failures (tab-strip compact, bead stats golden Flags line) are unrelated and recorded as PROPOSED FOLLOW-UP.

[2026-08-16T18:22:20Z · sase-n8.5] Verified frontend-neutral alias-history adapter: load_alias_history defaults limit_per_alias from get_model_alias_history_limit, maps ProjectSpec keys through project_display_name_for (unknown keys fall back to themselves), classifies provenance as direct/default/via @prev/unrecorded including unknown future origins and indirect-regardless-of-origin, preserves per-group truncation/requested/returned counts, derives done/failed/running rollups, and computes unformatted duration_seconds. just lint gates passed (ruff, mypy, symvision). Adapter unit tests: 17 passed. just check escalated to the full suite because Justfile is a broadening path (31243 passed, 6 failed, 14 visual-env errors); the four config failures passed in isolation, and the two isolation-reproducible failures (tab-strip compact, bead stats golden Flags line) are unrelated and recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-n8.3](sase-n8.3.md) ✓ · ⧖ 2026-08-16
- **Depends on:** [sase-n8.4](sase-n8.4.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-n8.6](sase-n8.6.md) ◐ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n8.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n8.5/README.md) | [sase-n8.5](sase-n8.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`556a78b`](https://github.com/sase-org/sase/commit/556a78bcacbed60137dd69cbf33e5417e8b6acff) | feat(llm-provider): add frontend-neutral alias-history adapter | [sase-n8.5](sase-n8.5.md) | 2026-08-16 14:25:32 EDT |
