# Bead: sase-1h8.1 — Scaled-corpus bead benchmark harness

[Bead Pages](../README.md) / [sase-1h8](README.md) / sase-1h8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3u.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3u.linker.w0.md) · **Assignee:** `sase-1h8.1` · **Size:** medium
**Created:** 2026-10-06 18:59:29 EDT · **Closed:** 2026-10-06 21:07:14 EDT
**Plan:** [202610/bead\_store\_history\_independent\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202610/bead_store_history_independent_performance.md)

## Description

bench: add a deterministic realistic-shape synthetic bead corpus at any scale, a local prefix-copy tool for real stores, a scale-aware bead benchmark, and a record-only 4x CI run.

## Notes

[2026-10-07T01:06:13Z · sase-1h8.1] bench done: generator tests/perf/_bead_corpus.py (deterministic, seedable; event IDs minted exactly as core merge.rs mint, verified byte-equal against core-minted events), scale-copy tests/perf/_bead_scale_copy.py + tools/bead_scale_corpus (read-only source, length-preserving prefix rename with re-mint, refuses sidecar-clone dests), benchmark tests/perf/bench_bead_scale.py (16 ops: 8 binding reads, 2 binding mutations, 3 CLI incl. note against local bare remote, 3 TUI incl. no-change fast path; emits JSON with per-op p50/p95/max + shape + core revision), tests/perf/test_bead_corpus.py (6 tests: mint-exactness, validity+doctor-clean, determinism, shape, 2x copy, refusals). Recipes: just bead-perf-scale (1/2/4/8, slow), just bead-perf-scale-record + just bead-scale-copy; CI perf-floors runs record-only 4x with trimmed binding ops and uploads bead_perf_scale4.json.

[2026-10-07T01:06:36Z · sase-1h8.1] Baseline (medians, this host): 1x 6899 beads/2000 streams/44744 events closed91.9%: show_detail 495ms, ready 408ms, list 775ms, note_append 511ms, update 549ms, cli_show 2581ms, cli_ready 882ms, cli_note 4446ms, tui_board 1590ms, tui_snapshot 3030ms, tui_cached 33ms. 2x: show_detail 984ms, ready 966ms, list 2074ms, note 1019ms, update 1194ms, cli_show 3270ms, cli_ready 1721ms, cli_note 7133ms, tui_board 3745ms, tui_snapshot 11593ms, tui_cached 62ms. 4x 27807/8000/181158: show_detail ~2.1s, ready 2.3s, list 4.1s, note 2.3s, update 2.6s, cli 2.8-15s, tui_board 7.8s. 8x bindings-only: show_detail ~4.6-5.1s, ready 4.1s, list 8.2s. Replay cost ~0.5s at 1x matches research 0.48-0.52s; show_detail scales 495/984/2127/4628ms ~linear. tui_snapshot 3.0s->11.6s (3.8x for 2x data) confirms the O(epics x issues) loop the tui-board phase removes. 4x tui_cached ran 48s only because a background notification write moved the snapshot key mid-run (full reload); the no-change fast path itself is proven by 1x/2x (33/62ms).

[2026-10-07T01:06:52Z · sase-1h8.1] PROPOSED FOLLOW-UP: just check lint (symvision) fails on _runs private-import in src/sase/agents_sync/v2_snapshot_io.py and src/sase/ace/tui/widgets/decks/final/overview_card.py; reproduces with this phases files removed, in files this phase never touched (likely textual collision with from sase.instructions import _runs), so it does not keep this bead open.

[2026-10-07T01:07:14Z · sase-1h8.1] bench harness landed and verified: 6 generator tests pass; 1x corpus (6899 beads/2000 streams/44744 events, 91.9% closed, doctor-clean) replays at ~0.5s matching research; linear scaling to 8x recorded in notes; record-only 4x CI job added and its trimmed run verified; no epic-symbol leftovers; the one just-check failure (symvision _runs) reproduces without this phase's files and is recorded as PROPOSED FOLLOW-UP

## Dependencies

- **Blocks:** [sase-1h8.8](sase-1h8.8.md) ◐ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.1/README.md) | [sase-1h8.1](sase-1h8.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`dcda0f0`](https://github.com/sase-org/sase/commit/dcda0f0afd74748b9588d8fb8e2015599d4f5610) | feat(perf): add scaled-corpus bead benchmark harness | [sase-1h8.1](sase-1h8.1.md) | 2026-10-06 21:09:38 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1h8.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.1/README.md

<!-- sase:referenced-by:end -->
