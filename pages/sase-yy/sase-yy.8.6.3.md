# Bead: sase-yy.8.6.3 — Repair bead projections from complete event truth

[Bead Pages](../README.md) / [sase-yy.8.6](sase-yy.8.6.md) / sase-yy.8.6.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-yy.8.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-yy.8.land.md) · **Assignee:** `sase-yy.8.6.3` · **Size:** medium
**Created:** 2026-09-11 06:54:39 EDT · **Closed:** 2026-09-11 08:55:06 EDT
**Plan:** [202609/artifact\_link\_durable\_truth\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/artifact_link_durable_truth_repairs.md)

## Description

projection_convergence: separate occurrence deduplication from state projection so old receipts cannot suppress a necessary converged projection.

## Notes

[2026-09-11T12:53:06Z · sase-yy.8.6.3] PROPOSED FOLLOW-UP: Repair live flag bead sase-z6 - primary just check fails feature flag rule 8 because key ace_unified_agents has no registry definition; bead sase-z9 remains warning-only.

[2026-09-11T12:55:06Z · sase-yy.8.6.3] Verified core projection repair with cargo test -p sase_core link_projection_receipt_does_not_hide_changed_reduced_state, neighboring direction receipt test, Python SDD projection/event suites (11 passed), primary install, and core just check. Primary just check is still blocked by unrelated feature flag bead sase-z6; recorded PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-yy.8.6.2](sase-yy.8.6.2.md) ✓ · ⧖ 2026-09-11
- **Blocks:** [sase-yy.8.6.4](sase-yy.8.6.4.md) ✓ · ⧖ 2026-09-11
- **Blocks:** [sase-yy.8.6.6](sase-yy.8.6.6.md) ✓ · ⧖ 2026-09-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-yy.8.6.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-yy.8.6.3/README.md) | [sase-yy.8.6.3](sase-yy.8.6.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8f6e653`](https://github.com/sase-org/sase/commit/8f6e65361d1803160446bb3bdff16c061c7fa050) | test(sdd): cover bead projection convergence | [sase-yy.8.6.3](sase-yy.8.6.3.md) | 2026-09-11 08:56:55 EDT |
| sase-core | [`sase-core@b8ec0cb`](https://github.com/sase-org/sase-core/commit/b8ec0cb2170fc2da4b1eb64b8dbc4b13a4e1bad6) | fix(bead): repair projection receipt convergence | [sase-yy.8.6.3](sase-yy.8.6.3.md) | 2026-09-11 09:00:36 EDT |
