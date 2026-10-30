# Bead: sase-1pu.4 — Remove the full-check timeout for the empty-home SDD identity test (sase-120)

[Bead Pages](../README.md) / [sase-1pu](README.md) / sase-1pu.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pn.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pn.land.md) · **Assignee:** `sase-1pu.4` · **Size:** large
**Created:** 2026-10-29 19:19:01 EDT
**Plan:** [202610/task\_backlog\_epic\_3.md](https://github.com/sase-org/sase--plans/blob/main/202610/task_backlog_epic_3.md)

## Description

sdd-identity-check-flake: reproduce the repeated full-lane timeout and passing isolated run for test_sdd_git_identity_survives_empty_home_subprocess. Determine whether the nested subprocess or the temporary-directory leak guard causes the slow/failing result, then fix isolation or cleanup without weakening the test or simply extending its timeout. Verify the node, its file, and the scoped/full check.

## Notes

[2026-10-30T01:13:14Z · sase-1pu.4] WIP: isolated nested empty-home identity pytest with --basetemp plus private TMPDIR/TEMP/TMP/PYTEST_DEBUG_TEMPROOT under outer tmp_path. Leak-guard exemption stays child-local. Deterministic regression seeds inherited pytest-0 markers (plus pytest-1 keep-count decoy) for both TMPDIR and PYTEST_DEBUG_TEMPROOT; markers survive and child writes under its own basetemp. Negative control without isolation deleted pytest-0. Unchanged-tree timeout did not reproduce in isolation (node 7.02s, file 5.31s). After fix: node 5.38s; file 6.37s; just test file 3 passed in 10.11s (nested call 4.18s). just fix clean. sase tool run check 03356c5f189dd06b6387ec842f5d0e4d passed (scoped 3m18s, no full-lane escalation). Remaining: full governed just test for load/cleanup acceptance, then TASK RESOLVED + close sase-1pu.4 only.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pu.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pu.4.md) | [sase-1pu.4](sase-1pu.4.md) | 0 |
