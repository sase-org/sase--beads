# Bead: sase-fq.4 — Stop the real-uv harness leaking lock files into the watched temp root

[Bead Pages](../README.md) / [sase-fq](README.md) / sase-fq.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tq](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tq/README.md) · **Assignee:** `sase-fq.4` · **Size:** small
**Created:** 2026-08-05 21:05:56 EDT · **Closed:** 2026-08-05 21:31:54 EDT
**Plan:** [202608/ci\_master\_red\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202608/ci_master_red_recovery.md)

## Description

uv-harness-tmpdir: give the uv_env fixture its own TMPDIR under tmp_path so real uv subprocesses stop dropping uv-setuptools-*.lock into the managed SASE temp root and tripping the session temp-leak guard.

## Notes

[2026-08-06T01:31:54Z · sase-fq.4] Gave the uv_env fixture its own TMPDIR under tmp_path (tests/uv_tool/test_real_uv_harness.py) so real uv subprocesses stop dropping uv-setuptools-*.lock into the managed SASE temp root. Verified: just test-slow now finishes clean (10 passed, 2 skipped) with no system temp leakage section. just check still fails, but only on the pre-existing symvision R3 finding (progress_fingerprint in commit_finalizer_git.py), which is out of scope for this phase and owned by sase-fq.2.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fq.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fq.4/README.md) | [sase-fq.4](sase-fq.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6ee11e5`](https://github.com/sase-org/sase/commit/6ee11e5e9df5f47b1233ca34ed49f0a1989c323e) | fix(tests): stop real-uv harness leaking lock files into watched temp root | [sase-fq.4](sase-fq.4.md) | 2026-08-05 21:32:42 EDT |
