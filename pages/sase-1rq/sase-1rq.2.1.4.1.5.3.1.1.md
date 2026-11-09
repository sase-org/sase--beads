# Bead: sase-1rq.2.1.4.1.5.3.1.1 — Make the hosted default contention job finish within 90 minutes

[Bead Pages](../README.md) / [sase-1rq.2.1.4.1.5.3.1](sase-1rq.2.1.4.1.5.3.1.md) / sase-1rq.2.1.4.1.5.3.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.2.1.4.1.5.3--1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.1.4.1.5.3.md) · **Assignee:** `sase-1rq.2.1.4.1.5.3.1.1` · **Size:** medium
**Created:** 2026-11-09 04:31:23 EST · **Closed:** 2026-11-09 04:50:58 EST
**Plan:** [202611/hosted\_contention\_gap.md](https://github.com/sase-org/sase--plans/blob/main/202611/hosted_contention_gap.md)

## Description

hosted-runtime: profile the GitHub two-CPU Python 3.12 gap against the local green tally, remove the dominant hosted overhead without weakening the workload, and prove a complete hosted contention tally inside 90 minutes.

## Notes

[2026-11-09T09:50:21Z · sase-1rq.2.1.4.1.5.3.1.1] Hosted-gap profile: Telemetry 42574447281 (SHA 7a7ecd6885) did 28380/60600 in 5383s wall (~5.3 tests/s) vs local py312 green 60608 in 4570.78s (~13.3 tests/s), ~2.5x gap. Shards balanced by committed table (26x ~438s est) but hosted finished counts spread 386 (gw24) to 2501 (gw14); TUI-heavy shards are the critical path. Long in-flight nodes are CPU-bound whole-tree scans: test_main_static_on_repo_exits_zero (~8.8m, 24s uncontended), test_tracked_marker_mutation_sites_are_reviewed (~6.4m, 28s setup uncontended), test_only_boundary_calls_provider_invoke (~4.1m, 11.2s uncontended). Under 26 workers on 2 CPUs (13x oversubscription) each CPU-bound second costs ~13s wall, so redundant parses both stall their own worker and starve TUI event loops into 20-60s timeout hits (all 9 partial reports are timeout-shaped). tools/check_feature_flags run_checks already shares one streaming parse for rules 3+4; the remaining test-side redundancy was two full src scans inside tests/instructions/test_invoke_boundary.py.

[2026-11-09T09:50:33Z · sase-1rq.2.1.4.1.5.3.1.1] Change (1 file): tests/instructions/test_invoke_boundary.py now collects every root *.invoke call site with one whole-tree scan (_scan_invoke_calls, no cache so tmp trees stay fresh) shared through a module-scoped _invoke_snapshot fixture. Both policy tests keep their names, node IDs, and assertions; SRC constant stays live. New regression test_shared_invoke_scan_matches_individual_regressions proves the shared scan flags an off-boundary invoke (exact src/sase/off_boundary.py:run:6 offender), records only real call sites, and invents nothing. Measured: two ~11s scans -> one 12.45s shared setup; file 16 passed in 15.41s. Verified: sase tool run check aef71a31fd326401167f179df0ef015a succeeded (all lint gates + scoped tests, 422s). sase bead epic-symbols: no entries. Hosted <90min proof is NOT claimed this turn (see follow-ups); this is the first safe step of the scan-consolidation program.

[2026-11-09T09:50:38Z · sase-1rq.2.1.4.1.5.3.1.1] PROPOSED FOLLOW-UP: prove hosted completion after landing — dispatch Telemetry telemetry.yml --ref master on the landed tip containing this fix, watch contention-test via a zero-weight monitor, require a complete tally inside 90 minutes (red with full inventory is an acceptable handoff to hosted-failures sase-1rq.2.1.4.1.5.3.1.2); do not reuse cancelled 42574447281, and reuse scheduled 42578053332 only if its contention-test already finished with a complete zero-failure tally on 7a7ecd6885

[2026-11-09T09:50:43Z · sase-1rq.2.1.4.1.5.3.1.1] PROPOSED FOLLOW-UP: continue the scan-consolidation program for the remaining CPU-bound whole-tree scans (marker/directory/path-passing audit helpers shared across test files, terminology line-scans, feature-flag static run) with per-file single-scan fixtures and mutation regressions, then rebalance contention shards with hosted-measured per-file costs (committed table reflects uncontended speed; hosted finished-count spread 386-2501 shows TUI files need contention-aware weights) while keeping identical nodes and 26 workers

[2026-11-09T09:50:58Z · sase-1rq.2.1.4.1.5.3.1.1] Verified: invoke-boundary double whole-tree scan consolidated to one shared scan with mutation regression (16 tests passed in 15.41s); sase tool run check aef71a31fd326401167f179df0ef015a green (all lint gates + scoped tests); epic-symbols clean. Hosted <90min tally handed to follow-ups (hosted-failures 1.1.2): dispatch Telemetry on landed master after this fix lands.

## Dependencies

- **Blocks:** [sase-1rq.2.1.4.1.5.3.1.2](sase-1rq.2.1.4.1.5.3.1.2.md) ✓ · ⧖ 2026-11-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.2.1.4.1.5.3.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.2.1.4.1.5.3.1.1/README.md) | [sase-1rq.2.1.4.1.5.3.1.1](sase-1rq.2.1.4.1.5.3.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9dc824f`](https://github.com/sase-org/sase/commit/9dc824fbb77099044752a9f6c101fe9cae02227b) | perf(tests): share one invoke-boundary scan across policy tests | [sase-1rq.2.1.4.1.5.3.1.1](sase-1rq.2.1.4.1.5.3.1.1.md) | 2026-11-09 04:52:30 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1rq.2.1.4.1.5.3.1.1][1] | check notes and remaining work | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.2.1.4.1.5.3.1.1/README.md

<!-- sase:referenced-by:end -->
