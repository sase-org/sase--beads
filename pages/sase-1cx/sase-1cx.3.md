# Bead: sase-1cx.3 — Starter-scoped detached runs and sase tool run --detach

[Bead Pages](../README.md) / [sase-1cx](README.md) / sase-1cx.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u3.md) · **Assignee:** `sase-1cx.3` · **Size:** large
**Created:** 2026-09-29 20:32:16 EDT · **Closed:** 2026-09-30 11:16:05 EDT
**Plan:** [202609/tool\_run\_escalation.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_run_escalation.md)

## Description

detach-run: pin the new core, create the `tool_run_escalation` beta flag, and share one hand-off launcher between `-H` and the new agent-only `-d/--detach`. Scope detached runs to their starter runner with a worker watchdog and an end-of-invocation cleanup. Suppress their settlement notification and render `starter`/`join` in `sase tool show`.

## Notes

[2026-09-30T15:15:43Z · sase-1cx.3--2] PROPOSED FOLLOW-UP: 'sase tool run check' (just check) failed twice in 'just _setup' final line (_setup-required-plugins, exit 1) with zero product-test or lint failures — both runs spent ~15-17min rebuilding sase_core_rs after the linked sase-core checkout moved mid-session (0.36.0 then 0.36.1); tools/setup_required_plugins passes standalone (exit 0) immediately after each failure, so the _setup failure is transient orchestration flake, not the detach diff. Separately, tests/completion/test_candidates_project_providers.py::test_bead_candidates_without_a_store_returns_empty_list fails in this agent environment (bead store leaks via env) and reproduces on the stashed clean base — pre-existing, not ours; left untouched.

[2026-09-30T15:16:05Z · sase-1cx.3--2] detach-run done. just check could not complete: two runs failed ONLY in 'just _setup' final line (_setup-required-plugins exit 1, transient — passes standalone exit 0 each time) after long sase_core_rs rebuilds triggered by sase-core checkout moves mid-session (0.36.0/0.36.1); no product-test or lint failures in either run. Targeted evidence instead: 127 passed (test_detach 19 incl. new DoD-17 cases, test_handoff, test_lifecycle_controls, test_routing, completion build/zsh/candidates), ruff clean on all touched files, hermetic smoke 60 pass/0 fail, 'sase bead epic-symbols sase-1cx.3' empty. Fixed one real gap found during verification: test_mutex_groups_found 19->20 for the new tool/run [detach, hand_off] mutex group (confirmed ours; 19 still passes on clean base). Known pre-existing, untouched: bead-candidates env test (fails on clean base too) and symvision _kitty_graphics_support in checks_deep_terminal.py. Flag bead sase-1dc covers tool_run_escalation follow-ups.

## Dependencies

- **Depends on:** [sase-1cx.1](sase-1cx.1.md) ✓ · ⧖ 2026-09-29
- **Blocks:** [sase-1cx.4](sase-1cx.4.md) ✓ · ⧖ 2026-09-29
- **Blocks:** [sase-1cx.5](sase-1cx.5.md) ✓ · ⧖ 2026-09-29
- **Blocks:** [sase-1cx.6](sase-1cx.6.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cx.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1cx.3.md) | [sase-1cx.3](sase-1cx.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`018061f`](https://github.com/sase-org/sase/commit/018061f6f28a05fb35386d63e9a050fe57251f09) | feat(tool): implement starter scoped tool runs with detach and handoff | [sase-1cx.3](sase-1cx.3.md) | 2026-09-30 11:42:24 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1cx.3--2][1] | verification follow-up for detach-run phase: need bead state and evidence before close | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1cx.3.md

<!-- sase:referenced-by:end -->
