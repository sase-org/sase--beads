# Bead: sase-1ip.6 — Gates decide through evaluate()

[Bead Pages](../README.md) / [sase-1ip](README.md) / sase-1ip.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0yj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0yj.md) · **Assignee:** `sase-1ip.6` · **Size:** medium
**Created:** 2026-10-09 05:12:54 EDT · **Closed:** 2026-10-09 13:01:32 EDT
**Plan:** [202610/auto\_e1\_autonomy\_record.md](https://github.com/sase-org/sase--plans/blob/main/202610/auto_e1_autonomy_record.md)

## Description

gates: adapters declare capability sets, plan, epic, and question gates resolve through core evaluate() with a policy block and a decision-log row, and the agent receives the awareness block.

## Notes

[2026-10-09T16:20:19Z · sase-1ip.6] PROPOSED FOLLOW-UP: add decisions:autonomy-one-record memory note (autonomy is one record evaluated in core, not gate UI defaults); skipped per epic plan decision_record=no

[2026-10-09T17:01:23Z · sase-1ip.6--1] PROPOSED FOLLOW-UP: flaky tests/sdd/test_git_identity_fixture.py::test_sdd_git_identity_survives_empty_home_subprocess failed once in check run 77e35a42601cb848644144e4585ee9e9, triaged no_new_failures FLAKY per reproducible_flake_baseline.txt, untouched by this phase

[2026-10-09T17:01:32Z · sase-1ip.6--1] Gates via core evaluate(): adapters declare auto_capabilities; plan/epic/question evaluate once from the attached record snapshot with legacy enabled/argument fallback; policy block on envelope auto block, creation-result auto_resolution, and auto response.json (manual rule manual); one decision-log row per non-manual evaluation; awareness block via with_awareness_block on the anonymous-workflow prompt step in macro/workflow_executor_steps_prompt.py; docs sdd.md and notifications.md updated; contract suite 62 passed with only the 4 inherit-owned xfails

## Dependencies

- **Depends on:** [sase-1ip.3](sase-1ip.3.md) ✓ · ⧖ 2026-10-09
- **Depends on:** [sase-1ip.4](sase-1ip.4.md) ✓ · ⧖ 2026-10-09
- **Blocks:** [sase-1ip.7](sase-1ip.7.md) ✓ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ip.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ip.6.md) | [sase-1ip.6](sase-1ip.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6f6754f`](https://github.com/sase-org/sase/commit/6f6754f97db91a80c105b52d7719f31c29814173) | feat(gates): resolve plan, epic, and question gates through core evaluate() | [sase-1ip.6](sase-1ip.6.md) | 2026-10-09 13:02:53 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ip.6--1][1] | Need phase scope | 1 |
| read-by | [agent:sase-1ip.land--3][2] | finish_auto_e1_landing closeout: verify all phase children closed and exit criteria met | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ip.6.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ip.land.md

<!-- sase:referenced-by:end -->
