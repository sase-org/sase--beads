# Bead: sase-1ex.1 — Prompt-key perf instrumentation, benchmark, and I/O probes

[Bead Pages](../README.md) / [sase-1ex](README.md) / sase-1ex.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vk](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vk.md) · **Assignee:** `sase-1ex.1` · **Size:** small
**Created:** 2026-10-02 14:53:44 EDT · **Closed:** 2026-10-02 16:49:30 EDT
**Plan:** [202610/prompt\_space\_and\_project\_cycle\_latency.md](https://github.com/sase-org/sase--plans/blob/main/202610/prompt_space_and_project_cycle_latency.md)

## Description

key-perf-harness: record `SASE_TUI_PERF` key-to-paint samples for `<space>`, `ctrl+n`, and `ctrl+p`; add a slow bench plus a non-slow smoke test; add a main-thread I/O probe helper that later phases use for zero-I/O tests; record a baseline.

## Notes

[2026-10-02T20:48:34Z · sase-1ex.1] BASELINE (bench_prompt_bar_keys.py, shared host, run 2026-10-02; paint_ms / handler_ms): first_space n=1: 321.02 / 280.75; steady_space n=10: p50 168.58 / 132.35, p95 242.86 / 190.60; single_ctrl_p n=1: 518.44 / 509.89; burst_ctrl_p n=6: p50 369.54 / 357.65, p95 500.79 / 494.47; first_visit_ctrl_p n=1: 451.68 / 442.31; stall-watchdog rows: 0. Caveats: host load was high (load1 ~37 during the gate window); bench ran with compat stubs (empty agent-scan snapshot; empty tab catalog and empty Jinja scope-vars only when the installed wheel lacks those bindings) because the workspace venv sase-core-rs wheel (0.34.53, bumped to 0.35.1 during this phase to match pyproject floor >=0.35.0,<0.36.0) predates checkout bindings (local sase-core is 0.36.3). Later phases rerun the same bench for before/after.

[2026-10-02T20:49:09Z · sase-1ex.1] PROPOSED FOLLOW-UP: workspace venvs pin a stale sase-core-rs wheel (0.34.53 installed vs pyproject floor >=0.35.0; even 0.35.1 lacks ~46 bindings the checkout calls: scan-wire schema 9 vs 10/11, build_agent_tab_catalog, jinja_*). Full-app TUI tests fail without a source build from the linked sase-core checkout (0.36.3); this phase added binding-missing-conditional compat stubs to the prompt bench/smoke to stay green. Possibly tracked under sase-18s (test-scoped failures on clean master, stale binding suspected).

[2026-10-02T20:49:30Z · sase-1ex.1] key-perf-harness done: SASE_TUI_PERF samples for prompt_space/prompt_cycle_ctrl_p/n wired (cycle begin in _handle_vcs_mru_cycle_key after completion decline, space begin at action entry, mount-path completion); slow bench runs end-to-end with baseline in bead notes; non-slow smoke 4 passed; probe helper covered by self-test; ruff/mypy/symvision/prettier green; sase tool run check: all lint stages pass, test lane 51649 passed with 3 load-flake failures that pass on retry (incl. demand-runs on this tree). One pre-existing cycling-widget failure reproduces identically on clean base (stale wheel, noted as follow-up).

## Dependencies

- **Blocks:** [sase-1ex.2](sase-1ex.2.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1ex.5](sase-1ex.5.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1ex.6](sase-1ex.6.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1ex.9](sase-1ex.9.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ex.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ex.1/README.md) | [sase-1ex.1](sase-1ex.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`db40a72`](https://github.com/sase-org/sase/commit/db40a7219ac0e14d14e9965fa968ee58bc88884b) | feat(tui-perf): add prompt-key perf harness with recorded baseline | [sase-1ex.1](sase-1ex.1.md) | 2026-10-02 16:52:09 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ex.1][1] | check existing notes and implementation status | 2 |
| read-by | [agent:sase-1ex.12][2] | Need key-perf-harness baseline table | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ex.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ex.12/README.md

<!-- sase:referenced-by:end -->
