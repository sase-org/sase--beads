# Bead: sase-1pu.4 — Remove the full-check timeout for the empty-home SDD identity test (sase-120)

[Bead Pages](../README.md) / [sase-1pu](README.md) / sase-1pu.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pn.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pn.land.md) · **Assignee:** `sase-1pu.4` · **Size:** large
**Created:** 2026-10-29 19:19:01 EDT · **Closed:** 2026-10-29 22:22:53 EDT
**Plan:** [202610/task\_backlog\_epic\_3.md](https://github.com/sase-org/sase--plans/blob/main/202610/task_backlog_epic_3.md)

## Description

sdd-identity-check-flake: reproduce the repeated full-lane timeout and passing isolated run for test_sdd_git_identity_survives_empty_home_subprocess. Determine whether the nested subprocess or the temporary-directory leak guard causes the slow/failing result, then fix isolation or cleanup without weakening the test or simply extending its timeout. Verify the node, its file, and the scoped/full check.

## Notes

[2026-10-30T01:13:14Z · sase-1pu.4] WIP: isolated nested empty-home identity pytest with --basetemp plus private TMPDIR/TEMP/TMP/PYTEST_DEBUG_TEMPROOT under outer tmp_path. Leak-guard exemption stays child-local. Deterministic regression seeds inherited pytest-0 markers (plus pytest-1 keep-count decoy) for both TMPDIR and PYTEST_DEBUG_TEMPROOT; markers survive and child writes under its own basetemp. Negative control without isolation deleted pytest-0. Unchanged-tree timeout did not reproduce in isolation (node 7.02s, file 5.31s). After fix: node 5.38s; file 6.37s; just test file 3 passed in 10.11s (nested call 4.18s). just fix clean. sase tool run check 03356c5f189dd06b6387ec842f5d0e4d passed (scoped 3m18s, no full-lane escalation). Remaining: full governed just test for load/cleanup acceptance, then TASK RESOLVED + close sase-1pu.4 only.

[2026-10-30T02:22:38Z · sase-1pu.4--1] PROPOSED FOLLOW-UP: tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection failed the full governed just test (ToolRun 18fbb90be9fd777694a5cb231986b4dd, 58964 passed / 1 failed). Identical failure on clean HEAD 9664ed3c20 with the identity isolation change stashed: committed tests/contract_manifest.txt lists tests/test_core_finalizer_handoff.py, which carries no pytest.mark.contract, so marker collection omits it. Already recorded on closed sibling sase-1pu.3 note #1 and as DISCOVERED ISSUE on sase-1pj.2.1 / sase-1pi. Re-mark the file or run just refresh-contract-manifest. No new task bead.

[2026-10-30T02:22:45Z · sase-1pu.4--1] TASK RESOLVED: sase-120 — Nested empty-home identity pytest inherited TMPDIR/PYTEST_DEBUG_TEMPROOT and had no --basetemp, so pytest numbered-directory cleanup of pytest-* under the shared temp root ran at child shutdown under load. Historical TimeoutExpired: ToolRun e996bbfb6e8d632139c7686cc9268d44 at 180s. Unchanged-tree isolation did not reproduce (node 7.02s, file 5.31s). Fix: nested child gets --basetemp under a dedicated dir on outer tmp_path plus private TMPDIR/TEMP/TMP/PYTEST_DEBUG_TEMPROOT; parent os.environ is not mutated; leak-guard exemption stays child-local. Regression seeds inherited pytest-0 markers (plus pytest-1 keep-count decoys) for TMPDIR and PYTEST_DEBUG_TEMPROOT; markers survive and the child writes under nested-pytest-basetemp. After fix: node 5.38s; file 6.37s; just test tests/sdd/test_git_identity_fixture.py 3 passed in 10.11s (nested child 4.18s, returncode 0, no TimeoutExpired). sase tool run check 03356c5f189dd06b6387ec842f5d0e4d passed (scoped 3m18s, no full-lane escalation). Full governed just test ToolRun 18fbb90be9fd777694a5cb231986b4dd: identity node present in pytest nodeids and absent from lastfailed (child returncode 0, identity assertions held); suite 58964 passed / 1 failed (unrelated stale contract_manifest, recorded as follow-up).

[2026-10-30T02:22:53Z · sase-1pu.4--1] Nested empty-home SDD identity pytest isolated with --basetemp plus private TMPDIR/TEMP/TMP/PYTEST_DEBUG_TEMPROOT under outer tmp_path. Identity node passed as a child process (returncode 0, no TimeoutExpired) in focused, file, scoped check 03356c5f189dd06b6387ec842f5d0e4d, and full just test 18fbb90be9fd777694a5cb231986b4dd. TASK RESOLVED sase-120 recorded; pre-existing clean-base contract_manifest stale-manifest failure recorded as PROPOSED FOLLOW-UP. No epic-symbol entries. Did not close sase-120 or sase-1pu.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pu.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pu.4.md) | [sase-1pu.4](sase-1pu.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5437e0b`](https://github.com/sase-org/sase/commit/5437e0baaa60ab862ac7810a79ab776d74e3a93f) | test(sdd): isolate empty-home git identity nested pytest | [sase-1pu.4](sase-1pu.4.md) | 2026-10-29 22:24:48 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pu.4--1][1] | Need phase bead state, notes, and TASK RESOLVED format before closing or recording follow-up | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pu.4.md

<!-- sase:referenced-by:end -->
