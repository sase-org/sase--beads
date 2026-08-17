# Bead: sase-ns.6.6.6.1 — Isolate the process-global merged-config cache so its nodes stop failing the flake gate

[Bead Pages](../README.md) / [sase-ns.6.6.6](sase-ns.6.6.6.md) / sase-ns.6.6.6.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ns.6.6.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.6.6.land.md) · **Assignee:** `sase-ns.6.6.6.1` · **Size:** large
**Created:** 2026-08-17 05:54:39 EDT
**Plan:** [202608/backlog\_top\_five\_gates\_and\_flakes.md](https://github.com/sase-org/sase--plans/blob/main/202608/backlog_top_five_gates_and_flakes.md)

## Description

configcache: fix the process-global merged-config cache leak behind tests/test_config_cache.py::test_selector_change_eventually_invalidates_merged_config, the only non-epic-owned node still holding `just selection-health --fail-on-new-flake` red, and verify its sibling nodes in the same file.

## Notes

[2026-08-17T10:29:08Z · sase-ns.6.6.6.1] PROGRESS: Implemented atomic config-generation publication (lock around token/hit, rebuild off-lock, CAS publish) and test-only publisher restriction after each cache clear. Added leftover-loader and stale-rebuild regressions. Isolation + file-scoped SASE_CONTENTION_REPEAT=3 contention are green (27 passed x3). Next: just check-full via monitor (conftest_runtime is in the broadening set), then selection-health and close.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ns.6.6.6.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.6.6.6.1.md) | [sase-ns.6.6.6.1](sase-ns.6.6.6.1.md) | 0 |
