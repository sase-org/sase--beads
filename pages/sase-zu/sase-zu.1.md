# Bead: sase-zu.1 — Load-path parity oracle and archive-scale benchmark

[Bead Pages](../README.md) / [sase-zu](README.md) / sase-zu.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.05.f0` · **Assignee:** `sase-zu.1` · **Size:** medium
**Created:** 2026-09-12 10:35:42 EDT · **Closed:** 2026-09-12 13:11:22 EDT
**Plan:** [202609/agent\_query\_load\_tiering.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_query_load_tiering.md)

## Description

harness: build the synthetic large-archive fixture, the parity oracle that proves every load path returns the same visible rows as an authoritative source scan, and the benchmark that times the three load paths.

## Notes

[2026-09-12T17:11:22Z · sase-zu.1] Implemented synthetic 13k archive fixture, parity oracle, query battery, benchmark CLI/Justfile/docs, and live NOT pushdown safety. Verified: ruff on touched files; pytest tests/test_agent_load_tiering_harness.py tests/test_agent_query_pushdown.py; pytest -m slow tests/perf/bench_agent_load_tiering.py; just bench-agent-load-tiering --artifact-count 72 --runs 1 --warmup 0 --query cl:feature-done; just lint; sase bead epic-symbols sase-zu.1 clean. Archive baselines: cl:feature-done bounded p50 45.1ms vs source p50 8824.9ms with zero diffs; not machine:apollo bounded p50 88.6ms vs source p50 8674.5ms, full-history index zero diffs. just check was run and escalated to the full fast suite because of Justfile/core identity changes; it failed in unrelated queue/capacity/VCS tests after 40950 passes.

## Dependencies

- **Blocks:** [sase-zu.2](sase-zu.2.md) ✓ · ⧖ 2026-09-12
- **Blocks:** [sase-zu.3](sase-zu.3.md) ◐ · ⧖ 2026-09-12
- **Blocks:** [sase-zu.7](sase-zu.7.md) ◐ · ⧖ 2026-09-12

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6665e7b`](https://github.com/sase-org/sase/commit/6665e7be27e0367f34750ac0c5e2964a6a19bfc6) | feat: Load-path parity oracle and archive-scale benchmark (sase-zu.1) | [sase-zu.1](sase-zu.1.md) | 2026-09-12 13:16:29 EDT |
