# Bead: sase-1kj.8 — Move the artifact-link walks into sase-core

[Bead Pages](../README.md) / [sase-1kj](README.md) / sase-1kj.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.102](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.102.md) · **Assignee:** `sase-1kj.8` · **Size:** large
**Created:** 2026-10-13 11:47:20 EDT · **Closed:** 2026-10-14 00:13:32 EDT
**Plan:** [202610/apollo\_tui\_startup.md](https://github.com/sase-org/sase--plans/blob/main/202610/apollo_tui_startup.md)

## Description

core-link-index: replace the Python per-row walks behind the app-wide LinkIndex and the Patch relation projection with a sase-core inverted index memoized by the aggregate signature, with single-flight Python adapters and a sase-core pin move.

## Dependencies

- **Depends on:** [sase-1kj.5](sase-1kj.5.md) ✓ · ⧖ 2026-10-13
- **Depends on:** [sase-1kj.6](sase-1kj.6.md) ✓ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kj.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kj.8.md) | [sase-1kj.8](sase-1kj.8.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1kj.8.1.3][1] | Need outer epic DECISIONS | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kj.8.1.3/README.md

<!-- sase:referenced-by:end -->
