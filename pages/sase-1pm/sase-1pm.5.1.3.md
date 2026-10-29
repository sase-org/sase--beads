# Bead: sase-1pm.5.1.3 — Resolve changed-file first-party imports on the rebased tree

[Bead Pages](../README.md) / [sase-1pm.5.1](sase-1pm.5.1.md) / sase-1pm.5.1.3

**Status:** ○ open · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pm.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pm.5.md) · **Assignee:** `sase-1pm.5.1.3` · **Size:** medium
**Created:** 2026-10-29 02:12:58 EDT
**Plan:** [202610/rebased\_stitch\_gate.md](https://github.com/sase-org/sase--plans/blob/main/202610/rebased_stitch_gate.md)

## Previously Closed

> ↺ Closed 2026-10-29T08:52:10Z · done
>
> (none)
>
> Reopened 2026-10-29T09:07:07Z by `sase bead open`

## Description

import-checker: implement repo tooling using Python AST and importlib, with exact TYPE_CHECKING alias exceptions and subprocess fixtures. Follow the gate wire contract; do not modify commit dispatch or enable config.

## Notes

[2026-10-29T08:06:58Z · sase-1pm.5.1.3] Implemented tools/check_rebase_imports plus tools/_check_rebase_imports.py. TYPE_CHECKING allowlist is empty: a full importlib scan of this checkout resolved all 619 first-party TYPE_CHECKING aliases. Focused pytest: 15 checker tests plus typecheck_extensionless_tools tests passed. just fix, git diff --check, and sase bead epic-symbols (no leftovers) passed. Did not change commit dispatch or enable after_rebase config.

[2026-10-29T08:51:35Z · sase-1pm.5.1.3--2] PROPOSED FOLLOW-UP: just check test-scoped exited 1 with no_new_failures (ToolRun 1f27e5ba8e8253998b0479129f2e03d1): KNOWN tests/monitor/test_monitor_start_supervisor.py::test_start_monitor_scrubs_agent_identity_from_the_supervisor_env and tests/monitor/test_monitor_start_ack.py::test_start_monitor_kills_a_supervisor_that_never_writes_the_ack_marker (both tracked by sase-1pg; ack-marker shares its root cause) plus FLAKY tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection (baseline tests/reproducible_flake_baseline.txt@c76fee2af11d). Unrelated to this phase; close anyway.

[2026-10-29T08:52:10Z · sase-1pm.5.1.3--2] Implemented tools/check_rebase_imports plus tools/_check_rebase_imports.py (AST + importlib, empty TYPE_CHECKING allowlist, subprocess fixtures). Listed the helper in tools/typecheck_extensionless_tools EXTRA_TYPED_HELPERS so pyscripts Rule 1 is satisfied. Did not change commit dispatch or enable after_rebase config. sase bead epic-symbols reported no leftovers. just check ToolRun 1f27e5ba8e8253998b0479129f2e03d1 triaged no_new_failures (2 KNOWN monitor-start tests owned by sase-1pg, 1 FLAKY contract-manifest baseline).

## Dependencies

- **Depends on:** [sase-1pm.5.1.1](sase-1pm.5.1.1.md) ✓ · ⧖ 2026-10-29
- **Blocks:** [sase-1pm.5.1.4](sase-1pm.5.1.4.md) ◐ · ⧖ 2026-10-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pm.5.1.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pm.5.1.3.md) | [sase-1pm.5.1.3](sase-1pm.5.1.3.md) | 0 |
