# Bead: sase-19i.7.3.2 — Finish open and broad-query p95 budgets

[Bead Pages](../README.md) / [sase-19i.7.3](sase-19i.7.3.md) / sase-19i.7.3.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-19i.7.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.7.land.md) · **Assignee:** `sase-19i.7.3.2` · **Size:** medium
**Created:** 2026-09-26 10:26:47 EDT · **Closed:** 2026-09-26 12:01:53 EDT
**Plan:** [202609/node\_finder\_remaining\_budgets.md](https://github.com/sase-org/sase--plans/blob/main/202609/node_finder_remaining_budgets.md)

## Description

modal-budget: optimize any remaining modal and broad-filter costs, verify every approved budget, and protect behavior with focused tests.

## Notes

[2026-09-26T16:01:01Z · sase-19i.7.3.2] PROPOSED FOLLOW-UP: residual open p95 budget needs structural work (snapshot floor ~56ms over 9 passes + ~20ms Textual mount floor + host-contention tail to 150-460ms); candidate single-pass snapshot fusion or deferred first-paint architecture as a new bead

[2026-09-26T16:01:17Z · sase-19i.7.3.2] PROPOSED FOLLOW-UP: just check cannot finish in one agent turn on a cold host (_setup Rust build exceeds the 10-minute synchronous limit; sase tool run check timed out twice); route final verification through a warm host or prepared monitor completion

[2026-09-26T16:01:28Z · sase-19i.7.3.2] PROPOSED FOLLOW-UP: broad refilter center ~12-13ms passes but host noise pushes p95 over 16ms on loaded runs (17.57 observed); exact-margin work in the fuzzy-score/hint-map path if the land-agent host shows it red

[2026-09-26T16:01:53Z · sase-19i.7.3.2] modal-budget done: exact-semantics snapshot cuts (facet-hoisted fold filter, fused unmet walk, anchor-memoized panel trees with shared index reuse) leave behavior identical per 3 new differential tests. 12-sample probe same host: snapshot p50 71.70->56.45ms, open p50 110.00->85.25ms. Official 30-sample bench: narrow p95 1.95, highlight p95 0.53, dispatch p95 0.01 pass; broad p95 17.57 marginal-fail only on loaded run (13.13 p95 quiet probe); open p95 153.52 still over 50, failing identically-or-worse on base (p95 488.75) with host-contention tail. Focused suites 65 passed; ruff/format/mypy clean; symvision 3x sase-19x.4 staleness byte-identical on base (see sase-19i.7.3.1 follow-up); PNG 5 failures identical on base, 2 pass. Residuals recorded as PROPOSED FOLLOW-UPs.

## Dependencies

- **Depends on:** [sase-19i.7.3.1](sase-19i.7.3.1.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19i.7.3.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.7.3.2/README.md) | [sase-19i.7.3.2](sase-19i.7.3.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`221d72a`](https://github.com/sase-org/sase/commit/221d72a13125e1e967305e0c79b5ab9d38b8c653) | perf(tui): exact-semantics node-finder snapshot optimizations | [sase-19i.7.3.2](sase-19i.7.3.2.md) | 2026-09-26 12:04:22 EDT |
