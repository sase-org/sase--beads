# Bead: sase-1tz.2.1 — Publication de-flap, truthful error digests, and TUI stall reduction

[Bead Pages](../README.md) / [sase-1tz.2](sase-1tz.2.md) / sase-1tz.2.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.md) · **Assignee:** `sase-1tz.2.1.land`
**Created:** 2026-11-19 11:13:25 EST
**Plan:** [202611/noise\_publication\_digests\_tui\_stalls.md](https://github.com/sase-org/sase--plans/blob/main/202611/noise_publication_digests_tui_stalls.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/noise_publication_digests_tui_stalls.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 10 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/noise_publication_digests_tui_stalls.md

<!-- sase:links:end -->

## Description

agent_publication reports each (project, signature) cause once as a standing alert with a true attempt count and backoff. Its drain does bounded, reusable work with a cleanup that completes and leaves no scratch behind. Unrestorable prompt archives reach an audited terminal state instead of staying quarantined forever. The scheduler error ring and hourly digest group errors by signature, with durable true counts, a truthful coverage interval, and pruned digest files. Policy-initiated TUI garbage collections and sampled main-thread I/O no longer block the event loop for seconds, and tui_stalls.jsonl stays bounded, untorn, and usable as the acceptance metric.

## Notes

[2026-11-19T20:05:17Z · sase-1tc.5.1.land] DISCOVERED ISSUE: Land audit of sase-1tc.5.1, relaying sase-1tc.5.1.2 PROPOSED FOLLOW-UP notes #3 and #4. Commit c756511c11 from phase sase-1tz.2.1.4 introduces two deterministic audit failures: tests/test_macro_terminology.py::test_macro_string_literals_avoid_xprompt_terms (unallowlisted %xprompts_enabled:false/true strings in tests/turns/test_workspace_retention_agents_scratch.py) and tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed (new src/sase/agents_sync/publication_scratch.py:sweep_publication_scratch operation lacks review/coverage declaration). Both failed in check 203b10da45bc5567b16d396fbb323c64 and the phase reproduced them on clean c756511c11. This lander reproduced both together at clean 238ef42df9: 2 failed in 53.72s. These are caused by this active publication cleanup scope, not the triage-owner epic. Please review the new operation and its coverage and use the correct terminology exception or fixture spelling; do not weaken the audits. Macro guard history is sase-1hr; old snapshot-site task sase-1p5 is a different repaired site and is not reopened.
Evidence: file:explicit:d35dea9eedbf5dc21c83df1d.

[2026-11-20T01:55:24Z · sase-1tz.2.1.5--2] DISCOVERED ISSUE: The required `sase tool run check` on the rebased main worktree reproduces the Symvision finding `OutboxGroup` in `src/sase/doctor/_agent_publication.py`. `git diff HEAD --` confirms that file is unchanged by this repair; the class is used only inside its defining module, so the public name should be private. The finding originates in 77c0f23375 (phase sase-1tz.2.1.7, now closed) and was already recorded as KNOWN/out of scope in task sase-1u3. This run confirms the baseline lint failure persists; it is unrelated to the scoped inventory-reuse repair.

[2026-11-20T01:57:36Z · sase-1tz.2.1.5--2] DISCOVERED ISSUE: The required `sase tool run check` after this rebase reports two scoped-test failures outside the integrated inventory-reuse changes. `tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed` still finds `src/sase/agents_sync/publication_scratch.py:sweep_publication_scratch`; that source and audit test are unchanged here, and the same failure is already documented in epic note #1 from phase 2.1.4. `tests/agents_sync/test_commit_publication_queue/test_failures.py::test_repeated_format_publication_failure_retires_and_doctor_says_drop` expects `retired as unpublishable` in the doctor detail, but the unchanged doctor code returns a grouped signature summary. The relevant source/test files are unchanged by this repair; the latter behavior comes from the phase 2.1.7 doctor grouping change. The tool classified the scoped run as one NEW and one KNOWN failure; this evidence ties both failures to existing publication epic scope.

[2026-11-20T11:55:21Z · toobig-aa.test_skill_uses_loader.0] DISCOVERED ISSUE (corroboration of notes #1-#3): all three remain red on master fb85972f27 (after sase-1tz.2.1.5 landed). sase tool run check run 965ee6aefcdde2cec49e7a83788037ff (tests-only change, full-suite escalation) reports exactly these 3 as KNOWN with no owner: symvision OutboxGroup in src/sase/doctor/_agent_publication.py; test_artifact_directory_operation_sites_are_reviewed (extra site publication_scratch.py:sweep_publication_scratch); test_repeated_format_publication_failure_retires_and_doctor_says_drop (doctor detail now 'proj: 1 request(s) (retired) under signature ...' without 'retired as unpublishable').

[2026-11-20T12:10:48Z · toobig-aa.test_commit_publication_bounded_drain.0] DISCOVERED ISSUE (corroboration of notes #2/#4): symvision OutboxGroup in src/sase/doctor/_agent_publication.py is still red on master f76b82219a. Standalone just _lint-symvision fails on exactly that symbol, and sase tool run check run 784e83170d0b44d809b995f8594f8b33 (tests-only split of test_commit_publication_bounded_drain.py) reports it as the only failure: 1 KNOWN, no owner. Scoped tests passed. Fix remains making the file-local class private (_OutboxGroup).

[2026-11-20T12:23:09Z · toobig-aa.test_checks_agent_publication.0] DISCOVERED ISSUE (corroboration of notes #2/#4/#5): symvision OutboxGroup in src/sase/doctor/_agent_publication.py is still red on master 1d821e0c95. Standalone just _lint-symvision fails on exactly that symbol, and sase tool run check run 65f5be3de40acfb5a8cc707ba46370ac (tests-only split of tests/doctor/test_checks_agent_publication.py) reports it as the only failure: 1 KNOWN, no owner; scoped tests passed. Fix remains making the file-local class private (_OutboxGroup).

[2026-11-20T12:48:53Z · sase-1tz.2.1.land] LAND TRIAGE of phase PROPOSED FOLLOW-UP notes (sase-1tz.2.1.land, 2026-11-20). Resolved on master, no task: core pin moves (2.1.1 #3, 2.1.3 #2, 2.1.6 #2; sase-core-revision.txt 80fcc862 contains 3a32a233/5ad60139/3c3263fb/6eedf0a6/80fcc862); stale sase-1tz.2.1.2 epic-symbol rows (2.1.4 #2; sase bead epic-symbols empty); xprompt terminology failure (epic note #1, 2.1.2 #3 etc.; passes on master); LaunchPromptContext symvision (2.1.6 #3, 2.1.7 #3, 2.1.10 #5) fixed by fb85972f27, so sase-1u3 closed; sase-1tw closed (2.1.10 #3, demonstrated by 225bfb7ff2 plus retention test). Fixed by this lander (epic-caused): artifact-dir audit for publication_scratch.py:sweep_publication_scratch (epic note #1/#3, 2.1.8 #2, 2.1.11 #5) as a reviewed exemption; doctor-detail test failure (epic note #3), where group detail now keeps row reasons plus the newest member's last error; OutboxGroup symvision (epic note #2), made private. Tasks: 2.1.1 #2 gate_capacity flake +1 sase-1tn; drain_accounting order-dependent isolation bug (2.1.6 #3, 2.1.2 #3, 2.1.3 #3, 2.1.8 #2, 2.1.9 #2) created sase-1u4; sase-1rb remedy (b) (2.1.7 #4) created sase-1u5; remaining main-thread FS I/O callers (2.1.11 #1-#3, 2.1.13 #4) created sase-1u6; sase-1s4 evidence (2.1.11 #4) +1; bare_git index-lock flake (2.1.11 #5) +1 sase-1kr; bench_tui_trace clan-wave stub (2.1.13 #1/#5) created sase-1u7; master-gate video_frames failures (lander-discovered) created sase-1u8 and +1 sase-1ty. Noted: sase-1tx (2.1.10 #4, needs modal UX decision); sase-1nc (2.1.10 #6, per-type freed census soak). Declined: 2.1.2 #2 spawn ModuleNotFoundError in test_concurrent_error_appends_are_atomic_and_lossless, which passes on master and in CI; the spawn design predates the epic (6a6549cf65). Kept as epic work, not a task: 2.1.13 #3 level-based VmSwap GC deferral (caused by gc_policy), which goes into the remaining-work tale.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.2.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.land/README.md) | [sase-1tz.2.1](sase-1tz.2.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8cf9d8e`](https://github.com/sase-org/sase/commit/8cf9d8e5465994f9c1a34a5075a4bb7ea0ed9d47) | fix(doctor): keep cause detail in grouped publication issues and review scratch sweep | [sase-1tz.2.1](sase-1tz.2.1.md) | 2026-11-20 08:03:07 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tc.5.1.land][1] | Need causally related active scopes and runner-slot flake duplicate status | 1 |
| read-by | [agent:sase-1tz.2.1.1][2] | parent epic scope | 1 |
| read-by | [agent:sase-1tz.2.1.2][3] | Need parent epic DECISIONS and phase list | 1 |
| read-by | [agent:sase-1tz.2.1.3][4] | parent epic scope | 1 |
| read-by | [agent:sase-1tz.2.1.4][5] | Need parent epic DECISIONS, design, and remaining phases for pub_cleanup | 1 |
| read-by | [agent:sase-1tz.2.1.5--2][6] | Assess whether the known OutboxGroup Symvision lint failure belongs to this active publication-performance epic | 1 |
| read-by | [agent:sase-1tz.2.1.7][7] | Need parent epic plan context | 1 |
| read-by | [agent:toobig-aa.test_checks_agent_publication.0][8] | Check whether this in-progress epic owns the OutboxGroup symvision finding | 1 |
| read-by | [agent:toobig-aa.test_commit_publication_bounded_drain.0][9] | Read existing OutboxGroup discovered-issue notes on the causing epic | 2 |
| read-by | [agent:toobig-aa.test_skill_uses_loader.0][10] | Check whether epic already records the OutboxGroup/audit/doctor-wording master failures | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.5.1.land/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.1/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.2/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.3/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.1.4.md
[6]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.1.5.md
[7]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.7/README.md
[8]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-aa.test_checks_agent_publication.0/README.md
[9]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-aa.test_commit_publication_bounded_drain.0/README.md
[10]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-aa.test_skill_uses_loader.0/README.md

<!-- sase:referenced-by:end -->
