# Bead: sase-g3.2 — Make the scoped lane's selection and degradation visible on the success path

[Bead Pages](../README.md) / [sase-g3](README.md) / sase-g3.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tx](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tx/README.md) · **Assignee:** `sase-g3.2` · **Size:** small
**Created:** 2026-08-06 08:55:23 EDT
**Plan:** [202608/selection\_soundness.md](https://github.com/sase-org/sase--plans/blob/main/202608/selection_soundness.md)

## Description

visible: `tools/run_silent` discards captured output on success, so a passing `just check` shows only `✓ test (scoped)` and hides how many tests ran, whether the run escalated, and whether the contexts baseline was missing; surface a one-line scoped summary that survives the success path.

## Dependencies

- **Blocks:** [sase-g3.5](sase-g3.5.md) ◐ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-g3.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-g3.2/README.md) | [sase-g3.2](sase-g3.2.md) | 0 |
