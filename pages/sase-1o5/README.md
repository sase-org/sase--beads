# Bead: sase-1o5 — Questions and answers on the Agents Main deck

[Bead Pages](../README.md) / sase-1o5

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.58.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.58.linker.w0.md) · **Assignee:** `sase-1o5.land`
**Created:** 2026-10-24 19:29:30 EDT · **Closed:** 2026-10-25 00:52:51 EDT
**Plan:** [202610/questions\_main\_deck.md](https://github.com/sase-org/sase--plans/blob/main/202610/questions_main_deck.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/questions_main_deck.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 3 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/questions_main_deck.md

<!-- sase:links:end -->

## Description

Selecting an agent session, the turn that asked, or a question gate turn on the Agents tab shows that session's /sase_questions rounds in a QUESTIONS section on the Main deck's Context card: each question, its recommended (first-listed) option, the actual answer when one exists, and how the round was answered (human via TUI, Telegram, mobile, or CLI; automatic policy; agent; unknown). Data is projected from the existing question gate bundles, nothing new is written at settlement, and it works for every past gate-turn round with no backfill.

## Notes

[2026-10-25T02:14:54Z · sase-1nn.8.4.3.land] DISCOVERED ISSUE: Phase .2 commit 5497b59c5d adds --epic-symbol sase-1o5.3(project_question_round), but src/sase/question_gate_turn/projection.py:315 already consumes it. Master Gate 40149338072 attempt 2 lint job 121044124879 rejects the unnecessary exemption. The same commit advances source pin to 3156d11f, after published v0.42.5, renewing CORE_LAG. Release lander plans removal of the stale entry and a guarded containing core cut/metadata refresh; it will re-inventory before editing to avoid duplicating .3 cleanup. Other still-needed .3 exemptions remain until their actual consumers land. Evidence file:explicit:eca15519850917b7992759fe.

[2026-10-25T04:52:51Z · sase-1o5.land] LANDING VERIFIED at master 113d799b2c (+ this landing's uncommitted integration edits, committed by the host after this turn).

Step 1 (verify): read the epic, plan (placement=before_vars decision), all six phases and every note; reviewed each phase commit (b76183e938 .1, 5497b59c5d .2, 393430da55 .3, 518717cdac .4, 2066212dfa .5, 113d799b2c .6) and the source. qa_markdown renders option-less Answer and pick Comment lines; decline_auto_execution/should_auto_execute park option-less auto rounds on live and resume paths. sase-core 3156d11f (on sase-core origin/master, pinned by sase-core-revision.txt) has the pure question_round projection whose status/actor (source before caller)/recommendation/data_state rules match the shared contracts, plus the project_question_round binding and tests. The sase facade, projection loader, presenter, lane (batch 1, gate-state-keyed invalidation, use-site imports), and Context-card mount all landed; the mount sits immediately before OUTPUT VARIABLES, honoring before_vars. The gate-row GATE section is de-duplicated, while Reply phases and hint mode keep their behavior. Docs and the skill sentence landed undeployed.

Step 2 (integrate): the only non-epic commit since the start is 3d13864e76 (removed tracked .sase-evidence), which fixed the xprompt terminology failure the phases kept reporting. Landing edits: retired all six sase-1o5 --epic-symbol rows. parse_question_round_wire went private. The QuestionRoundHeadingSource protocol became the real QuestionRoundStub type. Presenter helpers now name QuestionAnswer/Cancellation/Option/ProvenanceView, deduping duplicated cancellation, responded-at, and feedback code. Also tidied the lane's misplaced TYPE_CHECKING import and stale comment in _agent_display_state.py, corrected the docs sentence that claimed the gate-row GATE section still renders the round, and fixed tests/perf/bench_detail_header_summary.py (pre-epic _TRACE_SPAN_PREFIX rename; the plan required keeping it working) and added its question_rounds span.

Verification: 62 focused question tests plus the bench smoke test pass. just symvision is clean. sase tool run check 1382d84adc9afcfbd08453027edb81cd: 57527 passed, 1 failed (test_tui_app_import_stays_under_startup_budget 3538 vs 3537, identical on the clean tree with changes stashed; tracked by sase-1ic).

Follow-ups: import budget (.1/.2/.3/.4) -> +1 sase-1ic. Macro xprompt terminology (.1/.2/.3/.4) -> declined: fixed by 3d13864e76 (not reproduced in the full check run), and the phases' sase-1hr attribution named a different node. bench_detail_header_summary unimportable (.4) -> fixed in this landing. bench_tui_jk p95 over 16 ms (.5) -> +1 sase-1ge after a reproduction (10 failed/9 passed under load avg 8-14, main agents j/k passed). sort_and_reorder None/datetime TypeError (.5) -> reproduced, new task sase-1ob (small). Declined-auto gates keep an outcome=auto policy block and decision-log row (.1; deferred by the plan's own instruction) -> reproduced, new task sase-1oc (large). Epic note #1 (sase-1nn.8.4.3.land): stale project_question_round row already dropped by 393430da55; the CORE_LAG release cut is owned by release epic sase-1nn.8.4.3.5. The sase_questions skill deploy goes through a human gate, because the global editable install's primary checkout (87827788c2) does not yet contain 113d799b2c.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1o5.1](sase-1o5.1.md) | Fix the two latent shared question bugs | ✓ closed | small | 2026-10-24 | 1 | 1 |
| [sase-1o5.2](sase-1o5.2.md) | Core question-round projection, binding, and Python read model | ✓ closed | medium | 2026-10-24 | 1 | 2 |
| [sase-1o5.3](sase-1o5.3.md) | Rich presenter and GATE-phase swap for question gates | ✓ closed | medium | 2026-10-24 | 1 | 1 |
| [sase-1o5.4](sase-1o5.4.md) | Question-round scoping and the questions summary lane | ✓ closed | medium | 2026-10-24 | 1 | 1 |
| [sase-1o5.5](sase-1o5.5.md) | Mount the QUESTIONS section on the Context card | ✓ closed | medium | 2026-10-24 | 1 | 1 |
| [sase-1o5.6](sase-1o5.6.md) | Reference docs and the questions skill sentence | ✓ closed | small | 2026-10-24 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1o5: Questions and answers on the Agents Main deck [closed]"]
    n1["sase-1o5.1: Fix the two latent shared question bugs [closed]"]
    n2["sase-1o5.2: Core question-round projection, binding, and Python read model [closed]"]
    n3["sase-1o5.3: Rich presenter and GATE-phase swap for question gates [closed]"]
    n4["sase-1o5.4: Question-round scoping and the questions summary lane [closed]"]
    n5["sase-1o5.5: Mount the QUESTIONS section on the Context card [closed]"]
    n6["sase-1o5.6: Reference docs and the questions skill sentence [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n2 -.-> n3
    n2 -.-> n4
    n3 -.-> n5
    n4 -.-> n5
    n5 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1o5.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1o5.1/README.md) | [sase-1o5.1](sase-1o5.1.md) | 1 |
| [bbugyi200.athena.sase-1o5.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1o5.2.md) | [sase-1o5.2](sase-1o5.2.md) | 2 |
| [bbugyi200.athena.sase-1o5.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1o5.3/README.md) | [sase-1o5.3](sase-1o5.3.md) | 1 |
| [bbugyi200.athena.sase-1o5.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1o5.4.md) | [sase-1o5.4](sase-1o5.4.md) | 1 |
| [bbugyi200.athena.sase-1o5.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1o5.5/README.md) | [sase-1o5.5](sase-1o5.5.md) | 1 |
| [bbugyi200.athena.sase-1o5.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1o5.6/README.md) | [sase-1o5.6](sase-1o5.6.md) | 1 |
| [bbugyi200.athena.sase-1o5.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1o5.land/README.md) | [sase-1o5](README.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b76183e`](https://github.com/sase-org/sase/commit/b76183e9382941b325c46be867f71089b7bc8127) | fix(gates): render free-text answers and park option-less auto rounds as manual gates | [sase-1o5.1](sase-1o5.1.md) | 2026-10-24 20:14:43 EDT |
| sase-core | [`sase-core@3156d11`](https://github.com/sase-org/sase-core/commit/3156d11f33d5a5277ff806a78b92a9490f78d6be) | feat(question-round): add pure question\_round projection and project binding | [sase-1o5.2](sase-1o5.2.md) | 2026-10-24 21:03:41 EDT |
| sase | [`5497b59`](https://github.com/sase-org/sase/commit/5497b59c5ddac82c20cf92bd0f63394a1f5e2d82) | feat(questions): add question-round facade, projection loader, and core binding validation | [sase-1o5.2](sase-1o5.2.md) | 2026-10-24 21:06:42 EDT |
| sase | [`393430d`](https://github.com/sase-org/sase/commit/393430da551e6a981ebb0e3cf0f821eb2bf8cc60) | feat(ace): rich text presenter for question gates with GATE-phase swap | [sase-1o5.3](sase-1o5.3.md) | 2026-10-24 22:14:40 EDT |
| sase | [`518717c`](https://github.com/sase-org/sase/commit/518717cdaca4b05ed19427ceab4371987c60d16f) | feat(questions): add question-round scoping and questions summary lane | [sase-1o5.4](sase-1o5.4.md) | 2026-10-24 22:42:58 EDT |
| sase | [`2066212`](https://github.com/sase-org/sase/commit/2066212dfa5de8c57020bd604cd33f5f96196f33) | feat(ace): mount QUESTIONS section on Context card | [sase-1o5.5](sase-1o5.5.md) | 2026-10-24 23:44:30 EDT |
| sase | [`113d799`](https://github.com/sase-org/sase/commit/113d799b2c29f0ad49c46bf57ad55876bc5e9856) | docs(questions): document QUESTIONS section and skill sentence | [sase-1o5.6](sase-1o5.6.md) | 2026-10-25 00:03:18 EDT |
| sase | [`369ac34`](https://github.com/sase-org/sase/commit/369ac34168e6ee3787c40f42dc015422141b2286) | chore(questions): land sase-1o5 and retire its epic-symbol rows | [sase-1o5](README.md) | 2026-10-25 00:55:29 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1o5.1][1] | epic context for phase | 1 |
| read-by | [agent:sase-1o5.3][2] | Need phase scope, epic notes, and prior work | 1 |
| read-by | [agent:sase-1o5.5][3] | Need parent epic context and decisions | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1o5.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1o5.3/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1o5.5/README.md

<!-- sase:referenced-by:end -->
