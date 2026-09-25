# Bead: sase-18g.2 — XPROMPT section travels with the detached identity

[Bead Pages](../README.md) / [sase-18g](README.md) / sase-18g.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0rk](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0rk.md) · **Assignee:** `sase-18g.2` · **Size:** medium
**Created:** 2026-09-24 17:41:30 EDT · **Closed:** 2026-09-24 19:33:28 EDT
**Plan:** [202609/agent\_header\_xprompt\_preview.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_header_xprompt_preview.md)

## Description

document: extend IdentityHeader with the xprompt, attach it instead of rendering the body section in the agent, family, and both hint paths when xprompt detachment is on (off by default), give the cheap j/k path a bounded memo plus a pending flag, and update the inline renderable and hint-cache key, with tests.

## Notes

[2026-09-24T23:29:32Z · sase-18g.2] PROPOSED FOLLOW-UP: Restore clean Symvision — just _lint-symvision still reports unchanged base symbols AgentSurvivorsError, Survivor, and environ_has_launch_key; active epic sase-18f tracks returning just check to green.

[2026-09-24T23:33:28Z · sase-18g.2] Implemented detachable highlighted XPROMPT identity content, hint-cache separation, and the bounded 128-entry cheap-path memo/pending state; 57 focused tests pass. sase tool run check passed format, Ruff, mypy, and all gates through terminology, then stopped only at three documented clean-base Symvision findings.

## Dependencies

- **Blocks:** [sase-18g.3](sase-18g.3.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18g.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18g.2/README.md) | [sase-18g.2](sase-18g.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4af219e`](https://github.com/sase-org/sase/commit/4af219ebae29fdc28715fbf7ecd9dbc1efccc9ad) | feat(ace): detach agent xprompts into identity headers | [sase-18g.2](sase-18g.2.md) | 2026-09-24 19:34:46 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-18g.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18g.2/README.md

<!-- sase:referenced-by:end -->
