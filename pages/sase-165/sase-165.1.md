# Bead: sase-165.1 — Pinned features, just fast, and a true MSRV in sase-core

[Bead Pages](../README.md) / [sase-165](README.md) / sase-165.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0p2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0p2.md) · **Assignee:** `sase-165.1` · **Size:** medium
**Created:** 2026-09-22 08:18:21 EDT · **Closed:** 2026-09-22 11:01:06 EDT
**Plan:** [202609/sase\_core\_p0\_agent\_maintainability.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_core_p0_agent_maintainability.md)

## Description

core-fast-loop: in sase-core, unify dependency features with a cargo-hakari workspace-hack plus a tool-free check.sh features gate (also run in CI). Add `just fast`, and make rust-version true by deleting the incompatible_msrv allows. Measure a ≤5 s no-edit -p scope switch.

## Notes

[2026-09-22T16:40:53Z · sase-165.land] Land-agent record (measurements were in commit 1d129cd's message, not a bead note): cold check 85s, no-edit -p scope switches <=0.42s (target <=5s: MET), just check 4085 passed. Re-verified 2026-09-22: ./scripts/check.sh features passes at 035851e; rust-version 1.89 with 0 incompatible_msrv allows; CI runs the features step on both OS legs.

## Dependencies

- **Blocks:** [sase-165.2](sase-165.2.md) ✓ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-165.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-165.1/README.md) | [sase-165.1](sase-165.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@1d129cd`](https://github.com/sase-org/sase-core/commit/1d129cd24fdb42e1906d32ddea89d416f6a61c05) | feat(fast-loop): unify features via workspace-hack, add drift gate, just fast, true MSRV 1.89 | [sase-165.1](sase-165.1.md) | 2026-09-22 10:16:33 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-165.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-165.1/README.md

<!-- sase:referenced-by:end -->
