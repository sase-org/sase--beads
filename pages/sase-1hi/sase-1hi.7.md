# Bead: sase-1hi.7 — Telegram decision sheet, live keyboard, and settle receipt

[Bead Pages](../README.md) / [sase-1hi](README.md) / sase-1hi.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.5n](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.5n.md) · **Assignee:** `sase-1hi.7` · **Size:** large
**Created:** 2026-10-07 18:48:30 EDT
**Plan:** [202610/plan\_decisions.md](https://github.com/sase-org/sase--plans/blob/main/202610/plan_decisions.md)

## Description

telegram: in the linked sase-telegram repo, render the static question sheet, the live set-value decision keyboard with choice sub-keyboards and the summarizing primary button, revision-bound submits with a stale-card refresh, the one-time settle edit, quiet `%auto` receipts, the feedback reply fix, decision-aware PDFs, and typed-origin agent launches.

## Notes

[2026-10-08T06:17:25Z · sase-1hi.7] PROPOSED FOLLOW-UP: Telegram gate-integration tests (new test_plan_decisions.py envelope tests and existing test_custom_gates.py gate tests) fail in this workspace with RuntimeError: sase_core_rs content-layout wire is stale: expected schema >= 7 for macro layout, got 5 (src/sase/core/content_layout_wire.py:227 via notification_gates/service.py _start_gate_creation -> config/core.py _compute_current_config_token). Reproduces identically on unchanged clean telegram base: git stash -u, pytest tests/test_custom_gates.py::test_hitl_uses_the_same_renderer_and_executor -> same FAILED; git stash pop restores work. Evidence: .venv/bin/python -m pytest tests/test_custom_gates.py::test_hitl... -x -q. Ruff + mypy on touched files pass; pure-unit decision tests (receipt filter, PDF preprocess, typed origin) pass 3/3. Needs: refresh installed sase_core_rs / content-layout wire in telegram venv (just install / rust-install) then re-run gate tests.

## Dependencies

- **Depends on:** [sase-1hi.4](sase-1hi.4.md) ✓ · ⧖ 2026-10-07
- **Blocks:** [sase-1hi.9](sase-1hi.9.md) ◐ · ⧖ 2026-10-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1hi.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.7.md) | [sase-1hi.7](sase-1hi.7.md) | 0 |
