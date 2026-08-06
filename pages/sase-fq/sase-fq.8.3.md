# Bead: sase-fq.8.3 — Close out epic sase-fq

[Bead Pages](../README.md) / [sase-fq.8](sase-fq.8.md) / sase-fq.8.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-fq.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fq.land/README.md) · **Assignee:** `sase-fq.8.3` · **Size:** small
**Created:** 2026-08-06 07:05:18 EDT · **Closed:** 2026-08-06 12:08:18 EDT
**Plan:** [202608/artifact\_ref\_scratch\_failure.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_ref_scratch_failure.md)

## Description

land-fq: confirm every sase CI job is green on master, close epic sase-fq with a verification note, run just symvision, and mark both plan files done.

## Notes

[2026-08-06T16:04:08Z · sase-fq.8.3] PROPOSED FOLLOW-UP: corroborate open bead sase-fs with a second occurrence — master CI run 31114984919 (sha 7cbfc3449), job "test (3.12)" coverage leg, failed 27 tests, 26 of them "NameError: name 'sase_core_rs' is not defined" raised from .venv/lib/python3.12/site-packages/sase_core_rs/__init__.py:3, plus one downstream "assert False is True". Same signature as sase-fs, again only on the 3.12 coverage leg, now with sase_core_rs 0.18.4 rather than 0.18.2, so the unbound-submodule failure is not specific to one wheel version. This is a +1 on sase-fs, not a new task.

[2026-08-06T16:04:16Z · sase-fq.8.3] PROPOSED FOLLOW-UP: new member of the sase-ct ACE TUI parallel-flake class — tests/ace/tui/test_app_title.py::test_on_mount_refines_title_to_resolved_version failed on master CI run 31114984919, job "test (3.13)", with AssertionError: assert 'sase ace (v0.15.0)' == 'sase ace (v0.15.0+9.gdeadbee.dirty)'. The test monkeypatches resolved_app_version and then awaits a single pilot.pause(); the title refinement runs off-thread in on_mount, so under full-parallel load the refinement has not landed when the assertion runs. It passes in isolation and on the 3.12/3.14 legs of the same run. Suggested fix: wait for the refinement instead of a bare pause. This is a +1 on sase-ct, not a new task.

[2026-08-06T16:04:26Z · sase-fq.8.3] PROPOSED FOLLOW-UP: CI has no retry for GitHub Actions platform failures in "Set up job" — on run 31114984919 published-core-minimum-smoke, perf-floors and coverage-contexts each failed with zero steps executed, annotated "Failed to resolve action download info" and "Service Unavailable"; run 31113753459 lost build-core (and therefore every dependent lane) the same way. A whole master run reads as red with no code signal at all, which is exactly what made this epic hard to land. Worth deciding whether these jobs should retry the setup step or whether the run summary should distinguish platform failures from test failures.

[2026-08-06T16:04:34Z · sase-fq.8.3] PROPOSED FOLLOW-UP: an SDD land phase cannot execute "close the parent epic" from inside that epic. This plan gave phase land-fq (sase-fq.8.3) the deliverable "close epic sase-fq", but sase-fq has an in_progress child epic sase-fq.8 whose own land agent owns closing it, so a non-forced close is rejected by the parent-close descendant guard, and phase workers are told by their launch prompt not to close a parent epic. The plan even anticipates rejection ("If it is rejected, a phase bead is still open — finish or reopen it instead"), which is circular when the still-open phase is the one attempting the close. Either the plan template should route an epic close to the land agent one level up, or `sase bead close` should offer a "close once my own phase closes" handoff.

[2026-08-06T16:08:18Z · sase-fq.8.3] land-fq done, with one deliverable deliberately left to sase-fq.8's land agent.

CI CONFIRMATION (the epic's R6 gate): master CI run 31114984919, sha 7cbfc3449. All three test legs ran the full suite to completion — test (3.14) 25994 passed / 0 failed, test (3.13) 25993 passed / 1 failed, test (3.12) coverage leg 25967 passed / 27 failed. test_commit_completion_rows_match_shared_inventory_and_resolve is absent from every failure summary, and the string "artifact-ref commit inventory" (the sase-fq.6 CommitLogFailure stderr diagnostic and the sase-fq.8.1 probe, both of which only fire on an empty inventory) appears zero times across all three job logs. First master run since 9672c5602 where the parity test passes on every leg. build-core, lint and visual-test green on the same run. Locally reproduced the fix on 7cbfc3449 too: the exact poisoning order from sase-fq.8.2 (test_prepare_pytest_tmpdir_honors_override then the parity test, -p no:randomly) passes 2/2, and all six run_pytest modules + the leak-regression test + the artifact-ref catalog pass together (70 passed). Full evidence is recorded as an R6 VERIFICATION note on sase-fq.

NOT EVERY JOB IS GREEN, and none of the red is this epic's. published-core-minimum-smoke, perf-floors and coverage-contexts failed with zero steps executed in "Set up job" ("Failed to resolve action download info", "Service Unavailable"); the next run 31116699976 lost build-core the same way with "The job was not acquired by Runner of type hosted even after multiple attempts", which skipped every dependent lane. That is a GitHub Actions hosted-runner incident, not repo code. test (3.12)'s 27 failures are 26 sase_core_rs unbound-submodule NameErrors from site-packages/sase_core_rs/__init__.py:3 plus one downstream assertion — open bead sase-fs, second occurrence, now on 0.18.4 as well as 0.18.2. test (3.13)'s single failure is tests/ace/tui/test_app_title.py::test_on_mount_refines_title_to_resolved_version, an off-thread title refinement racing one pilot.pause() under parallel load — the sase-ct flake class. Both are out of scope per the epic plan.

just symvision: clean at 7cbfc3449 ("All public/private classes/functions are used properly!", exit 0). grep across the tree finds no sase-fq epic-symbol whitelist entries, exactly as the plan predicted, so nothing to remove.

PLAN FILES: status: wip -> done in both plans:202608/ci_master_red_recovery.md and plans:202608/artifact_ref_scratch_failure.md, both re-validated with sase plan validate (valid epic plan, 0 warnings), committed and pushed to sase--plans as 63a1a4fc.

EPIC sase-fq IS NOT CLOSED BY ME, on purpose. It still has an in_progress child epic sase-fq.8, so a non-forced close is rejected by the parent-close descendant guard, the plan forbids forcing it, and a phase worker must not close a parent epic. sase-fq.8's land agent should close sase-fq immediately after closing sase-fq.8; the R6 VERIFICATION note on sase-fq is the record it needs. Four PROPOSED FOLLOW-UP entries are on this bead: +1 sase-fs, +1 sase-ct, no CI retry for Actions platform "Set up job" failures, and the plan-authoring flaw that made this phase unable to execute its own headline deliverable.

No sase-repo source changed in this phase, so the workspace tree is clean and just check was not applicable.

## Dependencies

- **Depends on:** [sase-fq.8.2](sase-fq.8.2.md) ✓ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fq.8.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fq.8.3/README.md) | [sase-fq.8.3](sase-fq.8.3.md) | 0 |
