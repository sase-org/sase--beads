# Bead: sase-1sd.1 — Salvage and land the verified -p display-name resolution fix (sase-zo)

[Bead Pages](../README.md) / [sase-1sd](README.md) / sase-1sd.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1bp](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1bp.md) · **Assignee:** `sase-1sd.1` · **Size:** medium
**Created:** 2026-11-12 05:26:15 EST
**Plan:** [202611/next\_seven\_salvage\_and\_unstrand.md](https://github.com/sase-org/sase--plans/blob/main/202611/next_seven_salvage_and_unstrand.md)

## Description

salvage-display-name: sase repo list/log/open/path -p still resolves the project token as a directory key only, so `sase repo list -p sase` exits 2 on master (+10 corroboration). The complete, verified fix — registry-canonicalized -p accepting key, display name, or alias, with regression tests — sits uncommitted in the sase_21 workspace clone on athena (base 99932634cd). Salvage that diff, rebase it onto current master, re-run its tests, and land it before workspace retention reclaims the state.

## Notes

[2026-11-12T10:56:15Z · sase-1sd.1] Salvage applied: sase_21 diff at base 99932634cd (workspace_handler_context.py + patch_sync.py + tests/main/test_project_ref_canonicalization.py, 7 tests) applied cleanly onto ea4121387b with git apply --check 0 on both patches; git diff base-to-HEAD on both source files was empty so no rebase drift. Reproduced before: sase repo list -p sase failed with no WORKSPACE_DIR in /home/bryan/.sase/projects/sase/sase.sase. After fix: -p sase, -p SASE, -p gh_sase-org__sase all exit 0 with identical 14-repo inventory (project field sase); repo log -p sase, repo path sase -p sase, repo open sase -p sase -w 18 all exit 0. Salvaged suite: 7/7 pass. Focused: test_repo_handler.py 8 pass; repo_log/open_aliases/open_linked/open_resolution/open_workspace/patch_sync_external 40 pass.

[2026-11-12T10:56:30Z · sase-1sd.1] sase_29 state per decision sase21_only (record-only, not salvaged): base 0cc9fad474, dirty 7 modified + 1 untracked: M src/sase/axe/_run_agent_runner_shutdown_markers.py, M src/sase/axe/run_agent_exec_finalize.py, M src/sase/axe/run_agent_runner_errors.py, M src/sase/axe/runner_failure_facts.py, M src/sase/axe/source_skew.py, M tests/axe/test_runner_failure_facts.py, M tests/axe/test_source_skew.py, ?? tests/test_agent_auto_restart_signature_skew_replay.py. Matches plan description (8 files incl. signature-skew replay test). Left untouched for owner / resumed sase-1ra.7.

[2026-11-12T10:56:39Z · sase-1sd.1] PROPOSED FOLLOW-UP: carried_repo reopen guard stays open — a carried_repo obligation whose staged successor never adopts leaves the predecessor bead closed with no reopen (mirror sase-1oh.4 guard). Owning surface is sase-1ra.8 per decision reopen_guard=defer; this phase did not touch the guard.

[2026-11-12T10:56:55Z · sase-1sd.1] PROPOSED FOLLOW-UP: 5 workspace_handler tests fail identically on clean base (no fix applied): test_json_list_includes_registered_workspace, test_open_materializes_configured_sibling_project_spec, test_implicit_state_linked_repo_spec_is_healed_to_sibling, test_configured_sibling_with_explicit_non_sibling_state_fails, test_configured_sibling_with_workspace_dir_and_explicit_enabled_state_fails. Verified via git stash on this workspace (5 failed, 27 passed both before and after). Pre-existing, outside sase-1sd.1 scope.

[2026-11-12T10:57:03Z · sase-1sd.1] sase_21 restore deferred: phase requires restore only after rebased fix is committed in this workspace. Fix is applied but uncommitted (host commits on close), so sase_21 left dirty/intact for recovery. Follow-up restores sase_21 to clean only after this bead closes and the fix is committed; if sase_21 content ever mismatches what landed, leave untouched and record why. Check run cdb14e97a0880c9de1127a1bd78bcdf6 handed to verify monitor; follow-up closes bead on green.

## Dependencies

- **Blocks:** [sase-1sd.2](sase-1sd.2.md) ◐ · ⧖ 2026-11-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sd.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sd.1.md) | [sase-1sd.1](sase-1sd.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e072729`](https://github.com/sase-org/sase/commit/e07272959937e0a39e1b7c31254b252e657978be) | fix(repo): resolve -p project ref through registry display names and aliases | [sase-1sd.1](sase-1sd.1.md) | 2026-11-12 06:01:49 EST |
