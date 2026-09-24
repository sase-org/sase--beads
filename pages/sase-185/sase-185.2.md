# Bead: sase-185.2 — Hold and provider guards run after the bar unmounts

[Bead Pages](../README.md) / [sase-185](README.md) / sase-185.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0r6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0r6.md) · **Assignee:** `sase-185.2` · **Size:** medium
**Created:** 2026-09-24 15:03:18 EDT · **Closed:** 2026-09-24 16:28:52 EDT
**Plan:** [202609/detached\_prompt\_submit.md](https://github.com/sase-org/sase--plans/blob/main/202609/detached_prompt_submit.md)

## Description

detached-guards: move the acceptance point ahead of the `%hold` and hard-disabled-provider preflights, re-key both guards per pending launch with non-exclusive workers, and surface their decisions without stealing focus, restoring or stashing the prompt on abort.

## Dependencies

- **Depends on:** [sase-185.1](sase-185.1.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-185.3](sase-185.3.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-185.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-185.2.md) | [sase-185.2](sase-185.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`93d8d41`](https://github.com/sase-org/sase/commit/93d8d4140cea62629942839fa9eee8c962fcf5a0) | feat(ace): detach accepted agent launch guards | [sase-185.2](sase-185.2.md) | 2026-09-24 16:17:44 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-185.land][1] | Need the child scope and notes | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-185.land/README.md

<!-- sase:referenced-by:end -->
