# Bead: sase-1i5.2 — Break the prompt\_store\_mutations import cycle (sase-1h2)

[Bead Pages](../README.md) / [sase-1i5](README.md) / sase-1i5.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0y8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0y8.md) · **Assignee:** `sase-1i5.2` · **Size:** small
**Created:** 2026-10-08 09:47:18 EDT · **Closed:** 2026-10-08 10:22:36 EDT
**Plan:** [202610/close\_top\_ten\_impact\_task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202610/close_top_ten_impact_task_beads.md)

## Description

prompt-store-cycle: make importing sase.history.prompt_store_mutations order-independent, add fresh-interpreter regression tests for it and its lazy launch callers, and close sase-1h2.

## Notes

[2026-10-08T14:22:11Z · sase-1i5.2] PROPOSED FOLLOW-UP: sase tool run check (run cbac55cb958787b5959cd88abec06b87) reports 19 test failures that reproduce identically on the clean base tree with this phase edit stashed (isolated rerun: 14 failed, 43 passed both with and without the fix — terminology, finalizer-discard, multi_prompt_launcher_macro_groups x2, plan_approval_archive, claimed_status, plan_gates x2, plan_gates_execution, agent_meta_atomic, bead_fast_path x3; demand_runs, detach, gate_cli_answer_detach, import_budget, zsh_smoke pass in isolation and are load-flaky or owned elsewhere) — pre-existing master red including lanes owned by sibling phases sase-1i5.6 (sase-1f0) and sase-1i5.8 (sase-13p); land agent to triage.

[2026-10-08T14:22:36Z · sase-1i5.2] Import cycle broken via call-time facade imports in prompt_store_mutations.py (TYPE_CHECKING-only module import). Verified: cold mutations-first, store-first, and all 3 lazy-caller-first import orders succeed; new tests/history/test_prompt_store_import_cycle.py 5 passed; tests/history/ 484 passed; check lint gates (ruff, mypy, symvision, fmt) green; owned bead sase-1h2 closed done. Residual check test failures reproduce identically on clean base and are recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-1i5.9](sase-1i5.9.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1i5.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1i5.2/README.md) | [sase-1i5.2](sase-1i5.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e592f46`](https://github.com/sase-org/sase/commit/e592f46412d042d27a3f30b9489d946ad83eb6c1) | fix(history): break prompt\_store\_mutations import cycle (sase-1h2) | [sase-1i5.2](sase-1i5.2.md) | 2026-10-08 10:24:24 EDT |
