# Bead: sase-g3.1 — Historical backtest of selection recall against coverage ground truth

[Bead Pages](../README.md) / [sase-g3](README.md) / sase-g3.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tx](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tx/README.md) · **Assignee:** `sase-g3.1` · **Size:** medium
**Created:** 2026-08-06 08:55:18 EDT
**Plan:** [202608/selection\_soundness.md](https://github.com/sase-org/sase--plans/blob/main/202608/selection_soundness.md)

## Description

backtest: add a `tools/selection_backtest` harness (plus a `just selection-backtest` recipe) that replays the last N real commits, computes the selection each diff would have produced, and reports recall against per-test coverage-context ground truth — so the epic's unmet exit criterion is answerable now rather than after weeks of organic sample growth.

## Dependencies

- **Blocks:** [sase-g3.3](sase-g3.3.md) ◐ · ⧖ 2026-08-06
- **Blocks:** [sase-g3.5](sase-g3.5.md) ◐ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-g3.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-g3.1/README.md) | [sase-g3.1](sase-g3.1.md) | 0 |
