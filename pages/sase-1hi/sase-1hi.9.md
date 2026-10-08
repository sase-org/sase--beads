# Bead: sase-1hi.9 — Planner and memory-skill policy, authoring docs, and flag removal

[Bead Pages](../README.md) / [sase-1hi](README.md) / sase-1hi.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.5n](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.5n.md) · **Assignee:** `sase-1hi.9` · **Size:** medium
**Created:** 2026-10-07 18:48:32 EDT · **Closed:** 2026-10-08 04:32:56 EDT
**Plan:** [202610/plan\_decisions.md](https://github.com/sase-org/sase--plans/blob/main/202610/plan_decisions.md)

## Description

policy: teach planners when to embed a decision instead of asking now, rewrite the memory-write authorization routes around memory decisions, document the authoring grammar in `--explain` and the SDD docs, delete the beta flag's Off branch, and record the follow-ups, including the dogfooded memory-decision plan for this feature's own memory notes.

## Notes

[2026-10-08T08:29:03Z · sase-1hi.9] PROPOSED FOLLOW-UP: Dogfood memory plan — glossary:plan-decision strand, decisions record, generated_skills Plan Mode line, worked plan-first with memory decisions for Bryan review

[2026-10-08T08:29:10Z · sase-1hi.9] PROPOSED FOLLOW-UP: Enforcing guard mode for memory_change_uncovered after a soak period — refuse publication and list uncovered paths

[2026-10-08T08:29:18Z · sase-1hi.9] PROPOSED FOLLOW-UP: Android client renders the Decision Sheet from the gateway and the mobile wire carries it

[2026-10-08T08:29:29Z · sase-1hi.9] PROPOSED FOLLOW-UP: Memory task beads under %auto can never obtain human consent via sase bead work — decide whether to drop %auto for memory beads or count human-created bead descriptions as human text

[2026-10-08T08:29:36Z · sase-1hi.9] PROPOSED FOLLOW-UP: Generic gate-input UX follow-ups — TypedInputForm bool toggle, Telegram step-flow yes/no keyboard and Keep default for custom gates

[2026-10-08T08:29:43Z · sase-1hi.9] PROPOSED FOLLOW-UP: CLI review token (-V) if a script ever needs one

[2026-10-08T08:29:50Z · sase-1hi.9] PROPOSED FOLLOW-UP: just check symvision gate red on 4 NEW unused symbols (is_unverified_row, collapsed_row_text, expanded_row_text in plan_decision_rows.py; classify_callout in plan_decision_document.py) — reproduces identically on clean base tree; tracked by sase-1hp

[2026-10-08T08:32:56Z · sase-1hi.9] Skills teach embed-vs-ask (sase_plan), memory-decision auth routes plus declined-change handling and guard (sase_memory_write), and Plan Decision pointer (sase_questions); --explain and sdd.md document the grammar, lifecycle, archive fields, and Archived mode with beta framing removed; plan_decisions Off branch deleted and On made unconditional with registry/schema/bead retired (sase-1hq closed). Verified: 211 focused tests pass (decision suites, skill phrases, validate suites, approve/gate/ACE suites), workspace sase plan validate renders the Decision Sheet with no flag, schema-drift and flag-integrity checks clean, epic-symbols empty. just check stops at the symvision gate on 4 NEW unused ACE symbols that fail identically on the clean base (recorded as follow-up, tracked by sase-1hp).

## Dependencies

- **Depends on:** [sase-1hi.5](sase-1hi.5.md) ✓ · ⧖ 2026-10-07
- **Depends on:** [sase-1hi.6](sase-1hi.6.md) ✓ · ⧖ 2026-10-07
- **Depends on:** [sase-1hi.7](sase-1hi.7.md) ✓ · ⧖ 2026-10-07
- **Depends on:** [sase-1hi.8](sase-1hi.8.md) ✓ · ⧖ 2026-10-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1hi.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1hi.9/README.md) | [sase-1hi.9](sase-1hi.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ee3a4f6`](https://github.com/sase-org/sase/commit/ee3a4f6787a6e5fa53790a63b044ed48ca2b24da) | feat(plan): add Plan Decisions step with memory-write routing | [sase-1hi.9](sase-1hi.9.md) | 2026-10-08 04:35:05 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1hi.9][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1hi.9/README.md

<!-- sase:referenced-by:end -->
