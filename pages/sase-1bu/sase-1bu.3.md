# Bead: sase-1bu.3 — Ledger root resolution and the hidden-clone write lane

[Bead Pages](../README.md) / [sase-1bu](README.md) / sase-1bu.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tb.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tb.w0.md) · **Assignee:** `sase-1bu.3` · **Size:** medium
**Created:** 2026-09-27 19:03:20 EDT · **Closed:** 2026-09-28 02:12:04 EDT
**Plan:** [202609/goal\_ledger.md](https://github.com/sase-org/sase--plans/blob/main/202609/goal_ledger.md)

## Description

ledger-root: resolve each project's ledger (goals.visibility / goals.host_role config, shared in the hidden beads clone or local-only), and add the locked write transaction that commits only goals/. Publish synchronously through the existing managed sync worker, and keep bead commits and readers clear of goals/.

## Notes

[2026-09-28T04:59:14Z · sase-1bu.3] PROPOSED FOLLOW-UP: goal_ledger_append plans edit-on-missing against GoalStateWire::empty instead of None, so the goal_not_found refusal in plan_edit is unreachable via append (verified: edit of unknown id returns applied); needs a ledger-io/core-model owner to decide empty-state vs None planning

[2026-09-28T05:10:30Z · sase-1bu.3] PROPOSED FOLLOW-UP: bump pyproject sase-core-rs floor once a published release contains the goal bindings (cbe70f6 unreleased; release-core-floor probe lists them as blocked_unpublished alongside other in-flight bindings)

[2026-09-28T06:10:47Z · sase-1bu.3--1] PROPOSED FOLLOW-UP: test_build_agent_completion_candidates_omits_empty_clan and test_named_proc_is_not_also_offered_as_a_plain_agent_candidate fail identically on the clean base tree (extra main/tab candidates); needs a TUI completion owner, unrelated to goal ledger

[2026-09-28T06:11:07Z · sase-1bu.3--1] PROPOSED FOLLOW-UP: test_scroll_derived_cursor_and_streaming_stays fails under full-suite load but passes solo with and without ledger-root changes; suspected load flake, needs a decks owner to confirm

[2026-09-28T06:11:27Z · sase-1bu.3--1] PROPOSED FOLLOW-UP: test_project_sase_yml_matches_public_schema fails identically on the clean base tree (tools.check receipt key rejected by schema); needs a config-schema owner, unrelated to goals schema addition

[2026-09-28T06:12:04Z · sase-1bu.3--1] ledger-root done: goals config (visibility/host_role), hidden-clone resolution, locked goals-only write txn with sync publish, bead-commit goals/ exclusion. Verified: tests/goals (20) + commit-type-tag contract pass; fixed new SASE_TYPE=goals tagging in goals/write.py. just check 3 NEW failures dispositioned: 2 agent-completion + config-schema fail identically on base, deck-spread passes solo (load flake); all recorded as PROPOSED FOLLOW-UP. No epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-1bu.2](sase-1bu.2.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bu.4](sase-1bu.4.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bu.6](sase-1bu.6.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bu.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bu.3.md) | [sase-1bu.3](sase-1bu.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9b69949`](https://github.com/sase-org/sase/commit/9b69949d98429b1b2fd2a2b9eab5957d695debc7) | feat(goals): ledger root resolution and hidden-clone write lane (sase-1bu.3) | [sase-1bu.3](sase-1bu.3.md) | 2026-09-28 02:30:10 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bu.3--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bu.3.md

<!-- sase:referenced-by:end -->
