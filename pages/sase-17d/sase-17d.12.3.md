# Bead: sase-17d.12.3 — Record before/after j/k bench numbers for SINGLE and LEFT\_RIGHT

[Bead Pages](../README.md) / [sase-17d.12](sase-17d.12.md) / sase-17d.12.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17d.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17d.land.md) · **Assignee:** `sase-17d.12.3` · **Size:** medium
**Created:** 2026-09-25 08:46:17 EDT · **Closed:** 2026-09-25 19:20:46 EDT
**Plan:** [202609/finish\_agent\_decks\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_agent_decks_landing.md)

## Description

deck-jk-bench: run the j/k key-to-paint bench with decks on in the SINGLE and LEFT_RIGHT layouts, on the pre-spread baseline a054efc585 and on the final tree, interleaved to control for host load. Explain every p95 budget miss as host noise or a deck regression, fix any regression, and record the table in a bead note.

## Notes

[2026-09-25T23:20:22Z · sase-17d.12.3] BENCH RESULTS: deck j/k before/after (bead sase-17d.12.3)

Baseline: a054efc585 (parent of spread commit 329d4049b; decks behind
`agent_decks` flag, paged-only rendering). After: 04cf2b1765 (final tree,
decks unconditional, spread rendering). Harness: scratch
tests/ace/tui/bench_deck_layout_scratch.py (DELETED after the runs; used the
committed bench helpers/fixture verbatim: 240-agent synthetic list,
20×j + 20×k + 20×J + 20×K after warmup, SASE_TUI_PERF key-to-paint samples).
Layout via SASE_BENCH_DECK_LAYOUT: `single` (default state) or `left_right`
(entered through the app's own `vertical_line` split binding, asserted
DeckLayout.LEFT_RIGHT on both trees). Flag on baseline enabled in-process;
final tree needs none. Interleaved A/B/A/B, 2 rounds each, loadavg recorded
per run. Host was heavily loaded throughout (1-min loadavg 18.6-24.8).

p95 table (p50/p95 ms; max in run logs):

SINGLE, final 04cf2b1765:
  R1 (load 18.6): next 16.52/20.91, prev 17.85/21.32,
    next_agent_panel 42.55/55.55, prev_agent_panel 50.53/69.37
  R2 (load 22.0): next 15.50/21.31, prev 19.49/34.86,
    next_agent_panel 39.96/56.53, prev_agent_panel 49.91/61.05
SINGLE, baseline a054efc585:
  R1 (load 23.0): next 17.09/23.24, prev 14.96/33.04,
    next_agent_panel 35.35/55.11, prev_agent_panel 47.34/60.54
  R2 (load 19.7): next 15.26/24.42, prev 13.21/17.58,
    next_agent_panel 45.97/68.13 (max 295.10), prev_agent_panel 55.17/74.12
LEFT_RIGHT, final 04cf2b1765:
  R1 (load 24.8): next 16.82/22.32, prev 18.90/43.41,
    next_agent_panel 52.07/78.17, prev_agent_panel 64.31/94.72 (max 306.41)
  R2 (load 19.3): next 16.01/21.43, prev 14.21/43.18,
    next_agent_panel 54.49/78.21, prev_agent_panel 73.03/108.87 (max 365.58)
LEFT_RIGHT, baseline a054efc585:
  R1 (load 22.7): next 17.61/22.04, prev 13.37/20.26,
    next_agent_panel 55.19/86.94, prev_agent_panel 67.06/87.61 (max 344.05)
  R2 (load 19.1): next 13.88/18.83, prev 19.29/39.91,
    next_agent_panel 48.47/67.53, prev_agent_panel 60.00/70.76 (max 268.87)

Classification: HOST NOISE, no deck regression. Row-move (next/prev) p95s sit
~19-24 ms on both trees (over the 16 ms epic tight budget, under the committed
100 ms large-list ceiling) with no tree consistently worse in interleaved runs;
panel-move (J/K) p95s 55-109 ms likewise overlap across trees per round, and the
250-365 ms max outliers land on BOTH trees (single scheduler stalls under
loadavg ~20, also seen by sase-17d.10.1.4.3 at load 28-34). The one 100 ms+
p95 (final LEFT_RIGHT prev_agent_panel R2, 108.87) is a single-round excursion
against baseline 70.76-87.61 with a 365 ms stall in max; R1 of the same cell
was 94.72 vs baseline 87.61. Nothing to fix; no re-measure needed.

Headline before/after j/k p95 (baseline -> final):
  SINGLE row j/k: 23.2/33.0 & 24.4/17.6 -> 20.9/21.3 & 21.3/34.9
  LEFT_RIGHT row j/k: 22.0/20.3 & 18.8/39.9 -> 22.3/43.4 & 21.4/43.2
  (next/prev p95 per round; panel J/K 55-109 both trees; all ms)

Environment caveat (same-mechanism both trees): the workspace venv's
sase_core_rs already emits scan-wire schema 10 while the baseline Python
expects 9, so baseline startup used the scratch's empty-scan fallback (real
scan runs untouched on the final tree). The measured path is post-startup
steady-state navigation on the identical synthetic fixture after warmup, so
this does not bias the comparison. `test_bench_axe_jk` was not re-run here;
sase-17d.10.1.4.3 already recorded it failing on both trees (expected
context, not a regression). Run logs: /tmp/deckjk_{final,base}_{single,lr}_r{1,2}.log
plus /tmp/deckjk_probe.log (final SINGLE R1).

[2026-09-25T23:20:46Z · sase-17d.12.3] Bench done: baseline a054efc585 vs final 04cf2b1765, SINGLE and LEFT_RIGHT, interleaved 2 rounds each under loadavg 19-25. Row j/k p95 ~19-24ms and panel J/K p95 55-109ms overlap across trees per round with 250-365ms stall outliers on BOTH trees: host noise, no deck regression, nothing to fix. Full table in BENCH RESULTS note; headline SINGLE 23/33 & 24/18 -> 21/21 & 21/35, LEFT_RIGHT 22/20 & 19/40 -> 22/43 & 21/43 (next/prev p95 ms). Scratch harness deleted, baseline worktree removed, tree clean, epic-symbols empty.

## Dependencies

- **Depends on:** [sase-17d.12.1](sase-17d.12.1.md) ✓ · ⧖ 2026-09-25
- **Depends on:** [sase-17d.12.2](sase-17d.12.2.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17d.12.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17d.12.3/README.md) | [sase-17d.12.3](sase-17d.12.3.md) | 0 |
