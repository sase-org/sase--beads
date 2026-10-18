# Bead: sase-1mk.9.5 — Fix the known-continuation and provider-drain flakes

[Bead Pages](../README.md) / [sase-1mk.9](sase-1mk.9.md) / sase-1mk.9.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1mk.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1mk.land.md) · **Assignee:** `sase-1mk.9.5` · **Size:** medium
**Created:** 2026-10-18 16:48:01 EDT · **Closed:** 2026-10-18 17:54:21 EDT
**Plan:** [202610/ship\_v0\_18\_0\_post\_repair\_reds.md](https://github.com/sase-org/sase--plans/blob/main/202610/ship_v0_18_0_post_repair_reds.md)

## Description

runtime-flakes: root-cause test_agent_run_stops_on_generic_output and the provider-drain JSONDecodeError (sase-1k2) outside the TUI.

## Notes

[2026-10-18T21:54:10Z · sase-1mk.9.5--1] runtime-flakes evidence for task sase-1k2: the 20-iteration -n 8 stress command completed with 19 clean iterations (30 passed each). Both target nodes, test_agent_run_stops_on_generic_output and test_provider_drain_e2e_relaunches_stranded_agent, passed all 20 iterations. Iteration 16 had one failure only: test_agent_run_continues_past_all_known_stage stopped with helper_error and yielded undetermined — 1 KNOWN. After the required check rebuilt the linked sase-core-rs 0.42.0 extension, that adjacent test passed in the scoped check and a standalone -n 8 rerun. The first sase tool run check found the new test sleep missing its sase-test-wait pragma; the pragma was added, then ToolRun a5b7bf5d2604abf8e656331d6b01d02f passed all lint and validation stages and 523 selected tests (523/5274). CI status: latest completed Master Gate 39168313120 at b68b516 passed all eight test shards; provider-drain appeared in successful test (6). Newer Master Gate 39168441419 at 7f3c8d0 remains in progress. Full CI 39164596460 at 457dd728 remains in progress, with test (3.12), (3.13), and (3.14) unfinished; lint and visual-test jobs failed, and their logs are unavailable until the workflow completes. Task sase-1k2 remains open; this note records evidence only. PROPOSED FOLLOW-UP: investigate the one xdist helper_error in test_agent_run_continues_past_all_known_stage from stress iteration 16; the fresh extension reruns passed.

[2026-10-18T21:54:21Z · sase-1mk.9.5--1] Verified both runtime-flakes target nodes passed all 20 stress iterations; recorded the single adjacent xdist helper_error and passing reruns as a proposed follow-up. sase tool run check ToolRun a5b7bf5d2604abf8e656331d6b01d02f passed all lint/validation stages and 523 selected tests. Latest completed Master Gate 39168313120 passed all eight shards; the newer gate and Full CI remain in progress as detailed in the phase note. sase-1k2 remains open. epic-symbol check found no leftovers.

## Dependencies

- **Blocks:** [sase-1mk.9.6](sase-1mk.9.6.md) ◐ · ⧖ 2026-10-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1mk.9.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1mk.9.5.md) | [sase-1mk.9.5](sase-1mk.9.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e5c02dc`](https://github.com/sase-org/sase/commit/e5c02dc8a439c0df5610d0e07ea5e1b0b5a59e6a) | fix(runtime): harden triage and provider drain handling | [sase-1mk.9.5](sase-1mk.9.5.md) | 2026-10-18 17:55:29 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1mk.9.5--1][1] | Need the phase scope, design file, and earlier remaining-work notes before completing verification | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1mk.9.5.md

<!-- sase:referenced-by:end -->
