# Bead: sase-1ex.6 — Run each prompt text-area mount, unmount, and worker hook once

[Bead Pages](../README.md) / [sase-1ex](README.md) / sase-1ex.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vk](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vk.md) · **Assignee:** `sase-1ex.6` · **Size:** medium
**Created:** 2026-10-02 14:53:51 EDT · **Closed:** 2026-10-02 19:36:42 EDT
**Plan:** [202610/prompt\_space\_and\_project\_cycle\_latency.md](https://github.com/sase-org/sase--plans/blob/main/202610/prompt_space_and_project_cycle_latency.md)

## Description

mount-dedup: replace the mixins' super-chained, Textual-dispatched `on_mount`, `on_unmount`, and `on_worker_state_changed` handlers with cooperative hooks that are dispatched once. Body order and theme layering stay the same, and goldens stay unchanged.

## Notes

[2026-10-02T21:36:30Z · sase-1ex.6] Pre-change probe: 16 on_mount definers in PromptTextArea MRO; body runs triangular (Yank x1 ... DirectiveWorker x14, ScrollView x22 incl. app noise); first-run order base-first; theme=sase-jinja-prompt

[2026-10-02T21:37:44Z · sase-1ex.6] Bench BEFORE (bench_prompt_bar_keys): first_space paint 551ms; steady_space p50 184ms p95 262ms; single_ctrl_p 536ms; burst p50 239ms p95 427ms; first_visit 484ms; 0 stall rows

[2026-10-02T21:47:39Z · sase-1ex.6] Bench AFTER (2 runs): steady_space p50 167/145ms p95 192/189ms vs before 184/186 p50, 262/220 p95 (-19..-41ms p50, directionally at research -25..-35ms); n=1 cases swing wildly (first_space 629/273, single 1067/104) = host noise; burst elevation reproduces on stashed old code (380ms) = host drift, not a regression; first_visit flat ~492ms; 0 stall rows

[2026-10-02T21:58:29Z · sase-1ex.6] PROPOSED FOLLOW-UP: agents_tribe_panel_prompts glance/inspect PNG goldens drift on clean base too (extra sase project-tag prefix in (no Patch) row) — needs a golden refresh or tribe async-settle fix outside this phase

[2026-10-02T23:36:42Z · sase-1ex.6--1] mount-dedup done: cooperative _prompt_mount/unmount/worker hooks dispatched once from LineRenderingMixin; 15 mount + 3 unmount bodies run once base-first; theme parity kept. Verified: test_prompt_mount_dedup 9 passed; prompt highlight/completion sweep 135 passed; catalog_warm+dedup 13 passed; ruff clean; mypy _line_rendering clean; just check lints/SASE-validation/committed-plans all green, test-scoped timed out after 1h (signal 15, no failure). epic-symbols clean, no goldens touched.

## Dependencies

- **Depends on:** [sase-1ex.1](sase-1ex.1.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1ex.11](sase-1ex.11.md) ◐ · ⧖ 2026-10-02
- **Blocks:** [sase-1ex.7](sase-1ex.7.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ex.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ex.6.md) | [sase-1ex.6](sase-1ex.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`24cff91`](https://github.com/sase-org/sase/commit/24cff91cd3e5a737d417a5b32cd38835a4125fae) | feat(tui): dispatch prompt mount/unmount/worker hooks once (sase-1ex.6) | [sase-1ex.6](sase-1ex.6.md) | 2026-10-02 19:39:47 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ex.6--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ex.6.md

<!-- sase:referenced-by:end -->
