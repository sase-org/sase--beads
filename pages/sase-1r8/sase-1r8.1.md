# Bead: sase-1r8.1 — Anchor the scanner rules and make scanner-hit blocks rules-versioned (sase-core)

[Bead Pages](../README.md) / [sase-1r8](README.md) / sase-1r8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.184](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.184.md) · **Assignee:** `sase-1r8.1` · **Size:** medium
**Created:** 2026-11-04 13:54:36 EST · **Closed:** 2026-11-04 14:43:50 EST
**Plan:** [202611/agent\_publication\_errors.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_publication_errors.md)

## Description

core: in sase-core, add a left token boundary to the prefix credential rules, bump the scanner rules version to 2, make a scanner-hit block enforced only while its evidence is current, supersede stale blocks with provenance on a clean rescan, add a parked-recheck predicate, and expose all of it through bindings with tests.

## Notes

[2026-11-04T19:43:50Z · sase-1r8.1] Core phase done and verified: scanner rules v2 with left token boundary on all prefix rules plus digit/upper shape check for sk-/sk-ant- keys and window-start guard; protection blocks rules-versioned with enforced lookup, stale retry, and supersede-with-provenance on clean rescan; parked-recheck predicate added; all exposed through sase_core_py bindings with round-trip tests. sase tool run check (run 4f7d81eee9fd8248fd990eefa2f082c0) green in sase-core; epic-symbols clean.

## Dependencies

- **Blocks:** [sase-1r8.4](sase-1r8.4.md) ◐ · ⧖ 2026-11-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1r8.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1r8.1.md) | [sase-1r8.1](sase-1r8.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1r8.1--1][1] | Need phase scope and design file for monitor follow-up close | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1r8.1.md

<!-- sase:referenced-by:end -->
