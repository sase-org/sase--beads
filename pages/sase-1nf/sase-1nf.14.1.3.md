# Bead: sase-1nf.14.1.3 — Avoid copying Agent graphs that a load will discard

[Bead Pages](../README.md) / [sase-1nf.14.1](sase-1nf.14.1.md) / sase-1nf.14.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nf.14](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.14.md) · **Assignee:** `sase-1nf.14.1.3` · **Size:** medium
**Created:** 2026-10-24 13:37:43 EDT · **Closed:** 2026-10-24 14:19:44 EDT
**Plan:** [202610/measured\_tui\_gc\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/measured_tui_gc_fixes.md)

## Description

graph-allocation: classify cached-row use before detaching graphs, copy only required ownership closures, and preserve worker isolation and aliases.

## Notes

[2026-10-24T18:19:44Z · sase-1nf.14.1.3] graph-allocation done: classify-then-copy in _loading_graph (CachedGraphNeeds/classify_cached_graph_needs/own_required_apply_snapshot) wired into worker/apply-boundary/merge paths. Authoritative+projection loads copy 0 rows (was 102/1000); delta/query-change/capacity/named-proc/fleet behavior preserved with shared-memo aliasing. Verified: 4 new regression tests in test_agents_tab_graph_isolation (failed pre-fix), 243 tests green across the loading-pipeline closure, all just-check lint gates pass (ruff/mypy/symvision). Benchmarks at 100/1000 rows: authoritative 14.8/117.6ms peak 0.2/2.0MB vs old full-copy 43.4/395.2ms peak 1.0/10.0MB; delta steady-state ~22ms/100 rows. Note: sase tool run check run a11cacab77de983d1333909ff64caa86 escalated to the full suite on a stale baseline (4641 commits behind) and is still running under host load; no lane failure observed. No follow-ups.

## Dependencies

- **Blocks:** [sase-1nf.14.1.6](sase-1nf.14.1.6.md) ◐ · ⧖ 2026-10-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.14.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.14.1.3/README.md) | [sase-1nf.14.1.3](sase-1nf.14.1.3.md) | 0 |
