# Bead: sase-17z.3 — Names everywhere plans are listed

[Bead Pages](../README.md) / [sase-17z](README.md) / sase-17z.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qx](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qx.md) · **Assignee:** `sase-17z.3` · **Size:** small
**Created:** 2026-09-24 12:07:29 EDT · **Closed:** 2026-09-24 13:50:02 EDT
**Plan:** [202609/plan\_approve\_names.md](https://github.com/sase-org/sase--plans/blob/main/202609/plan_approve_names.md)

## Description

surfaces: lead `sase plan list` Proposed rows and `sase plan show` hints with the plan name, add a `name` JSON field, and finish the name-first docs.

## Notes

[2026-09-24T17:49:44Z · sase-17z.3] PROPOSED FOLLOW-UP: just check symvision gate fails on master with 74 private-import violations in llm_provider/usage, ace/tui and others, none in plan files; proven identical on pristine tree

[2026-09-24T17:50:02Z · sase-17z.3] Surfaces done and verified: Proposed rows lead with plan name (collision-qualified display, dim id_prefix second line) plus approve/reject hint line; name field in ProposedPlan JSON and show proposal context/hint/JSON; cli.md and configuration.md updated. Focused suites green (81 inventory/show/resolve + 45 selector/approve tests). just check red only on pre-existing symvision violations, proven identical on pristine tree with zero overlap in touched files.

## Dependencies

- **Depends on:** [sase-17z.1](sase-17z.1.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17z.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17z.3/README.md) | [sase-17z.3](sase-17z.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c3a61ae`](https://github.com/sase-org/sase/commit/c3a61ae7d9e178ef1ec4758b808191ea50c54a93) | feat(plan): names everywhere plans are listed (sase-17z.3) | [sase-17z.3](sase-17z.3.md) | 2026-09-24 13:51:33 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17z.3][1] | check surfaces phase deps status | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17z.3/README.md

<!-- sase:referenced-by:end -->
