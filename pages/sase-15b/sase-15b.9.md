# Bead: sase-15b.9 — Split crates/sase\_core/src/runner\_capacity.rs

[Bead Pages](../README.md) / [sase-15b](README.md) / sase-15b.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oh.r0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oh.r0.md) · **Assignee:** `sase-15b.9` · **Size:** medium
**Created:** 2026-09-21 11:31:49 EDT · **Closed:** 2026-09-21 17:50:25 EDT
**Plan:** [202609/sase\_core\_next\_ten\_big\_file\_split.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_core_next_ten_big_file_split.md)

## Description

runner_capacity: decompose the 2,938-line runner capacity policy module into wire, claims/lineage, waiters, candidate decision, holds, and capacity math submodules under runner_capacity/.

## Notes

[2026-09-21T21:50:25Z · sase-15b.9] Split 2,938-line runner_capacity.rs into runner_capacity/ tree (largest 468 lines); all 43 tests moved whole and passing; just check exit 0 with 33 ok suites; lib.rs untouched, public API preserved via mod.rs re-exports

## Dependencies

- **Blocks:** [sase-15b.10](sase-15b.10.md) ✓ · ⧖ 2026-09-21
- **Depends on:** [sase-15b.8](sase-15b.8.md) ✓ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-15b.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-15b.9/README.md) | [sase-15b.9](sase-15b.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@f54b2ba`](https://github.com/sase-org/sase-core/commit/f54b2ba4cb7c38739f0a9c5c202ca1a4077de9d4) | refactor(sase-core): split runner\_capacity into module tree | [sase-15b.9](sase-15b.9.md) | 2026-09-21 17:52:24 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.24.cld][1] | research sase-core agent maintainability (split epic phase evidence) | 1 |
| read-by | [agent:sase-15b.9][2] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-15b.land][3] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.24.cld/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-15b.9/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-15b.land/README.md

<!-- sase:referenced-by:end -->
