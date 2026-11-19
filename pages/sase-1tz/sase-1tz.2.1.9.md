# Bead: sase-1tz.2.1.9 — Stop policy-initiated garbage collections from blocking the loop for seconds

[Bead Pages](../README.md) / [sase-1tz.2.1](sase-1tz.2.1.md) / sase-1tz.2.1.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.md) · **Assignee:** `sase-1tz.2.1.9` · **Size:** medium
**Created:** 2026-11-19 11:13:28 EST · **Closed:** 2026-11-19 17:01:18 EST
**Plan:** [202611/noise\_publication\_digests\_tui\_stalls.md](https://github.com/sase-org/sase--plans/blob/main/202611/noise_publication_digests_tui_stalls.md)

## Description

gc_policy: idle, backstop, and RSS-backstop collections stay bounded. The policy re-freezes survivors, defers full collections while the process is swapping, and cost-gates the backstops, while keeping the memory backstops. Before/after pause stats are recorded by trigger.

## Notes

[2026-11-19T21:02:25Z · sase-1tz.2.1.9] Pre-change live baseline captured 2026-11-19 from all retained tui_stalls.jsonl rows on athena and apollo (gen-2 pause seconds by trigger, n / p50 / p95 / max). Athena: backstop 17 / 17.733 / 102.783 / 324.224; idle 2043 / 1.900 / 3.258 / 74.773; rss_backstop 79 / 2.008 / 3.994 / 31.828; startup_freeze 38 / 0.692 / 1.265 / 3.437. Apollo: automatic 1 / 8.264 / 8.264 / 8.264; backstop 9 / 1.951 / 5.498 / 7.274; idle 2161 / 0.764 / 1.793 / 4.289; rss_backstop 47 / 0.933 / 2.047 / 2.939; startup_freeze 26 / 0.593 / 0.798 / 0.952. Recent 24h heartbeat peaks were 5.83 GB across 8 athena instances and 3.87 GB across 8 apollo instances; the Nov 16 15-35 GB runaway did not reproduce. Implemented freeze-only startup, re-freeze after every full policy sweep, deep unfreeze/full/re-freeze after 15 minutes of input quiet at most every 30 minutes, a 2x allocated-block pause predictor with a 2 s ordinary pause budget, and cached worker-sampled VmSwap/major-fault deferral (>16 MiB or >100 faults/s). Deferrals are queued off the UI thread and rate-limited; perf runbook updated. After the human install/restart and a four-hour observation window, remeasure with `tools/tui_freeze_report --since <window-start-ISO-8601> --until <window-end-ISO-8601>`. No post-install live measurement is available in this phase.

[2026-11-19T21:25:15Z · sase-1tz.2.1.9] PROPOSED FOLLOW-UP: Land triage should re-key the unrelated clean-base failures, confirmed by the same three targeted nodes on detached clean HEAD afb070580a159fc383b8b5f52e29ea649328c096: tests/test_macro_terminology.py::test_macro_string_literals_avoid_xprompt_terms fails on existing unclassified %xprompts_enabled strings (historical task sase-1hr; recurrence already discussed in sibling phase sase-1tz.2.1.11); tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed finds src/sase/agents_sync/publication_scratch.py:sweep_publication_scratch, already recorded by sase-1tz.2.1.11 note 5; tests/agents_sync/test_commit_publication_drain_accounting.py::test_cleanup_after_success_does_not_resurrect uses a clean stub that rejects remaining_timeout, in the clean-base drain-accounting family recorded on sase-1qt.2 note 3. This GC phase changed none of those inputs.

[2026-11-19T22:01:18Z · sase-1tz.2.1.9] Implemented startup freeze without a full collection, survivor re-freezing after policy sweeps, long-idle deep collection cadence, pause-cost and cached memory-pressure gates, off-thread pressure sampling/deferred telemetry, and the perf runbook update. Verification: `just fmt` and `git diff --check` passed; 78 GC policy/lifecycle/census/telemetry tests passed. `sase tool run check` 400b4f9f07b7dcf8681dadc91080b6c6 passed lint, docs, and SASE validation, with 9,738 tests passed, 1 skipped, and only `test_macro_string_literals_avoid_xprompt_terms` failing; that exact failure was reproduced on detached clean HEAD afb070580a159fc383b8b5f52e29ea649328c096 and is recorded as a proposed follow-up with existing references. Clean-base targeted checks also confirmed the artifact-operation audit and agents-sync cleanup test failures, recorded in the same follow-up. `sase bead epic-symbols` returned no entries.

## Dependencies

- **Blocks:** [sase-1tz.2.1.10](sase-1tz.2.1.10.md) ✓ · ⧖ 2026-11-19
- **Blocks:** [sase-1tz.2.1.13](sase-1tz.2.1.13.md) ◐ · ⧖ 2026-11-19
- **Depends on:** [sase-1tz.2.1.8](sase-1tz.2.1.8.md) ✓ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.2.1.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.9/README.md) | [sase-1tz.2.1.9](sase-1tz.2.1.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`49b96a9`](https://github.com/sase-org/sase/commit/49b96a9c5095bf677829c980bcfe8b658d0b5182) | feat(tui): gate policy GC pauses | [sase-1tz.2.1.9](sase-1tz.2.1.9.md) | 2026-11-19 17:03:45 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.2.1.9][1] | Verify the implementation evidence note was recorded | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.9/README.md

<!-- sase:referenced-by:end -->
