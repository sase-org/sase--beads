# Bead: sase-1rd.2 — Python facade, review snapshots, and CLI apply/restore

[Bead Pages](../README.md) / [sase-1rd](README.md) / sase-1rd.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.18e](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.18e.md) · **Assignee:** `sase-1rd.2` · **Size:** medium
**Created:** 2026-11-05 06:20:14 EST · **Closed:** 2026-11-05 10:06:00 EST
**Plan:** [202611/actionable\_run\_prune\_notifications.md](https://github.com/sase-org/sase--plans/blob/main/202611/actionable_run_prune_notifications.md)

## Description

trash_callers: ratchet the core pin, add the Python facade and the review-snapshot payload module, make `prune-runs --apply` quarantine fresh-intersect-reviewed runs, and post a result notification. `artifact trash` gains run batches, and the artifact index stays consistent.

## Notes

[2026-11-05T15:05:24Z · sase-1rd.2] PROPOSED FOLLOW-UP: tests/test_pytest_isolation_guards.py::test_no_undo_on_shared_monkeypatch_fixture and ::test_session_sandbox_seal_is_not_first_test fail identically on the clean base tree (verified via git stash); no_undo already has KNOWN witness 0ea4d12896bf1d703ba1b18ecdb64ea3 cited in sase-1rd.1 notes

[2026-11-05T15:05:37Z · sase-1rd.2] PROPOSED FOLLOW-UP: FLAKY-triaged failures outside the trash_callers diff need owners — test_tracked_marker_path_passing_sites_are_reviewed (extra sites all in untouched src/sase/agent/hijack/recover_*.py) and test_app_export_body_tolerates_signal_task_prepare_error (untouched TUI screenshot path)

[2026-11-05T15:06:00Z · sase-1rd.2] trash_callers done and verified: pin ratcheted 542448a0->39744416; facade agent_artifact_run_trash.py (quarantine/list/restore/purge with deindex/reindex reporting); review module (verbatim fingerprint, atomic snapshots with newest-8 GC, RunPruneReview payload schema 1 with never-raising parser); prune-runs --apply quarantines with --snapshot intersection and --notify result+preview-retire, envelope schema 2, exits 0/1/2, typed artifact.prune-runs result; trash list/restore runs:/purge run batches with fresh protections; schema mirrored in tools/validate_sase_core_rs with tests; footprint+completion catalogs and CLI docs regenerated; 2 reference pages updated. just check: all 19 lint gates green (incl. mypy+symvision), scoped lane 60113 passed; remaining failures are KNOWN/FLAKY or reproduce identically on clean base (recorded as PROPOSED FOLLOW-UP notes). 25 focused tests green. 8 epic-symbol rows keyed to still-open sase-1rd.3/sase-1rd.4.

## Dependencies

- **Depends on:** [sase-1rd.1](sase-1rd.1.md) ✓ · ⧖ 2026-11-05
- **Blocks:** [sase-1rd.3](sase-1rd.3.md) ✓ · ⧖ 2026-11-05
- **Blocks:** [sase-1rd.4](sase-1rd.4.md) ✓ · ⧖ 2026-11-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rd.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rd.2.md) | [sase-1rd.2](sase-1rd.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`37a4c8e`](https://github.com/sase-org/sase/commit/37a4c8ed8d2b30942697494d1624532a63434460) | feat(artifact): quarantine ACE runs to restorable trash with review snapshots | [sase-1rd.2](sase-1rd.2.md) | 2026-11-05 10:14:11 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1qz.6.1.4.1.3][1] | Identify the phase that implemented the symbols rejected by symvision | 1 |
| read-by | [agent:sase-1rd.2--1][2] | Need phase scope | 1 |
| read-by | [agent:sase-1rd.3][3] | Check whether the phase's earlier check already records the unrelated test failure before making a duplicate proposal | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.6.1.4.1.3/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rd.2.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rd.3/README.md

<!-- sase:referenced-by:end -->
