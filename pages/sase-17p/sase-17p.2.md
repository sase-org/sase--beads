# Bead: sase-17p.2 — Hand a ToolRun off to a plain durable proc with sase tool run -H

[Bead Pages](../README.md) / [sase-17p](README.md) / sase-17p.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qj](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qj.md) · **Assignee:** `sase-17p.2` · **Size:** large
**Created:** 2026-09-24 08:40:21 EDT · **Closed:** 2026-09-24 11:42:17 EDT
**Plan:** [202609/tool\_e2\_durable\_handoff.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e2_durable_handoff.md)

## Description

standalone-handoff: split the executor so one body serves foreground and adopted runs, add the hidden claim-then-run worker and the shared launch module, and ship fail-closed sase tool run -H outside agents over a plain proc, behind the tool_handoff beta flag.

## Dependencies

- **Depends on:** [sase-17p.1](sase-17p.1.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17p.3](sase-17p.3.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17p.4](sase-17p.4.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17p.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17p.2.md) | [sase-17p.2](sase-17p.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c0591ad`](https://github.com/sase-org/sase/commit/c0591adf203646bbe36a723a5592b0d4275c6863) | feat(tool): standalone hand-off of ToolRun via sase tool run -H | [sase-17p.2](sase-17p.2.md) | 2026-09-24 11:40:31 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17p.3][1] | check dependency status | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17p.3/README.md

<!-- sase:referenced-by:end -->
