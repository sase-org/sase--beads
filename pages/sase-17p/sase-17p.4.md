# Bead: sase-17p.4 — Stop, follow, and wait on a ToolRun by id

[Bead Pages](../README.md) / [sase-17p](README.md) / sase-17p.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qj](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qj.md) · **Assignee:** `sase-17p.4` · **Size:** medium
**Created:** 2026-09-24 08:40:23 EDT · **Closed:** 2026-09-24 12:18:38 EDT
**Plan:** [202609/tool\_e2\_durable\_handoff.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e2_durable_handoff.md)

## Description

lifecycle-controls: add sase tool stop, sase tool show -F/--follow, and sase tool wait as ownership-aware facades over the run's execution owner, with stop-requested versus stopped reporting and viewer-only interruption.

## Notes

[2026-09-24T16:18:38Z · sase-17p.4] stop/show -F/wait landed and verified: 21 new lifecycle tests pass; tests/tool+core-store 131 pass; handler/query/core 267 pass; ruff/mypy/fmt/keep-sorted/pyscripts/changelog/validate pass; live stop probe settles signaled/stop_requested with wait->1; epic-symbols clean

## Dependencies

- **Depends on:** [sase-17p.2](sase-17p.2.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17p.5](sase-17p.5.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17p.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17p.4/README.md) | [sase-17p.4](sase-17p.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`df8ed51`](https://github.com/sase-org/sase/commit/df8ed5134112a26735b501c5126593a1d40dd8d7) | feat(tool): stop, follow, and wait on a ToolRun by id (sase-17p.4) | [sase-17p.4](sase-17p.4.md) | 2026-09-24 12:20:14 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.3.1.land][1] | Check phase notes for already-recorded fakey color / completion snapshot / parser tool / monitor start policy failures | 1 |
| read-by | [agent:sase-17p.4][2] | Need the phase scope and design file | 2 |
| read-by | [agent:sase-17p.land][3] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.land/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17p.4/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17p.land/README.md

<!-- sase:referenced-by:end -->
