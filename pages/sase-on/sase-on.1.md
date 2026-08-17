# Bead: sase-on.1 — Threshold config and TaskTriage suppression

[Bead Pages](../README.md) / [sase-on](README.md) / sase-on.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04x](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04x.md) · **Assignee:** `sase-on.1` · **Size:** medium
**Created:** 2026-08-17 11:47:54 EDT
**Plan:** [202608/task\_bead\_gate\_thresholds.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_bead_gate_thresholds.md)

## Description

triage: add the grouped `bead.task_triage` config block with its three fields, schema entries, and fail-open accessors, add the shared staleness/suppression predicates, and teach the bead_task_triage chop to withhold a TaskTriage gate from a sub-threshold ready task bead and to cancel the ones it already raised.

## Dependencies

- **Blocks:** [sase-on.4](sase-on.4.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-on.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-on.1/README.md) | [sase-on.1](sase-on.1.md) | 0 |
