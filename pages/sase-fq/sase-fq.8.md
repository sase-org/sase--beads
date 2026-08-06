# Bead: sase-fq.8 — Fix the artifact-ref commit inventory's scratch-file failure and finish landing sase-fq

[Bead Pages](../README.md) / [sase-fq](README.md) / sase-fq.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-fq.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fq.land/README.md) · **Assignee:** `sase-fq.8.land`
**Created:** 2026-08-06 07:05:00 EDT · **Closed:** 2026-08-06 12:24:31 EDT
**Plan:** [202608/artifact\_ref\_scratch\_failure.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_ref_scratch_failure.md)

## Description

The artifact-ref commit inventory stops returning an empty result on GitHub runners, the failure is fixed at the cause the runtime diagnostic actually names rather than at the budget hypothesis that was already disproved, every job in the sase CI workflow passes on master, and epic sase-fq is closed out.

## Notes

[2026-08-06T16:24:31Z · sase-fq.8.land] LAND VERIFICATION (sase-fq.8.land, 2026-08-06). Epic goal met: the artifact-ref commit inventory no longer returns empty on CI runners, the cause was fixed where the runtime diagnostic pointed, and the last known blocker on sase-fq is cleared.

VERIFIED IN SOURCE, not just from phase notes.
- sase-fq.8.1 (scratch-probe): tests/_scratch_resource_probe.py exists and reports TMPDIR + permissions, statvfs free blocks/inodes, RLIMIT_NOFILE, open-fd count and an fd-target histogram, plus live tempfile.TemporaryFile() and os.dup() attempts with errno. tests/ace/tui/widgets/test_artifact_ref_completion_catalog.py:317-325 prints it and attaches it to the assertion message when either inventory is empty; the parity assertion itself is unchanged, as the standing constraint required. Landed via PR #278 (commit be25ef5b4).
- sase-fq.8.2 (scratch-fix): the root cause was test pollution, not resource exhaustion -- eleven in-process tests drove tools/run_pytest's main(), which writes TMPDIR and SASE_PYTEST_TMP_REDIRECTED straight to os.environ, without pinning them first. The fix is present and complete: tests/_run_pytest_fixtures.py:40-56 defines the autouse isolate_run_pytest_environment fixture using the set-then-delete registration the plan specified, and pins all six env vars plus the CWD; all six test_run_pytest_*.py modules import it (verified by grep, one '# noqa: F401' import each). tests/_tmp_leak_guard.py:242-282 now restores the baseline before pytest.fail(), and its message says so, so a leak is contained at its own offender instead of cascading. tests/test_scratch_tmpdir_leak_regression.py pins the ordering fix and now includes a main()-driven offender.
- sase-fq.8.2's sase-core half is landed and adopted: crates/sase_core/src/editor/completion.rs now carries CommitLogIoCause (kind + raw_os_error) and a ScratchStep discriminator into every Scratch/Spawn/Wait/Read message, so 'could not create a scratch file ... under TMPDIR: Too many open files (os error 24)' replaces the old guessed 'check that TMPDIR exists and is writable'. Plan step 4 of plans:202608/run_pytest_main_env_leaks.md was blocked on the 0.18.4 publish at the time; it has since unblocked and is DONE -- pyproject.toml:46 is 'sase-core-rs>=0.18.4,<0.19.0', uv.lock resolves 0.18.4, and tests/test_sase_core_rs_telemetry_smoke_tool.py:35 asserts the declared minimum is 0.18.4. The bump rode in on d9c13549f (epic sase-g4) rather than on this epic's own commit.
- Every child note reviewed, including sase-fq.8.2's own 13:47:52Z correction that e0acf80 fixed 1 of 11 tests. That correction is what the final state reflects: I re-ran the plan's own reproductions at HEAD and they are clean.

REPRODUCED THE FIX LOCALLY at b694c00c1: 'uv run pytest -p no:randomly tests/test_run_pytest_*.py' -> 64 passed, 0 errors (was '30 passed, 10 errors' before the fixture). The epic's parity test paired with a main()-driven neighbour ('test_scoped_run_lands_in_the_durable_health_store' then 'test_commit_completion_rows_match_shared_inventory_and_resolve', -p no:randomly) -> 2 passed (was 1 failed, 1 passed, 1 error). The guard, regression and probe suites -> 11 passed. 'just check' green, and because rebuilding sase-core tripped core-identity-changed it escalated to the FULL suite, so the whole suite passed at HEAD with my integration edits applied.

