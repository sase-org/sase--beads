# Bead: sase-1t3.11.1.5 — Collect stranded facts and titles from one targeted snapshot

[Bead Pages](../README.md) / [sase-1t3.11.1](sase-1t3.11.1.md) / sase-1t3.11.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t3.11](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.11.md) · **Assignee:** `sase-1t3.11.1.5` · **Size:** medium
**Created:** 2026-11-17 12:30:57 EST · **Closed:** 2026-11-18 00:16:40 EST
**Plan:** [202611/bounded\_log\_queries.md](https://github.com/sase-org/sase--plans/blob/main/202611/bounded_log_queries.md)

## Description

stranded_reports: remeasure the indexed bead reader, eliminate repeated candidate collection, and retain only the issue facts required by stranded reports.

## Notes

[2026-11-18T05:16:26Z · sase-1t3.11.1.5] PROPOSED FOLLOW-UP: tests/test_workflow_executor_parallel.py::test_pre_expand_parallel_no_embedded_workflows fails on the clean base tree (verified via stash: identical AssertionError on step identity `modified[1] is nested_steps[1]` with no stranded imports in that file); unrelated to this phase, tracked for the land agent.

[2026-11-18T05:16:40Z · sase-1t3.11.1.5] stranded_reports done: load_stranded_report now collects facts+titles from one slim Rust snapshot (bead_stranded_snapshot) instead of 4 full list_issues reads. Measured on gh_sase-org__sase (8632 issues, fresh read model): before 2824 full Issue hydrations incl. 1140 plans for ~0 context rows and 715k desc chars at 2.95s/report; after 260 candidates+context slim rows with zero heavy payload at 0.034s snapshot and 2.36s/report, binding/fallback parity asserted. Old whole-store parse already gone on warm stores (indexed lane serves). Added core binding + indexed/replay parity tests, facade parity/projection/scale tests, single-snapshot coherence tests. just check: all lints + 61860 scoped tests pass except pre-existing test_pre_expand_parallel_no_embedded_workflows, which fails identically on the clean base (recorded as PROPOSED FOLLOW-UP). Core sase tool run check: pass. Both repos changed; pin update left to host landing.

## Dependencies

- **Depends on:** [sase-1t3.11.1.4](sase-1t3.11.1.4.md) ✓ · ⧖ 2026-11-17
- **Blocks:** [sase-1t3.11.1.6](sase-1t3.11.1.6.md) ◐ · ⧖ 2026-11-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.11.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.11.1.5/README.md) | [sase-1t3.11.1.5](sase-1t3.11.1.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@71c59dc`](https://github.com/sase-org/sase-core/commit/71c59dca5790d8ac7e8eab1e9c1e11f8d2ae4440) | perf(bead): add bead\_stranded\_snapshot slim projection | [sase-1t3.11.1.5](sase-1t3.11.1.5.md) | 2026-11-18 00:19:09 EST |
| sase | [`88431ca`](https://github.com/sase-org/sase/commit/88431cab7190cf5bb3b78c6e629c4a33958d5d10) | perf(bead): read stranded report from single slim snapshot | [sase-1t3.11.1.5](sase-1t3.11.1.5.md) | 2026-11-18 00:20:52 EST |
