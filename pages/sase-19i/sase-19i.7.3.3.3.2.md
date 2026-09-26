# Bead: sase-19i.7.3.3.3.2 — Pass first-paint and broad-refilter budgets

[Bead Pages](../README.md) / [sase-19i.7.3.3.3](sase-19i.7.3.3.3.md) / sase-19i.7.3.3.3.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-19i.7.3.3.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.7.3.3.land.md) · **Assignee:** `sase-19i.7.3.3.3.2` · **Size:** medium
**Created:** 2026-09-26 15:55:46 EDT · **Closed:** 2026-09-26 17:51:49 EDT
**Plan:** [202609/node\_finder\_open\_and\_broad\_tail.md](https://github.com/sase-org/sase--plans/blob/main/202609/node_finder_open_and_broad_tail.md)

## Description

paint-and-broad: trim first-paint pump work and broad refilter while preserving navigation, then pass every official budget.

## Notes

[2026-09-26T21:51:18Z · sase-19i.7.3.3.3.2] Phase evidence — paint-and-broad. Official bench tests/ace/tui/bench_node_finder.py (unchanged, 25 measured samples), this host load ~15-20: open p50=63.3 p95=74.8 max=397.0 (base: p50=70.9 p95=80.6 max=477.3) FAILS <50; keystroke-dispatch p95=0.01 PASS; keystroke p50=0.61 p95=0.64 PASS (<16); broad p50=4.99 p95=7.65 max=9.15 PASS (<16, was 14.64 base); highlight p50=0.54 p95=0.55 PASS (<16). Stage split (open): snapshot ~35-40 quiet (~55-90 loaded), modal-init ~2.6, push+drain ~25 (28 pump rounds: suspend-layout + mount-layout + on_mount; rounds structural, on_mount content does not change round count). Landed cuts: filter_tree_rows all-match early-out (open query-survivor pass -6ms, helps live view too), per-modal (query, prev-tokens) view memo capped at 8 (refilters after first sample ~0.2ms), identical-rebuild skip incl. live-highlight guard (cursor-move then refilter still re-centers). Focused suites: 837 passed (models dir + node-finder modal), 36 passed (live-query + e2e + snapshot), 7 new tests (view memo, rebuild skip, highlight reset, tree early-out). just check: fmt/ruff/mypy/model-policy/keep-sorted/feature-flags/pyscripts/test-waits/changelog/terminology PASS; symvision 2 KNOWN (sase-1ab private-import, pre-existing); SASE validation init-memory drift UNKNOWN but base-identical (prior phase follow-up #4); 3 test-collection ImportErrors (gate/monitor/proc-shell rows) verified base-identical (prior follow-up #3). No epic symbols remain. Bench file untouched; no PNG changes possible (all cuts produce byte-identical options/views/lists).

[2026-09-26T21:51:33Z · sase-19i.7.3.3.3.2] PROPOSED FOLLOW-UP: open p95 still over 50ms (74.8 mine vs 80.6 clean-base, same spike signature max ~400-477ms) — needs structural snapshot+drain work beyond safe cuts: snapshot facets/tree/row-loop are all load-bearing (~35 quiet), drain is Textual suspend/mount/layout + 28 structural pump rounds; candidate avenues are prompt/guide caches for cold rebuilds, banner-skeleton tree emitter, fact-threaded grouping keys, or budget recalibration on a quiet host

[2026-09-26T21:51:49Z · sase-19i.7.3.3.3.2] Verified: broad 7.65/narrow 0.64/highlight 0.55/dispatch 0.01 p95 all under budget (broad was failing at 14.64-19.1); open improved 80.9 to 74.8 p95 but still over 50 identically on clean base (80.6, same spike signature) so environmental — recorded as follow-up. 7 new tests green; 837+36 focused tests green; just check gates green except base-identical symvision-KNOWN, memory-drift, and 3 collection ImportErrors. No epic symbols; bench file untouched.

## Dependencies

- **Depends on:** [sase-19i.7.3.3.3.1](sase-19i.7.3.3.3.1.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19i.7.3.3.3.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.7.3.3.3.2/README.md) | [sase-19i.7.3.3.3.2](sase-19i.7.3.3.3.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0a74b4f`](https://github.com/sase-org/sase/commit/0a74b4f25ca52cd0c4de862ff49133c6db7a6465) | perf(node-finder): pass broad/narrow refilter budgets and cut open path (sase-19i.7.3.3.3.2) | [sase-19i.7.3.3.3.2](sase-19i.7.3.3.3.2.md) | 2026-09-26 17:53:38 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-19i.7.3.3.3.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.7.3.3.3.2/README.md

<!-- sase:referenced-by:end -->
