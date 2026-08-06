# Bead: sase-fq.8.2 — Fix the identified scratch-file failure at its source

[Bead Pages](../README.md) / [sase-fq.8](sase-fq.8.md) / sase-fq.8.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-fq.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fq.land/README.md) · **Assignee:** `sase-fq.8.2` · **Size:** medium
**Created:** 2026-08-06 07:05:12 EDT · **Closed:** 2026-08-06 11:08:42 EDT
**Plan:** [202608/artifact\_ref\_scratch\_failure.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_ref_scratch_failure.md)

## Previously Closed

> ↺ Closed 2026-08-06T11:45:32Z · done
>
> (none)
>
> Reopened 2026-08-06T11:48:40Z by `sase bead open`

## Description

scratch-fix: fix the cause scratch-probe identified, carry the underlying io::Error into sase-core's commit-inventory diagnostic, and confirm the parity test passes on master CI.

## Notes

[2026-08-06T11:49:32Z · sase-fq.8.2] REOPENED: the commit workflow auto-closed this phase when the sase-core diagnostic commit landed (sase-core 7b28c3e), but the phase still owes the root-cause fix, the sase-core-rs floor bump, and CI confirmation of the parity test.

[2026-08-06T13:04:20Z · tw] Root cause found and fixed: not EMFILE/ENOSPC/O_TMPFILE (all ruled out by the sase-fq.8.1 probe on CI run 31097887770). The empty commit inventory was caused by test pollution, not a resource limit or a bad TMPDIR. tests/test_run_pytest_tmpdir.py::test_prepare_pytest_tmpdir_honors_override called the real _prepare_pytest_tmpdir(), which writes TMPDIR and SASE_PYTEST_TMP_REDIRECTED directly to os.environ (tools/run_pytest:405-407). The test only monkeypatched SASE_PYTEST_TMPDIR, not those two vars, so both writes survived teardown for the rest of that xdist worker's session. pyproject.toml's tmp_path_retention_policy="failed" then deleted the passing test's tmp_path, leaving TMPDIR pointing at a directory that no longer existed. Python-side checks never noticed because tempfile.gettempdir() caches its answer on first use; only non-Python code that re-reads $TMPDIR fresh -- sase-core's tempfile::tempfile() -- hit ENOENT, which commit_log_output discarded into a guessed 'check TMPDIR' message. The parent epic plan's 'What is already ruled out' section is wrong on this point: it ruled out a bad TMPDIR because 'no conftest fixture rewrites or deletes it' -- true, but irrelevant, since a TEST rewrote it and monkeypatch only restores variables it set itself. Fixed in sase-fq.8.2 by routing both env vars through monkeypatch.setenv() in the offending test, adding a per-test guard (tests/_tmp_leak_guard.py) that fails any test leaving TMPDIR/SASE_PYTEST_TMP_REDIRECTED changed after its own teardown, and adding a pytester-based ordering regression test (tests/test_scratch_tmpdir_leak_regression.py) that pins the fix at the sequencing level.

[2026-08-06T13:47:52Z · tw.f1] Correction: the 2026-08-06T13:04:20Z note's "Fixed in sase-fq.8.2" claim was half true. The mechanism was correctly identified, but the fix (commit e0acf80, PR #278) only routed the two env-var writes through monkeypatch in the ONE test that called _prepare_pytest_tmpdir() directly. The actual shared source is main() itself: any of the ten other tests across test_run_pytest_scoped.py, test_run_pytest_main.py, and test_run_pytest_health.py that drive main() far enough to reach _prepare_pytest_tmpdir()/_sanitize_pytest_environment() leaked the same way, unguarded. CI run 31104590294 confirmed the parity test (test_commit_completion_rows_match_shared_inventory_and_resolve) was STILL failing after e0acf80 landed, for exactly the original reason, when paired with any of those ten. Follow-up plan sase/repos/plans/202608/run_pytest_main_env_leaks.md closed the gap: an autouse isolate_run_pytest_environment fixture now pins every process global main() writes (TMPDIR, SASE_PYTEST_TMP_REDIRECTED, and the four PYTEST_ENV_UNSET_KEYS) across all six test_run_pytest_*.py modules, and check_tmp_env_leak_guard() now restores the baseline before failing so one leak can no longer cascade into an unrelated test's failure.

[2026-08-06T13:49:07Z · tw.f1] sase-core-rs 0.18.4 adoption (plan step 4, sase/repos/plans/202608/run_pytest_main_env_leaks.md) remains blocked: sase-core PR #88 (chore: release v0.18.4) merged 2026-08-06T13:40:54Z, but its Release-plz publish workflow was still in_progress and PyPI's latest sase-core-rs was still 0.18.3 as of this check. Not unblocking by merging/publishing myself, per the plan -- that is a cross-repo release action for the project owner. pyproject.toml's floor stays at sase-core-rs>=0.18.3,<0.19.0 until it publishes.

## Dependencies

- **Depends on:** [sase-fq.8.1](sase-fq.8.1.md) ✓ · ⧖ 2026-08-06
- **Blocks:** [sase-fq.8.3](sase-fq.8.3.md) ✓ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fq.8.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fq.8.2/README.md) | [sase-fq.8.2](sase-fq.8.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@7b28c3e`](https://github.com/sase-org/sase-core/commit/7b28c3e16f865cfead2b8265ecd69fd30b01c772) | fix(editor): report the OS error behind a dropped commit-log repository | [sase-fq.8.2](sase-fq.8.2.md) | 2026-08-06 07:46:55 EDT |
