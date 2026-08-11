# Bead: sase-j7.4 — Fix every inventoried leak and root-cause the residual flakes

[Bead Pages](../README.md) / [sase-j7](README.md) / sase-j7.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-j0.w1.f0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j0.w1.f0/README.md) · **Assignee:** `sase-j7.4` · **Size:** large
**Created:** 2026-08-10 15:44:51 EDT · **Closed:** 2026-08-10 20:12:50 EDT
**Plan:** [202608/fix\_sase\_ct\_flake\_class.md](https://github.com/sase-org/sase--plans/blob/main/202608/fix_sase_ct_flake_class.md)

## Description

fix-leaks - fix every poisoning leak in the inventory by mechanism, deterministically reproduce and fix the bead-cluster and plan-approval nodes whose cause is not yet known, and flip the leak detector into a blocking gate so the class cannot recur.

## Notes

[2026-08-11T00:12:50Z · sase-j7.4] Verified with focused detector and runner tests; direct full cost lane passed with zero global-state poisoning; just check passed; just check-full passed through test-cost and failed only the existing flake-baseline gate for ready tasks sase-jb and sase-j6, with corroboration recorded.

## Dependencies

- **Depends on:** [sase-j7.1](sase-j7.1.md) ✓ · ⧖ 2026-08-10
- **Depends on:** [sase-j7.2](sase-j7.2.md) ✓ · ⧖ 2026-08-10
- **Blocks:** [sase-j7.5](sase-j7.5.md) ◐ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-j7.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-j7.4.md) | [sase-j7.4](sase-j7.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6385a8e`](https://github.com/sase-org/sase/commit/6385a8ebb16d6315b2fd74fd4ef47b630f516ace) | test: gate cost lane on global-state leak detector | [sase-j7.4](sase-j7.4.md) | 2026-08-10 20:14:05 EDT |
