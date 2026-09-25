# Bead: sase-17m.2 — sase-core additive rename

[Bead Pages](../README.md) / [sase-17m](README.md) / sase-17m.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qh](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0qh.md) · **Assignee:** `sase-17m.2` · **Size:** large
**Created:** 2026-09-23 22:46:35 EDT · **Closed:** 2026-09-24 02:48:23 EDT
**Plan:** [202609/agent\_session\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_rename.md)

## Description

core-expand: non-breaking sase-core change. Rename the Rust internals to agent-session vocabulary and add the new pyo3 binding names alongside the old ones. Inputs accept both old and new spellings; serialized output stays byte-identical.

## Notes

[2026-09-24T06:49:02Z · sase-17m.2.1.land] Verified by sase-17m.2.1 land agent: child epic sase-17m.2.1 delivered the full core-expand scope (Rust internals renamed to agent-session, 4 new pyo3 binding names beside legacy ones, dual-spelling input, byte-identical output/goldens/schema versions); follow-ups routed to sase-17m.3 and sase-17m.8.

## Dependencies

- **Blocks:** [sase-17m.3](sase-17m.3.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17m.2.md) | [sase-17m.2](sase-17m.2.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.2.1.land][1] | Confirm parent phase close state | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.2.1.land/README.md

<!-- sase:referenced-by:end -->
