# Bead: sase-1qn.2 — Stop behavior-neutral module splits from turning the TUI import budget red (sase-1ic)

[Bead Pages](../README.md) / [sase-1qn](README.md) / sase-1qn.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pu.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pu.land.md) · **Assignee:** `sase-1qn.2` · **Size:** large
**Created:** 2026-11-01 14:34:48 EST
**Plan:** [202611/task\_backlog\_epic\_4.md](https://github.com/sase-org/sase--plans/blob/main/202611/task_backlog_epic_4.md)

## Description

import-budget-churn: the first-party TUI import-count guard in tests/ace/tui/test_app_import_budget.py has been re-raised after toobig splits and reopened twice (+35). Make the guard catch genuine new import-path work while staying neutral to mechanical splits of modules already on the path, without weakening the deferred-module list or just raising the cap again. Verify against recent split commits and a synthetic new eager import.

## Notes

[2026-11-01T19:47:14Z · sase-1qn.2] PLANNING EVIDENCE: No prior phase work notes; clean base 078e3da1d6. Existing import-budget tests pass 5/5 at 2860 first-party modules against strict 2861, but historical d3d26a5b55 reproduces the exact 2863-vs-2861 AssertionError. Same-interpreter split replays: eef22a0124 adds 3 modules and bffbc8effd adds 5. Prototype normalized source-token bytes across changed source files grow only 288 and 59 respectively (prompt staging split 362fcb2e7f: 69). Authored and validated a medium tale replacing tight module counting with a shared normalized-source-footprint guard while retaining deferred modules, CPU, and loose total limits. No implementation changes made; phase remains in progress for the plan handoff. No epic-symbol entries found.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1qn.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qn.2.md) | [sase-1qn.2](sase-1qn.2.md) | 0 |
