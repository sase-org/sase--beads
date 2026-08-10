# Bead: sase-i8.10.2 — Give each remote-fixture test its own origin repository

[Bead Pages](../README.md) / [sase-i8.10](sase-i8.10.md) / sase-i8.10.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-i8.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i8.land/README.md) · **Assignee:** `sase-i8.10.2` · **Size:** small
**Created:** 2026-08-10 08:26:27 EDT · **Closed:** 2026-08-10 09:34:16 EDT
**Plan:** [202608/merge\_visibility\_dispatch\_fix.md](https://github.com/sase-org/sase--plans/blob/main/202608/merge_visibility_dispatch_fix.md)

## Description

isolation: remove the shared bare-remote path that makes two provider tests collide inside one pytest worker, which is the reproducible flake recorded three times against this epic.

## Notes

[2026-08-10T13:33:41Z · sase-i8.10.2] PROPOSED FOLLOW-UP: just check/just check-full committed-plans gate fails repo-wide on sase/repos/plans/202608/new_task_recent_task_sweep.md:1 (tale-size-missing: required `size` field absent). Confirmed pre-existing on master via `git stash` before this change — unrelated to phase isolation, but currently blocks the committed-plans step for every agent in every workspace before it can reach the test-scoped lane.

[2026-08-10T13:34:16Z · sase-i8.10.2] Fixed the shared-remote collision: added a remote_repo fixture (tests/test_vcs_provider_vcs_log.py) that derives a unique bare-remote path from the repo fixture's own tmp_path directory name instead of the literal Path(repo).parent/'origin.git', and applied it to both test_vcs_partition_commits_honors_merge_visibility_modes and test_remote_log_ops_fetch_partition_and_union_log (also uniquified that second test's remote_work clone dir the same way). Grepped tests/ tree for other Path(...).parent scratch-location traps; the only other .parent-derived sibling paths shared by multiple tests in one file are intentionally-nonexistent remotes (missing.git) used to simulate an unreachable remote, so no other file has this bug. Verified: (1) all 28 tests in the file pass together via '.venv/bin/python -m pytest tests/test_vcs_provider_vcs_log.py -p no:randomly -q'; (2) the two previously-colliding tests run together 5x in each order, all green; (3) constructed the deliberate failing interleaving from the plan directly against git (root commit + push to the shared literal origin.git path, 1.1s delay, second push) -- reproduces the exact non-fast-forward rejection on the old path scheme every time, and confirmed the new per-repo-derived path scheme never collides under the same delay. just check's lint gates (fmt, ruff, mypy, pyscripts, test-waits, changelog, patch/stitch terminology, symvision, toobig, SASE validation) all pass on this change. just check's committed-plans gate fails, but reproduces identically on master via git stash, so it's pre-existing/unrelated (filed as PROPOSED FOLLOW-UP note on this bead). The live just test-scoped run did not finish in-session -- host load spiked to 15-27 from concurrent agents/workspaces and the run was still going after 49 minutes with far less CPU time accumulated than wall clock implied, so it was stopped; this is host contention, not a code issue. tools/selection_health --fail-on-new-flake still lists test_remote_log_ops_fetch_partition_and_union_log because the reproducible-flake classifier keys off historical full-lane records that predate this fix (by design it requires both a failing and a passing full run on the node); this will clear once fresh full-lane runs after this fix land.

[2026-08-10T13:35:35Z · sase-i8.10.2] Fixed shared bare-remote path collision in tests/test_vcs_provider_vcs_log.py: added a remote_repo fixture deriving a unique remote path from the repo fixture's own tmp_path dir name, used by both test_vcs_partition_commits_honors_merge_visibility_modes and test_remote_log_ops_fetch_partition_and_union_log (also uniquified the latter's remote_work clone dir). Verified: all 28 tests in the file pass together and in both orders, repeatedly; reconstructed the exact failing interleaving from the plan (root commits ~1.1s apart racing to push to the old shared literal path) and confirmed it reproduces the non-fast-forward rejection on the old code every time and never collides on the new code. Lint gates pass. just check's committed-plans gate and a live just test-scoped run were blocked/slow for reasons unrelated to this change (pre-existing broken plan file on master; heavy host contention from concurrent agents); the unrelated plan-file breakage is recorded as a PROPOSED FOLLOW-UP on this bead.

## Dependencies

- **Blocks:** [sase-i8.10.3](sase-i8.10.3.md) ✓ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-i8.10.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i8.10.2/README.md) | [sase-i8.10.2](sase-i8.10.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e9e414e`](https://github.com/sase-org/sase/commit/e9e414e2f5a55ba3a79e1b5cd0239e1749d51792) | test(vcs-log): give each remote-fixture test its own bare origin path | [sase-i8.10.2](sase-i8.10.2.md) | 2026-08-10 09:38:06 EDT |
