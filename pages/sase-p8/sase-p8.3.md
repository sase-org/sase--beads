# Bead: sase-p8.3 — Shared out-of-process family spawn

[Bead Pages](../README.md) / [sase-p8](README.md) / sase-p8.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05f](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05f.md) · **Assignee:** `sase-p8.3` · **Size:** medium
**Created:** 2026-08-17 19:01:00 EDT · **Closed:** 2026-08-17 20:23:18 EDT
**Plan:** [202608/agent\_pipe.md](https://github.com/sase-org/sase--plans/blob/main/202608/agent_pipe.md)

## Description

spawn: put the detached child spawn and the family-attach env encoding behind one primitive that monitor follow-up and retry spawn both call.

## Notes

[2026-08-18T00:22:21Z · sase-p8.3] PROPOSED FOLLOW-UP: Justfile symvision recipe (_lint-symvision) still carries 6 --epic-symbol entries for sase-p1.2, which is already closed, so `just check` fails for every agent until they are cleaned up (the closing agent for a phase should remove its own entries, per the project convention that "they go stale the instant this phase closes and turn unrelated agents just check red"). Verified via: running symvision with those 6 entries dropped correctly flags GlossaryConflictError/GlossaryMutationError/GlossaryMutationOutcome/GlossaryValidationError/add_glossary_term/delete_glossary_term in src/sase/glossary/mutation.py as the only unused-public-symbol violations -- i.e. the entries are genuinely stale, not still needed.

[2026-08-18T00:22:39Z · sase-p8.3] PROPOSED FOLLOW-UP: tests/ace/tui/test_panel_tab_strip_compact.py::test_reflow_to_fit_ladder_picks_tier_by_width fails consistently (reproduced twice) on a fresh workspace with `assert strip._tier == "compact"` -> actual "full" after resizing to (20, 5); unrelated to sase-p8.3 (spawn/family-attach code), pre-existing TUI panel-tab-strip reflow-tier-by-width logic bug or environment-dependent layout assumption.

[2026-08-18T00:22:55Z · sase-p8.3] PROPOSED FOLLOW-UP: This ephemeral workspace (sase_25) fails all 14 tests/ace/tui/visual/test_visual_idle.py setup fixtures with RendererEnvironmentError (markdown-it-py, mdit-py-plugins, pillow, pygments, resvg-py, rich, textual, tree-sitter version mismatches vs the pinned renderer_env manifest; resvg-py not installed at all). Only surfaces when a scoped test run escalates to the full suite (core-identity-changed changes trigger this). Needs `just install-visual` in this workspace, or investigate why editable installs are drifting from the pinned visual snapshot manifest.

[2026-08-18T00:23:18Z · sase-p8.3] Added src/sase/agent/detached_child.py: shared spawn_detached_child/spawn_family_successor/family_attach_env primitive. Rewired _family_attach_launch.py, axe/run_agent_retry_spawn.py, and monitor/followup.py to use it, removing duplicated timestamp-reservation/workflow-name/env-encoding logic. Verified: sase bead epic-symbols sase-p8.3 reports no entries; symvision clean for all touched files (confirmed by excluding the unrelated already-closed sase-p1.2 stale entries and seeing only sase-p1.2's own glossary symbols flagged, filed as follow-up); ruff/mypy/fmt/toobig/validate/validate-committed-plans all pass; full 32.6k-test suite run twice (17min/15min) -- first run caught two real regressions from the refactor (tests/fakey/test_retry_pipeline_e2e.py and tests/monitor/test_monitor_start.py patching now-removed names/relying on the old return-value contract), fixed both, second run is clean except one pre-existing unrelated TUI reflow-tier test and 14 pre-existing renderer-environment-mismatch errors in the visual snapshot suite (both filed as follow-ups, neither touches spawn/family-attach code).

## Dependencies

- **Blocks:** [sase-p8.6](sase-p8.6.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p8.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p8.3/README.md) | [sase-p8.3](sase-p8.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d8a903a`](https://github.com/sase-org/sase/commit/d8a903ac90085156e126de50e8c92a54a3ab7ad8) | refactor(agent): share the out-of-process family-spawn primitive | [sase-p8.3](sase-p8.3.md) | 2026-08-17 20:24:10 EDT |
