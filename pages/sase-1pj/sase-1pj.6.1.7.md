# Bead: sase-1pj.6.1.7 — Expose re-adoption and actionable held notifications

[Bead Pages](../README.md) / [sase-1pj.6.1](sase-1pj.6.1.md) / sase-1pj.6.1.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pj.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.6.md) · **Assignee:** `sase-1pj.6.1.7` · **Size:** small
**Created:** 2026-10-31 08:56:56 EDT · **Closed:** 2026-11-01 10:35:30 EST
**Plan:** [202610/staged\_handoff\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202610/staged_handoff_recovery.md)

## Description

readopt-cli: add sase agent readopt for one unambiguous originating turn, render recovery results and refusals, and include the exact command in held handoff notifications and focused user documentation.

## Notes

[2026-11-01T15:35:30Z · sase-1pj.6.1.7] Added explicit staged-handoff re-adoption with unique agent/session resolution, held notification commands, JSON output, docs, and generated CLI catalogs. Focused tests passed; sase tool run check passed with 59,552 tests after regeneration.

## Dependencies

- **Depends on:** [sase-1pj.6.1.6](sase-1pj.6.1.6.md) ✓ · ⧖ 2026-10-31
- **Blocks:** [sase-1pj.6.1.8](sase-1pj.6.1.8.md) ✓ · ⧖ 2026-10-31

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.6.1.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.6.1.7/README.md) | [sase-1pj.6.1.7](sase-1pj.6.1.7.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pj.6.1.6--1][1] | Need sibling phase scope for re-key decision | 1 |
| read-by | [agent:sase-1pj.6.1.7][2] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.6.1.6.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.6.1.7/README.md

<!-- sase:referenced-by:end -->
