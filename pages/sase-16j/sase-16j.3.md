# Bead: sase-16j.3 — Enter keymap swap and ,n retirement

[Bead Pages](../README.md) / [sase-16j](README.md) / sase-16j.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ph](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ph.md) · **Assignee:** `sase-16j.3` · **Size:** medium
**Created:** 2026-09-22 13:38:30 EDT · **Closed:** 2026-09-22 16:10:28 EDT
**Plan:** [202609/agents\_enter\_act\_on\_agent.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_enter_act_on_agent.md)

## Description

wire: add the act_on_agent app action bound to enter (jump_to_agent_patch stays as an unbound action), connect the resolver to the chooser, retire leader.jump_to_notification as a relocated key, and update the footer, help, palette, onboarding, docs, and tests.

## Notes

[2026-09-22T20:09:38Z · sase-16j.3] PROPOSED FOLLOW-UP: just check symvision gate reports unused agent_env_refusal_reason in src/sase/service/platform.py though it is used in-file and tested; pre-existing and unrelated to this phase (no touched file references it)

[2026-09-22T20:10:28Z · sase-16j.3] Enter wired to act_on_agent with chooser dispatch; ,n retired as relocated key; footer/help/palette/onboarding/docs updated. Verified: 131 scoped tests + 116 Enter/backlog/chooser tests pass; ruff/mypy/fmt green; epic-symbols cleared. just check symvision flags pre-existing unrelated agent_env_refusal_reason (noted as follow-up).

## Dependencies

- **Depends on:** [sase-16j.1](sase-16j.1.md) ✓ · ⧖ 2026-09-22
- **Depends on:** [sase-16j.2](sase-16j.2.md) ✓ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16j.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16j.3/README.md) | [sase-16j.3](sase-16j.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b27029e`](https://github.com/sase-org/sase/commit/b27029e894a0176f213c3915ddfc8b003acfed9a) | feat(ace): make Agents Enter context-aware via act\_on\_agent | [sase-16j.3](sase-16j.3.md) | 2026-09-22 16:12:48 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16j.3][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-16j.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16j.3/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16j.land/README.md

<!-- sase:referenced-by:end -->
