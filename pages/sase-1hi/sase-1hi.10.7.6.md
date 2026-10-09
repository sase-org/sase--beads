# Bead: sase-1hi.10.7.6 — Plan Decisions finish gaps: visible chosen-branch tint, a stale reopen that can submit, generic rails back to 42, the owed gate tests, and a real Telegram launch-failure signal

[Bead Pages](../README.md) / [sase-1hi.10.7](sase-1hi.10.7.md) / sase-1hi.10.7.6

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1hi.10.7.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.10.7.land.md) · **Assignee:** `sase-1hi.10.7.6.land`
**Created:** 2026-10-08 19:15:59 EDT
**Plan:** [202610/plan\_decisions\_finish\_gaps.md](https://github.com/sase-org/sase--plans/blob/main/202610/plan_decisions_finish_gaps.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/plan_decisions_finish_gaps.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/plan_decisions_finish_gaps.md

<!-- sase:links:end -->

## Description

Close the gaps the sase-1hi.10.7 land audit found in its own phases. ACE shows the chosen branch green and bold on screen. A stale review reopened after the modal closed can still submit. Generic gates keep their old rail width. The gate route tests the repair plans required exist and assert behaviour. Telegram says "coder could not start" only when sase recorded a real coder launch failure, and keeps each decision's choices next to its question.

## Notes

[2026-10-09T07:21:20Z · sase-1id.land] DISCOVERED ISSUE: just check lint (test waits) is red: tools/check_test_wait_helpers reports tests/ace/tui/test_plan_decision_ace_stale.py:183 and :310 inline-pause-wait (bounded 'for _ in range(100): ... await asyncio.sleep(0.05); await pilot.pause()' loops). Both loops were added by 1820636212 (SASE_BEAD sase-1hi.10.7.6.1, stale reopen via real open path). Reproduced on master bfe1d9c361 with 'just _lint-test-waits'. Fix: replace with sase.ace.testing.wait.wait_for (or add the '# sase-test-wait: <reason>' pragma). Reported as a PROPOSED FOLLOW-UP by sase-1id.6 (docs_truth) and routed here by the sase-1id land agent.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1hi.10.7.6.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1hi.10.7.6.land/README.md) | [sase-1hi.10.7.6](sase-1hi.10.7.6.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1hi.10.7.6.3--1][1] | need parent decisions for phase work | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.10.7.6.3.md

<!-- sase:referenced-by:end -->
