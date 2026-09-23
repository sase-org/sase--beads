# Bead: sase-16n.11.2 — Python project tag backend fixes and missing launch tests

[Bead Pages](../README.md) / [sase-16n.11](sase-16n.11.md) / sase-16n.11.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-16n.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-16n.land.md) · **Assignee:** `sase-16n.11.2` · **Size:** medium
**Created:** 2026-09-23 08:51:47 EDT · **Closed:** 2026-09-23 10:30:49 EDT
**Plan:** [202609/project\_tags\_landing\_gaps.md](https://github.com/sase-org/sase--plans/blob/main/202609/project_tags_landing_gaps.md)

## Description

backend-fixes: `+home` resolves before home's spec exists; project_tag_for leaves unknown names alone; targets send state and workspace_dir over the wire; the completion cache follows current/MRU changes; doctor reports key case collisions with accurate wording; dead catalog code goes; the backend step-8 launch tests that were never written are added.

## Dependencies

- **Depends on:** [sase-16n.11.1](sase-16n.11.1.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-16n.11.3](sase-16n.11.3.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-16n.11.6](sase-16n.11.6.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16n.11.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.11.2/README.md) | [sase-16n.11.2](sase-16n.11.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`394a53b`](https://github.com/sase-org/sase/commit/394a53b6dfc5ee436073203fe71cb958d6b039e4) | feat(project-tags): Python tag backend fixes and step-8 launch tests | [sase-16n.11.2](sase-16n.11.2.md) | 2026-09-23 10:25:14 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16n.11.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.11.2/README.md

<!-- sase:referenced-by:end -->
