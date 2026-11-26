# Bead: sase-1vd.7 — Agent guidance, contract docs, and skill rollout

[Bead Pages](../README.md) / [sase-1vd](README.md) / sase-1vd.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1gp](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1gp.md) · **Assignee:** `sase-1vd.7` · **Size:** small
**Created:** 2026-11-26 10:49:30 EST · **Closed:** 2026-11-26 16:43:18 EST
**Plan:** [202611/question\_copy\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202611/question_copy_panel.md)

## Description

agent-guidance: teach agents the `copy` field through the sase_questions skill source with a worked example and authoring rules, document the contract, and request the post-landing skill deploy.

## Notes

[2026-11-26T21:43:10Z · sase-1vd.7] PROPOSED FOLLOW-UP: Recheck the intermittent nested check child start failure in tests/tool/test_admission_processes.py::test_nested_agent_check_keeps_parent_and_never_queues (already tracked by sase-1ve). The scoped sase tool run check reported it under concurrent load; the targeted test passed on a clean HEAD worktree.

[2026-11-26T21:43:18Z · sase-1vd.7] Added the copy schema, Spotlight example, authoring rules, contract reference, CLI schema pointer, and skill-source test. just fix, generated skill diff, targeted test passed, docs/lint stages passed; scoped check reported existing sase-1ve failure, and its targeted clean-base rerun passed.

## Dependencies

- **Depends on:** [sase-1vd.4](sase-1vd.4.md) ✓ · ⧖ 2026-11-26
- **Depends on:** [sase-1vd.6](sase-1vd.6.md) ✓ · ⧖ 2026-11-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vd.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vd.7/README.md) | [sase-1vd.7](sase-1vd.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`909566a`](https://github.com/sase-org/sase/commit/909566a2079984631682156450d80fe8ccd8fb7d) | feat(questions): document copy items for agents | [sase-1vd.7](sase-1vd.7.md) | 2026-11-26 16:45:33 EST |
