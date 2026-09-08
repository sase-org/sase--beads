# Bead: sase-xe.16.5 — Third-party provider imports follow the finalizers trust model

[Bead Pages](../README.md) / [sase-xe.16](sase-xe.16.md) / sase-xe.16.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08c.md) · **Assignee:** `sase-xe.16.5` · **Size:** medium
**Created:** 2026-09-08 10:21:35 EDT · **Closed:** 2026-09-08 11:26:34 EDT
**Plan:** [202609/remote\_dispatch\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_completion.md)

## Description

provider-isolation: today collect_dispatch_providers and helpers eagerly ep.load() third-party entry points in-process, which the parent plan's dispatch-plugins phase explicitly forbade. Inventory entry points as metadata in-process; import provider code only inside a bounded, separately supervised helper subprocess with a deadline and cancellation, and only for the selected provider, following the finalizers loading model. A provider exception or timeout affects only its machines. Decide the dispatch_connection_plan hook: add it for third-party providers or record an explicit deferral decision (builtin providers derive plans from enrolled machine records and do not need it).

## Notes

[2026-09-08T15:24:15Z · sase-xe.16.5] PROPOSED FOLLOW-UP: Keymap scoped-test failure — just check escalated to the full suite and tests/test_keymaps_patch_grouping_binding.py::test_pane_key_resolution failed for ref:plan o/O grouping actions, unrelated to dispatch provider isolation changes.

[2026-09-08T15:26:34Z · sase-xe.16.5] Verified focused dispatch provider suite (20 passed), targeted federation/machine/doctor regressions (4 passed), ruff/symvision clean, and just check ran through lint with scoped/full pytest failing only unrelated ref:plan keymap grouping tests already recorded as a proposed follow-up.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.5/README.md) | [sase-xe.16.5](sase-xe.16.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f081f23`](https://github.com/sase-org/sase/commit/f081f23038f4bb21170cc7860c24e5894ab36616) | feat(dispatch): isolate third-party provider hooks | [sase-xe.16.5](sase-xe.16.5.md) | 2026-09-08 11:29:47 EDT |
