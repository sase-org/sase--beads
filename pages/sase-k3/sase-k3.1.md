# Bead: sase-k3.1 — Durable startup telemetry

[Bead Pages](../README.md) / [sase-k3](README.md) / sase-k3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yo](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yo/README.md) · **Assignee:** `sase-k3.1` · **Size:** small
**Created:** 2026-08-12 11:36:33 EDT · **Closed:** 2026-08-12 12:45:11 EDT
**Plan:** [202608/ace\_startup\_critical\_path.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_startup_critical_path.md)

## Description

telemetry: record one JSONL row per ACE session carrying both a visible-surface-ready and an all-surfaces-ready time plus the component budget, make the loader-stage log threshold env-overridable so sub-2 s stages are capturable, and document the before/after capture recipe.

## Notes

[2026-08-12T16:44:12Z · sase-k3.1] PROPOSED FOLLOW-UP: Justfile _lint-symvision epic-symbol whitelist references closed bead sase-js (5 entries) — just check/-full now hard-fails on `just lint (symvision)` for every agent, unrelated to any in-flight diff; remove the stale --epic-symbol entries (and their now-untracked symbols if truly dead) from Justfile lines 306-310/? and the check-full mirror.

[2026-08-12T16:44:48Z · sase-k3.1] PROPOSED FOLLOW-UP: tests/test_multi_prompt_launcher_xprompt_groups.py::test_launcher_qualifies_research_swarm_per_dispatch is order-dependent — passes standalone and in its own file every time, but intermittently fails when run as part of the full just test-scoped suite; likely shared/global state leaking across test modules.

[2026-08-12T16:45:11Z · sase-k3.1] Implemented durable startup telemetry: StartupTelemetryMixin (_startup_telemetry.py) records one tui_startup.jsonl row per session with agents_ready/axe_ready/visible_ready/all_surfaces_ready seconds plus tier/artifact_source/record_count; added record_count to AgentLoadState and env-overridable loader-stage threshold (SASE_TUI_SLOW_LOADER_STAGE_SECONDS); wired mount/first-paint/agents-ready/axe-ready marks into startup.py and documented the before/after capture recipe in docs/perf_runbook.md. Verified: just fmt/lint-ruff/lint-mypy/lint-pyscripts/lint-test-waits/lint-changelog/lint-patch-stitch-terminology/validate/validate-committed-plans all pass; just test-scoped (9155 tests) passes after fixing two real regressions my mount/first-paint wiring exposed in tests/ace/tui/test_startup_stopwatch_live_update.py and tests/ace/tui/test_dismissed_index_startup_sync.py (hand-rolled harnesses missing the new _mark_startup_first_paint stub). Remaining just check failure is lint(symvision) referencing closed bead sase-js, pre-existing and unrelated (filed as follow-up); one launcher test is a pre-existing order-dependent flake (also filed).

## Dependencies

- **Blocks:** [sase-k3.3](sase-k3.3.md) ◐ · ⧖ 2026-08-12
- **Blocks:** [sase-k3.4](sase-k3.4.md) ◐ · ⧖ 2026-08-12
- **Blocks:** [sase-k3.5](sase-k3.5.md) ✓ · ⧖ 2026-08-12
- **Blocks:** [sase-k3.6](sase-k3.6.md) ◐ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-k3.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-k3.1/README.md) | [sase-k3.1](sase-k3.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`59967cc`](https://github.com/sase-org/sase/commit/59967cc062a72e179f66188b7a106644656fb61c) | feat(ace): record durable per-session startup telemetry (sase-k3.1) | [sase-k3.1](sase-k3.1.md) | 2026-08-12 12:46:08 EDT |
