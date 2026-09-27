# Bead: sase-19i.7.3.3.3.3.2 — Pass the official open benchmark

[Bead Pages](../README.md) / [sase-19i.7.3.3.3.3](sase-19i.7.3.3.3.3.md) / sase-19i.7.3.3.3.3.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-19i.7.3.3.3.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.7.3.3.3.land.md) · **Assignee:** `sase-19i.7.3.3.3.3.2` · **Size:** medium
**Created:** 2026-09-26 18:21:14 EDT · **Closed:** 2026-09-26 20:54:38 EDT
**Plan:** [202609/node\_finder\_open\_budget.md](https://github.com/sase-org/sase--plans/blob/main/202609/node_finder_open_budget.md)

## Description

open-budget: finish the first-paint drain and any leftover snapshot cost until the unchanged four-case benchmark passes.

## Notes

[2026-09-27T00:54:18Z · sase-19i.7.3.3.3.3.2--1] PROPOSED FOLLOW-UP: just check stays red on clean base tree too — mypy 8 errors (_tree.py:622-629, _node_finder_snapshot.py:617-667), symvision 21 unused publics, test_validate_proc_lifecycle_contract stale named-proc vs proc-shell; triage verdict no_new_failures (30 KNOWN), tool run aedc5e20509939ca0dc925c06fa2f247

[2026-09-27T00:54:38Z · sase-19i.7.3.3.3.3.2--1] open-budget passes: bench 25 samples open p50 41.60ms p95 46.50ms max 47.01ms (<50ms), keystroke-dispatch p95 0.00, keystroke p95 0.95, broad p95 4.78, highlight p95 0.57 (all <16ms), exit 0; focused node-finder model/modal/snapshot/ladder/reveal 79 passed; just check exit 1 triaged no_new_failures 30 KNOWN, all reproduce identically on clean base tree (verified via stash: same 8 mypy errors + proc-lifecycle test fail), recorded as PROPOSED FOLLOW-UP; bench file untouched; epic-symbols clean

[2026-09-27T00:58:45Z · sase-19i.7.3.3.3.3.2--1] BENCH RECORD: official command passed 2x (p50 41.60/p95 46.50/max 47.01; retry p50 40.72/p95 43.27/max 43.88) and failed 2x between them (p95 426.60/67.55, max ~450-502ms) with p50 still <50; code identical all runs; host load 12-16 from other workspaces pytest workers, so tail spikes are scheduling stalls, body consistently ~41-48ms vs 50ms budget — margin is thin, land agent may want a quiet-host confirmation run

[2026-09-27T01:34:50Z · sase-19i.7.3.3.3.3.2--2] Second just check confirmation (tool run 50b8ebe46608c2e340787d08360f25d8): same signature — 8 mypy errors (_tree.py, _node_finder_snapshot.py), 21 symvision unused publics; triage verdict no_new_failures (30 KNOWN, 0 flaky), matching prior base-tree finding; phase changes (node_finder snapshot/modal/model) remain in working tree for host finalizer

## Dependencies

- **Depends on:** [sase-19i.7.3.3.3.3.1](sase-19i.7.3.3.3.3.1.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19i.7.3.3.3.3.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.7.3.3.3.3.2.md) | [sase-19i.7.3.3.3.3.2](sase-19i.7.3.3.3.3.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d5387e1`](https://github.com/sase-org/sase/commit/d5387e15d9397084e72ba99cf0fe907c41a9445d) | perf(tui): finish first-paint drain for node finder open p95 budget | [sase-19i.7.3.3.3.3.2](sase-19i.7.3.3.3.3.2.md) | 2026-09-26 21:45:45 EDT |
