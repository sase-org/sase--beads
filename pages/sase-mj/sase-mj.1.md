# Bead: sase-mj.1 — Rust perf-log aggregation and binding

[Bead Pages](../README.md) / [sase-mj](README.md) / sase-mj.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.032](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.032.md) · **Assignee:** `sase-mj.1` · **Size:** medium
**Created:** 2026-08-15 20:25:44 EDT · **Closed:** 2026-08-15 20:55:43 EDT
**Plan:** [202608/statistics\_perf\_view.md](https://github.com/sase-org/sase--plans/blob/main/202608/statistics_perf_view.md)

## Description

core_perf_logs: add a `perf_logs` module to the sibling Rust core that reads the six durable TUI/launch perf JSONL logs with bounded tail reads, aggregates them over a caller-supplied window into one composite wire payload, and exposes it as the `perf_logs_query` Python binding.

## Notes

[2026-08-16T00:55:43Z · sase-mj.1] Implemented perf_logs Rust core aggregation and perf_logs_query PyO3 binding; verified main just install, focused cargo tests for perf_logs and binding, and sase-core just check.

[2026-08-16T00:58:07Z · sase-mj.1] Verified with just install, cargo test -p sase_core perf_logs, cargo test -p sase_core_py perf_logs_query_binding_round_trips_python_dict, and just check in sase-core.

## Dependencies

- **Blocks:** [sase-mj.2](sase-mj.2.md) ◐ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mj.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mj.1/README.md) | [sase-mj.1](sase-mj.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@d0ac555`](https://github.com/sase-org/sase-core/commit/d0ac55516eaeba739398a6014f6e9f31dec1519e) | feat: add perf log aggregation query | [sase-mj.1](sase-mj.1.md) | 2026-08-15 20:59:52 EDT |
