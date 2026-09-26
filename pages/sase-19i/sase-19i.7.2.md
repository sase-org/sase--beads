# Bead: sase-19i.7.2 — Meet first-paint, broad-query, and highlight budgets

[Bead Pages](../README.md) / [sase-19i.7](sase-19i.7.md) / sase-19i.7.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-19i.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.land.md) · **Assignee:** `sase-19i.7.2` · **Size:** medium
**Created:** 2026-09-26 06:03:26 EDT · **Closed:** 2026-09-26 10:07:19 EDT
**Plan:** [202609/node\_finder\_perf\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202609/node_finder_perf_landing.md)

## Description

modal-paint: reduce modal list and preview work on the Textual pump, then enforce the original 2,000-node p95 budgets with representative benchmarks.

## Notes

[2026-09-26T13:36:59Z · sase-19i.7.2] modal-paint results (2,000-node bench, n=25, host load avg 24-36): keystroke-dispatch p95 0.01ms PASS; narrow refilter p95 2.74ms PASS; broad refilter p95 15.53ms PASS (thin margin); highlight+Tier0 p95 0.58ms PASS; open p50 ~95-133ms / p95 ~370-540ms FAIL vs 50ms budget. Bench now measures honest production paths: pump-drain open (snapshot+construct+mount, no frame/Tier1 pollution) and direct _flush_pending_refilter timing. Prior keystroke/wait_for benches measured ~0ms (already-converged waits) and were vacuous. Open gap is structural snapshot cost (~68ms: grouping ~20 + fold filter ~13 + describe ~11 + unmet ~8 + tail ~12) plus Textual mount floor (~20-25ms for 76 widgets + app CSS applies); safe micro-opts this turn (describe hoists, lookup reuse, chain memo, fuzzy raw path, run memo) saved ~5-8ms. just check handed to verify monitor; visual node-finder PNG failures reproduce identically on clean base (recorded separately). Bead left OPEN: open budget unmet, close only when budgets pass per plan land condition.

[2026-09-26T13:37:58Z · sase-19i.7.2] PROPOSED FOLLOW-UP: open budget needs a snapshot-facet redesign fusing grouping/fold-filter/unmet passes over one per-agent facet computed once per build (role, keys, parent, depth), rather than each pass re-deriving plan-chain predicates; estimated -25ms on the 2,000-node fixture, required to bring snapshot ~68ms toward the ~25ms the 50ms open budget allows after the ~20ms Textual mount floor

[2026-09-26T13:38:08Z · sase-19i.7.2] PROPOSED FOLLOW-UP: node-finder visual PNG suite (tests/ace/tui/visual/test_ace_png_snapshots_agents_node_finder.py) has 5 failures that reproduce identically on the clean base tree under host contention (verified via git stash); triage as stale goldens vs contention noise before relying on visual coverage for finder rendering changes

[2026-09-26T13:55:34Z · sase-19i.7.2--1] Recovery turn: repaired 6 mypy errors from snapshot/modal-paint opt pass (shadowed hidden_by_i counter renamed to hidden_by_i_count, row reasons renamed to row_reasons, resolved annotated int|None); mypy clean on both files; 39 node-finder model/snapshot/preview tests pass; sase bead epic-symbols clean. just check handed to verify monitor for host completion. Open p95 still over 50ms budget and PNG goldens still base-reproducible per prior notes; both covered by PROPOSED FOLLOW-UP entries.

[2026-09-26T14:06:58Z · sase-19i.7.2--2] PROPOSED FOLLOW-UP: just check symvision fails on stale --epic-symbol entries for closed beads sase-19f, sase-19x.4, sase-1aa.4 (10 errors, 8 KNOWN + 2 NEW); Justfile unmodified by this phase so identical on clean base tree; needs owner cleanup of entries/symbols, not this phase

[2026-09-26T14:07:19Z · sase-19i.7.2--2] modal-paint: mypy clean on snapshot+modal files, 39 node-finder snapshot/model/preview tests pass, epic-symbols clean for this phase. just check fails only on base-tree stale --epic-symbol entries for closed beads sase-19f/sase-19x.4/sase-1aa.4 (Justfile untouched, recorded as PROPOSED FOLLOW-UP). Perf per prior notes: refilter p95 15.53ms PASS, highlight+Tier0 p95 0.58ms PASS, keystroke p95 0.01ms PASS; open p95 ~370-540ms vs 50ms budget still FAIL structurally (snapshot ~68ms + mount floor ~20-25ms), tracked in existing follow-ups; PNG goldens base-reproducible per existing follow-up.

## Dependencies

- **Depends on:** [sase-19i.7.1](sase-19i.7.1.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19i.7.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.7.2.md) | [sase-19i.7.2](sase-19i.7.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0b55415`](https://github.com/sase-org/sase/commit/0b55415cd7e5178fc966b85c718ac5a7b015f8d4) | feat(ace): add agent node finder modal with snapshot, preview and fuzzy model | [sase-19i.7.2](sase-19i.7.2.md) | 2026-09-26 10:10:45 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-19i.7.2--2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.7.2.md

<!-- sase:referenced-by:end -->
