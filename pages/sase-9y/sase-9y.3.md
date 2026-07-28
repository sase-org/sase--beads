# Bead: sase-9y.3 — Guarantee the compared PNG frame is the converged frame

[Bead Pages](../README.md) / [sase-9y](README.md) / sase-9y.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9y.3` · **Size:** medium
**Created:** 2026-07-27 10:58:31 UTC
**Plan:** [202607/fix\_ci\_bead\_isolation\_and\_visual\_flakes.md](https://github.com/sase-org/sase--plans/blob/main/202607/fix_ci_bead_isolation_and_visual_flakes.md)

## Description

visual-capture: eliminate the gap between the frame that convergence proved stable and the frame that is actually rasterized and compared, then fix whatever residual per-test races the hardened harness still exposes.

## Dependencies

- **Depends on:** [sase-9y.2](sase-9y.2.md) ✓
- **Blocks:** [sase-9y.4](sase-9y.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9y.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9y.3/README.md) | [sase-9y.3](sase-9y.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`57e3acb`](https://github.com/sase-org/sase/commit/57e3acb3a9ebf7fc777c1db799f09facbce5fd07) | test: harden ACE PNG snapshot convergence (sase-9y.3) | [sase-9y.3](sase-9y.3.md) | 2026-07-27 14:12:37 |
