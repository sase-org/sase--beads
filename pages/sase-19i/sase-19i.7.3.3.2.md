# Bead: sase-19i.7.3.3.2 — Pass the approved open p95 budget

[Bead Pages](../README.md) / [sase-19i.7.3.3](sase-19i.7.3.3.md) / sase-19i.7.3.3.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-19i.7.3.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.7.3.land.md) · **Assignee:** `sase-19i.7.3.3.2` · **Size:** medium
**Created:** 2026-09-26 12:33:56 EDT · **Closed:** 2026-09-26 14:43:56 EDT
**Plan:** [202609/node\_finder\_open\_floor.md](https://github.com/sase-org/sase--plans/blob/main/202609/node_finder_open_floor.md)

## Description

open-budget: make the official 2,000-node open benchmark pass at p95 under 50 ms without relaxing the harness or the other budgets.

## Notes

[2026-09-26T18:42:55Z · sase-19i.7.3.3.2] PROPOSED FOLLOW-UP: open p95 still >50ms (steady snapshot ~50ms + Textual drain ~25ms; ~350ms full-GC stalls at loadavg ~20); remaining rocks are build_agent_tree regroup, drain pump rounds, and per-open GC churn

[2026-09-26T18:43:17Z · sase-19i.7.3.3.2] PROPOSED FOLLOW-UP: broad refilter p95 19-24ms over 16ms budget (steady filter ~7ms incl Rust scoring + modal rebuild ~5ms; GC stalls dominate tail)

[2026-09-26T18:43:34Z · sase-19i.7.3.3.2] PROPOSED FOLLOW-UP: just check blocked on base-identical failures: flags rule 7 sase-1ad card_blocks, 11 KNOWN symvision unused publics owned by sase-19x, 5 node-finder PNG failures owned by sase-19i

[2026-09-26T18:43:56Z · sase-19i.7.3.3.2] Cut open steady-state (snapshot 60->50ms p50, Tier0 clan preview 10->4.4ms) via from_facts wiring, plain-row fast path, keep-all fold fast path, memoized unmet chains, reason interning; 49 focused Node Finder tests green incl new plain-row differential; ruff/mypy/symvision-delta clean and epic-symbol resolved. Bench still red on this host (open p95 ~350 with GC stalls, steady ~80; broad p95 ~20): remaining work filed as follow-ups. just-check flags/symvision-KNOWN/PNG failures reproduce identically on base.

## Dependencies

- **Depends on:** [sase-19i.7.3.3.1](sase-19i.7.3.3.1.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19i.7.3.3.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.7.3.3.2/README.md) | [sase-19i.7.3.3.2](sase-19i.7.3.3.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`64b15bd`](https://github.com/sase-org/sase/commit/64b15bdf528a69094ccadd56c4dcfc854c08e53c) | perf(tui): cut node-finder open path for 50ms budget (sase-19i.7.3.3.2) | [sase-19i.7.3.3.2](sase-19i.7.3.3.2.md) | 2026-09-26 15:12:59 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-19i.7.3.3.1--1][1] | confirm later phase open to own from_facts whitelist | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.7.3.3.1.md

<!-- sase:referenced-by:end -->
