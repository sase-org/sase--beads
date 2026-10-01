# Bead: sase-1dr.4.1.1 — Subject identity, shim aliasing, and the fixture corpus

[Bead Pages](../README.md) / [sase-1dr.4.1](sase-1dr.4.1.md) / sase-1dr.4.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1dr.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1dr.4.md) · **Assignee:** `sase-1dr.4.1.1` · **Size:** medium
**Created:** 2026-09-30 20:38:51 EDT · **Closed:** 2026-09-30 21:24:27 EDT
**Plan:** [202609/memory\_history\_core.md](https://github.com/sase-org/sase--plans/blob/main/202609/memory_history_core.md)

## Description

subjects: derive note, web, strand, instructions, and asset identity from file_history lineages, alias each shim version into its instructions subject by blob equality, and build the fixture corpus later phases assert against.

## Notes

[2026-10-01T01:23:58Z · sase-1dr.4.1.1] PROPOSED FOLLOW-UP: sase-core gate clippy fails on clean base (clippy 1.95.0 nonminimal_bool/manual-range-contains etc. in tool_run/store/triage.rs, provider_usage, finalizer, agent_runtime, agent_scan, fleet_owner_facts) — toolchain drift, no flake bead tracks it

[2026-10-01T01:24:27Z · sase-1dr.4.1.1] subjects phase done: memory_history module (wire/subjects/tests-corpus) in sase-core; 6/6 subject tests pass, fmt clean, new files clippy-clean; full gate blocked only by 9 pre-existing clippy-1.95 failures verified identical on clean base (recorded as PROPOSED FOLLOW-UP); no epic-symbol entries

## Dependencies

- **Blocks:** [sase-1dr.4.1.2](sase-1dr.4.1.2.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1dr.4.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.4.1.1/README.md) | [sase-1dr.4.1.1](sase-1dr.4.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@26ffc55`](https://github.com/sase-org/sase-core/commit/26ffc55d33c3c25a8a0806834cc51e9e6349ed7e) | feat(memory-history): subject identity, shim aliasing, and fixture corpus | [sase-1dr.4.1.1](sase-1dr.4.1.1.md) | 2026-09-30 21:26:16 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1dr.4.1.1][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1dr.4.1.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.4.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.4.1.land/README.md

<!-- sase:referenced-by:end -->
