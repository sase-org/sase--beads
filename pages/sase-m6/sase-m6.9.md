# Bead: sase-m6.9 — Unified Artifacts keymap with a safe migration

[Bead Pages](../README.md) / [sase-m6](README.md) / sase-m6.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.01u](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.01u.md) · **Assignee:** `sase-m6.9` · **Size:** medium
**Created:** 2026-08-14 17:06:24 EDT · **Closed:** 2026-08-16 15:59:43 EDT
**Plan:** [202608/artifacts\_pane\_contract.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_pane_contract.md)

## Description

keymap: unify the six Artifacts verbs whose meanings are inverted between Patch and its siblings, shipped together with action aliases, a doctor advisory and a one-shot config migration.

## Notes

[2026-08-16T17:27:19Z · 03y] CARRIED FORWARD from sase-m6.7.1.6 (child epic closed by 03y on user request, in place of its dismissed land agent): 'Files o and Beads o still own grouping-cycle' — cycle_grouping_mode is reachable on Stitches/Plans/Patches, but check_app_action keeps it off on files and beads so files_open_external and beads_open_bug keep 'o'. This phase (keymap) should assign a non-colliding grouping-cycle key or move those open actions, and the o-key pane exceptions currently asserted by the artifacts_contract reachability probe (beads=[cycle_grouping_mode, cycle_grouping_mode_reverse], files=[same]) must be updated in lockstep.

[2026-08-16T19:56:33Z · sase-m6.9] PROPOSED FOLLOW-UP: tests/main/test_var_integration.py::test_var_cli_end_to_end_refreshes_index_and_round_trips_machine_outputs fails on clean HEAD (confirmed via git stash) — asserts read_agent_artifact_index_meta(...) == str(AGENT_ARTIFACT_INDEX_SCHEMA_VERSION) but the upgraded index reports the version one lower than the live constant. Unrelated to sase-m6.9 keymap work.

[2026-08-16T19:57:19Z · sase-m6.9] PROPOSED FOLLOW-UP: tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[stats] fails on clean HEAD (confirmed via git stash) — golden stdout fixture is missing a "Flags:       0" line that the current `sase bead stats` output includes. Unrelated to sase-m6.9 keymap work; the golden fixture needs regenerating.

[2026-08-16T19:58:34Z · sase-m6.9] PROPOSED FOLLOW-UP: `just check`'s _lint-symvision gate fails on clean HEAD (confirmed via git stash) — the epic-symbol whitelist in the symvision invocation still lists 9 sase-n9(...) entries but bead sase-n9 is closed, so symvision refuses to run ("Remove this stale --epic-symbol entry and clean up the symbol"). Blocks a clean `just check` run for any agent until the stale whitelist entries are removed and the underlying symbols cleaned up per sase/memory/symvision.md. Unrelated to sase-m6.9 keymap work.

[2026-08-16T19:59:43Z · sase-m6.9] Implemented sase-m6.9: unified the six Patch-vs-siblings key collisions (y=copy/@ref, R=refresh app-wide, l/h=expand/collapse, L=artifacts_link_jump freeing zL for Patch fold-snap, o=artifacts_open_external freeing B/I for grouping-cycle everywhere including Beads/Files, mark_pr_origin/start_rewind to bang mode !o/!R), shipped action-name aliases + a sase doctor advisory + sase config migrate-keymap-actions (all three verified end-to-end against a live isolated HOME), fixed Beads' previously-false GROUPING capability declaration, and added a post-update-triggered (not every-mount) one-shot keymap-unification toast so it never pollutes AcePageGroup-based tests. Fixed ~25 test files whose keymap-name/key expectations were superseded by this redesign, plus a genuine gap (missing 'bug' copy target in beads DISPATCH_ORDER) and a genuine regression (Agents-tab R-key group-revival collided with the new global R=refresh; resolved by routing revival through bang-mode !R, matching docs/ace.md's already-updated instructions). Verified: ruff, mypy, pyscripts, test-waits, changelog, patch/stitch-terminology, and toobig lint gates all pass; full test-scoped suite (31238-31242 tests) passes except 3 pre-existing failures confirmed unrelated via git-stash-on-HEAD (test_var_integration schema-version test, test_cli_golden[stats] golden mismatch, and a stale symvision epic-whitelist for closed bead sase-n9) — each recorded as a PROPOSED FOLLOW-UP note on this bead. Two additional test_config_cache/test_config_center_state failures observed once under 14-way parallel load reproduced as flaky (passed in isolation), unrelated to this change.

## Dependencies

- **Blocks:** [sase-m6.10](sase-m6.10.md) ◐ · ⧖ 2026-08-14
- **Depends on:** [sase-m6.7](sase-m6.7.md) ✓ · ⧖ 2026-08-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m6.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m6.9/README.md) | [sase-m6.9](sase-m6.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3c9df11`](https://github.com/sase-org/sase/commit/3c9df1182ce53093c637909edef19c1297679b4e) | feat(ace-tui)!: unify the Artifacts keymap across Patch and its siblings | [sase-m6.9](sase-m6.9.md) | 2026-08-16 16:01:10 EDT |
