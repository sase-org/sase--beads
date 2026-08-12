# Bead: sase-k0.4.1 — Complete the promised convergence regression coverage

[Bead Pages](../README.md) / [sase-k0.4](sase-k0.4.md) / sase-k0.4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-k0.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-k0.land/README.md) · **Assignee:** `sase-k0.4.1` · **Size:** small
**Created:** 2026-08-12 12:46:28 EDT · **Closed:** 2026-08-12 13:05:12 EDT
**Plan:** [202608/finish\_task\_gate\_convergence.md](https://github.com/sase-org/sase--plans/blob/main/202608/finish_task_gate_convergence.md)

## Description

convergence_regressions: add the removed-then-re-enabled fresh-g1 and cross-project-key exact-convergence regressions promised by the original plan, fixing implementation defects if either regression exposes one, and rerun the focused task-gate suites.

## Notes

[2026-08-12T17:05:12Z · sase-k0.4.1] Added the two promised task-gate convergence regressions in tests/test_axe_chop_bead_task_triage.py: removed-then-re-enabled projects cancel stale state and restart at a fresh -g1 request id, and the same live bead under a different project key cancels the stale project gate while leaving exactly one expected live gate. Verified focused task-gate suites: 56 passed in 2.72s. Verified repository gate: just check passed, including full-suite escalation from scoped selection (core-identity-changed). No production reconciler changes were needed.

[2026-08-12T17:06:17Z · sase-k0.4.1] Verified focused task-gate suites passed (56 tests) and just check passed with scoped tests escalating to the full suite.

## Dependencies

- **Blocks:** [sase-k0.4.2](sase-k0.4.2.md) ◐ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-k0.4.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-k0.4.1/README.md) | [sase-k0.4.1](sase-k0.4.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9960d74`](https://github.com/sase-org/sase/commit/9960d7444062db28ce0bf8ee08011ace31272407) | test: cover task triage project-state convergence | [sase-k0.4.1](sase-k0.4.1.md) | 2026-08-12 13:11:21 EDT |
