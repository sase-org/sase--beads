# Bead: sase-rs.3 — Shared Python resolution and mutation facade

[Bead Pages](../README.md) / [sase-rs](README.md) / sase-rs.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.09g](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.09g.md) · **Assignee:** `sase-rs.3` · **Size:** medium
**Created:** 2026-08-21 09:58:41 EDT · **Closed:** 2026-08-21 12:47:27 EDT
**Plan:** [202608/feature\_flag\_control\_center.md](https://github.com/sase-org/sase--plans/blob/main/202608/feature_flag_control_center.md)

## Description

runtime: add the thin typed Python adapter, insert saved machine preferences into feature-flag resolution at the designed precedence, synchronize process transport after writes, and return one structured mutation outcome used by every frontend.

## Notes

[2026-08-21T16:46:20Z · sase-rs.3] PROPOSED FOLLOW-UP: just check _lint-ruff fails on pre-existing F601 duplicate key sase_finalizer in src/sase/telemetry/catalog.py — unrelated to the Python flag facade; do not edit that catalog from this epic.

[2026-08-21T16:46:40Z · sase-rs.3] PROPOSED FOLLOW-UP: just check _lint-flags fails on closed flag beads sase-qe (coder_inherits_planner_chat) and sase-qh (epic_resume_gate) with surviving registry definitions, plus live orphan sase-rc (artifact_links) — same class of unrelated integrity failures sase-rs.2 reported.

[2026-08-21T16:46:58Z · sase-rs.3] PROPOSED FOLLOW-UP: just test-scoped (escalated) fails tests/main/test_skills_handler.py::test_skills_inventory_reports_retired_deletion_drift — retired skill path not in inventory output; unrelated to feature-flag resolution.

[2026-08-21T16:47:27Z · sase-rs.3] Verified the shared Python facade: src/sase/feature_flags/state.py wraps feature_flag_state_get/set through sase_home() with defensive wire validation; resolve_feature_flags applies saved state after overlay and before overrides/env/CLI as source=state (rendered SAVED); set_saved_feature_flag is the only mutation path (registry check, Rust RMW, SASE_FEATURE_FLAGS merge, snapshot invalidate, structured FeatureFlagMutationOutcome); unknown stored keys stay in the store and as diagnostics but not in effective decisions; mutations rewrite only feature_flags.json. Focused feature-flag tests passed; tools/check_feature_flags --static and whole-repo mypy passed; sase bead epic-symbols sase-rs.3 had no leftovers. just check still fails on unrelated pre-existing gates (ruff F601 in telemetry/catalog.py, flag beads sase-qe/sase-qh/sase-rc, symvision private-imports, toobig declaration.py). Scoped tests escalated for a stale coverage baseline; the import-graph-sized run was 10842 passed / 1 unrelated skills-inventory failure.

[2026-08-21T16:48:35Z · sase-rs.3] Verified the shared Python facade: src/sase/feature_flags/state.py wraps feature_flag_state_get/set through sase_home() with defensive wire validation; resolve_feature_flags applies saved state after overlay and before overrides/env/CLI as source=state (rendered SAVED); set_saved_feature_flag is the only mutation path (registry check, Rust RMW, SASE_FEATURE_FLAGS merge, snapshot invalidate, structured FeatureFlagMutationOutcome); unknown stored keys stay in the store and as diagnostics but not in effective decisions; mutations rewrite only feature_flags.json. Focused feature-flag tests passed; tools/check_feature_flags --static and whole-repo mypy passed; sase bead epic-symbols sase-rs.3 had no leftovers.

## Dependencies

- **Depends on:** [sase-rs.2](sase-rs.2.md) ✓ · ⧖ 2026-08-21
- **Blocks:** [sase-rs.4](sase-rs.4.md) ◐ · ⧖ 2026-08-21
- **Blocks:** [sase-rs.5](sase-rs.5.md) ◐ · ⧖ 2026-08-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rs.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rs.3/README.md) | [sase-rs.3](sase-rs.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b88dfc7`](https://github.com/sase-org/sase/commit/b88dfc729359edaf7bda546e6bf581c7f2266b07) | fix(telemetry): drop duplicate sase\_finalizer catalog entries | [sase-rs.3](sase-rs.3.md) | 2026-08-21 12:55:10 EDT |
| sase | [`9223d47`](https://github.com/sase-org/sase/commit/9223d47c4617075c6298c2dd4663b56ecb6281ac) | feat(flags): add shared Python saved-state resolution and mutation facade | [sase-rs.3](sase-rs.3.md) | 2026-08-21 12:57:16 EDT |
