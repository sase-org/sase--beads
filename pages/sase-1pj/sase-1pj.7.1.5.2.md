# Bead: sase-1pj.7.1.5.2 — Preserve the actual origin across failed gate creation

[Bead Pages](../README.md) / [sase-1pj.7.1.5](sase-1pj.7.1.5.md) / sase-1pj.7.1.5.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pj.7.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.7.1.land.md) · **Assignee:** `sase-1pj.7.1.5.2` · **Size:** medium
**Created:** 2026-11-02 16:57:21 EST · **Closed:** 2026-11-02 18:17:11 EST
**Plan:** [202611/retention\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202611/retention_landing_repairs.md)

## Description

gate-origin: repair session-member creator identity and retain dirty origin work when detached gate publication fails.

## Notes

[2026-11-02T23:17:11Z · sase-1pj.7.1.5.2] Implemented exact root claim identity across live and staged gate creation; detached publication failures publish terminal state and retain/pin the matching origin while preserving primary and linked workspace edits. Synchronous failures retain notification compensation and claim restoration. Verified with 42 focused tests and successful sase tool run check (including 376 scoped test files); epic-symbol scan found no entries.

## Dependencies

- **Depends on:** [sase-1pj.7.1.5.1](sase-1pj.7.1.5.1.md) ✓ · ⧖ 2026-11-02
- **Blocks:** [sase-1pj.7.1.5.3](sase-1pj.7.1.5.3.md) ✓ · ⧖ 2026-11-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.7.1.5.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.7.1.5.2/README.md) | [sase-1pj.7.1.5.2](sase-1pj.7.1.5.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5dfd28c`](https://github.com/sase-org/sase/commit/5dfd28c74b2559cb61529291caf5691e25c0b6dd) | fix(gate-turn): preserve root claim origin on publication failure | [sase-1pj.7.1.5.2](sase-1pj.7.1.5.2.md) | 2026-11-02 18:18:18 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pj.7.1.5.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.7.1.5.2/README.md

<!-- sase:referenced-by:end -->
