# Bead: sase-1h8.14 — History-independence acceptance gate

[Bead Pages](../README.md) / [sase-1h8](README.md) / sase-1h8.14

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3u.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3u.linker.w0.md) · **Assignee:** `sase-1h8.14` · **Size:** medium
**Created:** 2026-10-06 18:59:47 EDT · **Closed:** 2026-10-09 05:28:53 EDT
**Plan:** [202610/bead\_store\_history\_independent\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202610/bead_store_history_independent_performance.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | [bead:sase-1iu][1] | A1 perf-gate miss recorded by the sase-1h8 history-independence gate; drop this criterion from the bead-perf-scale-gate --gate-allow list when fixed |
| related | [bead:sase-1iv][2] | A1 perf-gate miss recorded by the sase-1h8 history-independence gate; drop this criterion from the bead-perf-scale-gate --gate-allow list when fixed |
| related | [bead:sase-1iw][3] | A1 perf-gate miss recorded by the sase-1h8 history-independence gate; drop this criterion from the bead-perf-scale-gate --gate-allow list when fixed |
| related | [bead:sase-1ix][4] | A1 perf-gate miss recorded by the sase-1h8 history-independence gate; drop this criterion from the bead-perf-scale-gate --gate-allow list when fixed |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1iu/README.md
[2]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1iv/README.md
[3]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1iw/README.md
[4]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1ix/README.md

<!-- sase:links:end -->

## Description

perf-gate: enforce the A1 history-independence criteria on scaled corpora in CI and locally, and record the final before/after results.

## Notes

[2026-10-09T09:12:49Z · sase-1h8.14] perf-gate landed and measured. Gate: tests/perf/bench_bead_scale.py --check-gate/--gate-tolerance/--gate-allow (unit-tested, 5 tests), just bead-perf-scale-gate CI job (1x+4x, tolerance 0.5, blocks on ready ratio; misses recorded as known-miss), strict local just bead-perf-scale -- --check-gate. Formal sweep 1x/2x/4x/8x runs=5 (sdd/plans/202610/perf_artifacts/bead_perf_gate.json, core pin 5c4033f6, host load ~27): ratio:ready PASS (1.03); ratio:list FAIL 5.1x; ratio:detail FAIL (1.16 formal, 3.7x clean probes); ratio:note FAIL 1.8x; ratio:update FAIL 2.1x; abs:point-read FAIL (73ms worst med, 25ms clean at 4x vs 20ms); abs:active-list FAIL (318ms at 8x vs 50ms); abs:tui-nochange FAIL (133ms at 8x vs 100ms). Before/after table in docs/perf_runbook.md (Bead history-independence gate). Wins vs bench baseline: detail 495->37.8ms, ready 408->34.9ms at 1x (6.9/4.1ms clean-window); audited sase bead read 5-8s->3.0s live; remote CLI note 4.4s->~1.1-1.5s. One formal sweep discarded as contention-poisoned (1x ready p95 88ms vs 4ms same store minutes later); reports now record loadavg.

[2026-10-09T09:12:58Z · sase-1h8.14] PROPOSED FOLLOW-UP: per-mutation cost still scales with stream count (gate ratio:note 1.8x, ratio:update 2.1x at 1x->8x; epic note agrees at binding level 2.8x/2.9x) — break into admission/publication/binding overhead and fix; strace datum: one facade append_note at 1x issues only 1383 stat calls total incl. startup (< 2000 streams), so no full per-mutation stat sweep on that path and the sweep theory needs revisiting

[2026-10-09T09:13:02Z · sase-1h8.14] PROPOSED FOLLOW-UP: default-list (paged active query) scales 5.1x 1x->8x with 318ms worst median at 8x vs 50ms ceiling — hydration is per active row and the active set grows with the corpus; needs bounded serving for unbounded active lists

[2026-10-09T09:13:09Z · sase-1h8.14] PROPOSED FOLLOW-UP: bead_show_issue_detail binding scales ~6ms at 1x to ~23.5ms at 4x while plain bead_show is flat (0.6->0.8ms), so the relations expansion scans corpus-sized state; facade hydration adds ~nothing — narrow the expansion to indexed rows (also closes the abs:point-read 25ms-at-4x vs 20ms gap)

[2026-10-09T09:13:14Z · sase-1h8.14] PROPOSED FOLLOW-UP: TUI no-change snapshot refresh doubles per scale doubling (15.6/32/64/133ms medians at 1x/2x/4x/8x) — cost is linear in active rows; needs row virtualization to meet the <100ms ceiling at scale

[2026-10-09T09:27:50Z · sase-1h8.14] PROPOSED FOLLOW-UP: sase tool run check is red on init memory --check (sase/memory/README.md +2/-2 drift); reproduces identically with this phase’s files stashed, in files this phase never touched — pre-existing, does not keep this bead open. All phase-scoped verification is green: ruff, mypy (one pre-existing sase_core_rs-stub error in untouched _bead_corpus_store.py, also present stashed), 11 passed (test_bead_scale_gate + test_bead_corpus), CI-argv gate run exit 0.

[2026-10-09T09:28:53Z · sase-1h8.14] perf-gate enforced and measured: --check-gate harness + CI job + strict local recipe landed; ratio:ready passes (1.03, 1x->8x); list/detail/mutation/TUI misses recorded with breakdowns and 5 PROPOSED FOLLOW-UPs; before/after table in docs/perf_runbook.md; gate unit tests + corpus tests pass, ruff/mypy clean; check red only on pre-existing init-memory drift (reproduces stashed); no epic-symbol leftovers

## Dependencies

- **Depends on:** [sase-1h8.10](sase-1h8.10.md) ✓ · ⧖ 2026-10-06
- **Depends on:** [sase-1h8.13](sase-1h8.13.md) ✓ · ⧖ 2026-10-06
- **Depends on:** [sase-1h8.2](sase-1h8.2.md) ✓ · ⧖ 2026-10-06
- **Depends on:** [sase-1h8.3](sase-1h8.3.md) ✓ · ⧖ 2026-10-06
- **Depends on:** [sase-1h8.6](sase-1h8.6.md) ✓ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.14](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.14/README.md) | [sase-1h8.14](sase-1h8.14.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`10385fe`](https://github.com/sase-org/sase/commit/10385fe3c3c7ebbc5d63d64ff8a3f3a2daf8c128) | perf(beads): add bead-scale gate enforcement with list\_active\_page op and CI wiring | [sase-1h8.14](sase-1h8.14.md) | 2026-10-09 05:31:12 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.3y.grk][1] | Need 1h8 phase statuses that overlap sase-1h5 Beads-pane work | 1 |
| read-by | [agent:sase-1h8.14][2] | Need phase notes and remaining work | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3y.grk/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.14/README.md

<!-- sase:referenced-by:end -->
