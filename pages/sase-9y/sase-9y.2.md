# Bead: sase-9y.2 — Contention repro harness and load-robust visual convergence

[Bead Pages](../README.md) / [sase-9y](README.md) / sase-9y.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9y.2` · **Size:** medium
**Created:** 2026-07-27 10:58:06 UTC
**Plan:** [202607/fix\_ci\_bead\_isolation\_and\_visual\_flakes.md](https://github.com/sase-org/sase--plans/blob/main/202607/fix_ci_bead_isolation_and_visual_flakes.md)

## Description

visual-converge: build a repeatable contention harness that reproduces the visual snapshot flakes locally, then make render-convergence detection robust to CPU starvation instead of relying on a wall-clock quiet period.

## Notes

Added the test-visual-contention recipe with a fixed 26-worker/two-CPU harness and recorded pre/post measurements. Reworked wait_for_visual_idle to require five full Pilot CPU-idle/screen-drain cycles instead of a wall-clock quiet period, raised the starvation timeout to 15s, and normalized focused Input/TextArea cursor visibility. Added focused starvation regression coverage. Verification: focused tests 8 passed; CI-faithful serial visual suite 362 passed, 1 skipped in 17:57; violent harness improved from 116 failures to 15 with no convergence timeout, leaving capture/state races for sase-9y.3; just check passed.

## Dependencies

- **Blocks:** [sase-9y.3](sase-9y.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9y.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9y.2/README.md) | [sase-9y.2](sase-9y.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`a0636fc`](https://github.com/sase-org/sase/commit/a0636fcbbaf268c80434ef429b0caba6ccd19281) | fix: make visual convergence robust under CPU contention (sase-9y.2) | [sase-9y.2](sase-9y.2.md) | 2026-07-27 12:39:57 |
