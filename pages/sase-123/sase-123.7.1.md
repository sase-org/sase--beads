# Bead: sase-123.7.1 — Restore one renderer for screenshots and visual snapshots

[Bead Pages](../README.md) / [sase-123.7](sase-123.7.md) / sase-123.7.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-123.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-123.land.md) · **Assignee:** `sase-123.7.1` · **Size:** small
**Created:** 2026-09-17 21:13:50 EDT
**Plan:** [202609/complete\_tui\_screenshots.md](https://github.com/sase-org/sase--plans/blob/main/202609/complete_tui_screenshots.md)

## Description

canonical-renderer: remove the test-side rasterizer copy reintroduced by concurrent commits and repoint visual helpers and fingerprints to the packaged runtime renderer without changing pixels.

## Notes

[2026-09-18T02:01:04Z · sase-123.7.1] PROPOSED FOLLOW-UP: Gate decision tests are stale against Rust current-failure validation — `just check` escalated to the full non-visual suite and failed only `tests/test_gate_cli_show.py::test_show_reports_an_accepted_failed_gate` plus two `tests/test_gate_decision_acceptance.py` cases because their synthetic `attempt_failed` journal entries use an empty `attempt_id`, which `sase_core_rs 0.34.50` rejects as `execution_facts.current_failure.attempt_id must be nonempty`.

## Dependencies

- **Blocks:** [sase-123.7.5](sase-123.7.5.md) ◐ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-123.7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-123.7.1/README.md) | [sase-123.7.1](sase-123.7.1.md) | 0 |
