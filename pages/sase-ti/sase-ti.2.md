# Bead: sase-ti.2 — Baseline every checkout that exists before the first turn

[Bead Pages](../README.md) / [sase-ti](README.md) / sase-ti.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0d9](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0d9.md) · **Assignee:** `sase-ti.2` · **Size:** medium
**Created:** 2026-08-25 07:37:56 EDT · **Closed:** 2026-08-25 08:40:08 EDT
**Plan:** [202608/commit\_finalizer\_protection\_truth.md](https://github.com/sase-org/sase--plans/blob/main/202608/commit_finalizer_protection_truth.md)

## Description

checkouts: snapshot every repository checkout already present in the workspace at runner start rather than only the dirty ones, and make a later repo open unable to rebase an existing record for the same path onto the agent's own work.

## Notes

[2026-08-25T12:40:08Z · sase-ti.2] Implemented runner-start baselines for clean pre-existing checkouts plus path-idempotent late opens; verified focused baseline/live/bootstrap tests, just _lint-symvision, and just check.

## Dependencies

- **Depends on:** [sase-ti.1](sase-ti.1.md) ✓ · ⧖ 2026-08-25
- **Blocks:** [sase-ti.6](sase-ti.6.md) ✓ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ti.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ti.2/README.md) | [sase-ti.2](sase-ti.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`222a11e`](https://github.com/sase-org/sase/commit/222a11ea0d19603031071abddebd30e44f41435f) | fix(finalizer): baseline pre-existing checkouts | [sase-ti.2](sase-ti.2.md) | 2026-08-25 08:41:40 EDT |