CI EVIDENCE for R6 is sase-fq.8.3's run 31114984919 (sha 7cbfc3449), independently re-read from the job logs: test (3.14) 25994 passed / 0 failed, test (3.13) 25993 passed / 1 failed, test (3.12) coverage leg 25967 passed / 27 failed. test_commit_completion_rows_match_shared_inventory_and_resolve appears in no failure summary on any leg, and no 'left TMPDIR ... changed after its own teardown' error appears either -- the plan's exit criterion, on all three legs. I could NOT obtain a second independent CI confirmation at HEAD: master runs 31116699976 and 31118652934 were both lost to a GitHub hosted-runner incident before any repo step ran (see sase-ge). The full local suite run above is the substitute.

INTEGRATION (step 2). Reviewed all 20 commits on master since this epic was created (2026-08-06 07:05 EDT) against the epic's own commit be25ef5b4. Nothing has touched tests/_run_pytest_fixtures.py, tests/_tmp_leak_guard.py, tests/conftest.py, tests/test_run_pytest_*.py, tests/test_scratch_tmpdir_leak_regression.py, tests/_scratch_resource_probe.py or the catalog test since. No new test module drives tools/run_pytest's main() (grep for load_run_pytest finds only the six modules, all of which import the fixture), and the only direct os.environ['TMPDIR'] writes left in tests/ are the leak guard's own deliberate offenders. All six run_pytest modules are in tests/contract_manifest.txt, so the diff-scoped lane always selects them.

ONE REAL INTEGRATION CHANGE MADE, uncommitted in the workspace tree for the commit finalizer: this epic's own sase-core change reached the sase repo through d9c13549f's floor bump, which falsified three sase-side comments that still described the pre-0.18.4 diagnostic as discarding the errno and guessing at TMPDIR. Corrected tests/_scratch_resource_probe.py's module docstring (the message now names step + errno; the probe's remaining value is the resource state only the failing process can see), tests/ace/tui/widgets/test_artifact_ref_scratch_probe.py's module docstring and its EMFILE comment, and the catalog test's empty-inventory comment. Comments only, no behavior change; 'just check' (escalated to the full suite) is green with them.

FOLLOW-UP DISPOSITION -- all four PROPOSED FOLLOW-UP entries on sase-fq.8.3 processed through /sase_new_task, each independently re-verified from the job logs first:
1. sase_core_rs unbound-submodule NameErrors -> +1 on existing task sase-fs (duplicate, same root cause). Added what the second occurrence proves: the wheel version is not the variable (0.18.4 here vs 0.18.2 originally, install line quoted), still only the 3.12 coverage leg, 26 NameErrors + 1 downstream assertion out of 27 failures.
2. test_app_title.py::test_on_mount_refines_title_to_resolved_version -> +1 on existing task sase-ct (now +18). Same root cause as that bead's class (a single pilot.pause() standing in for real async work); recorded the specific mechanism -- off-thread title refinement racing the pause -- and the suggested fix.
3. No CI retry or distinct reporting for Actions platform 'Set up job' failures -> NEW task sase-ge (small, ready). No semantic duplicate existed; sase-fv is about correlating CI failures with selection manifests, not about platform failures. Scoped as a decision between a bounded retry of setup-phase failures and making the redness legible, pinned in tests/test_github_actions_ci.py. Noted the third occurrence observed live today.
4. A land phase cannot close its own parent epic -> NEW task sase-gf (small, ready). Verified all three blocking mechanisms in the actual sources (the descendant-close guard, the bd/work_phase_bead prohibition, and the fact that only bd/land_epic at src/sase/default_config.yml:950 carries the close instruction), and verified four real recurrences in bead notes across sase-fq.8.3, sase-fr.9.3, sase-fp.8.3 and sase-bd.9.5. Confirmed src/sase/xprompts/skills/sase_plan.md says nothing about the land agent, which is the authoring gap. Nothing declined.

Neither new task is caused by this epic, and both out-of-scope items (sase-ct, sase-fs) were already excluded by the epic plan. Both plan files (plans:202608/artifact_ref_scratch_failure.md and plans:202608/ci_master_red_recovery.md) are already status: done, committed to sase--plans as 63a1a4fc.

[2026-08-06T16:27:06Z · sase-fq.8.land] Land verification re-confirmed: epic already closed at 2026-08-06T16:24:31Z; re-running close to verify the close was published, not local-only.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fq.8.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fq.8.land/README.md) | [sase-fq.8](sase-fq.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a15f409`](https://github.com/sase-org/sase/commit/a15f409dd11322a32649c627e226a0fd448c9070) | docs(artifact-ref): describe the scratch probe against sase-core 0.18.4 | [sase-fq.8](sase-fq.8.md) | 2026-08-06 12:27:50 EDT |
