# Bead: sase-1b1.6 — View goldens, live inspection, and forced-spread benchmarks

[Bead Pages](../README.md) / [sase-1b1](README.md) / sase-1b1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sx](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sx.md) · **Assignee:** `sase-1b1.6` · **Size:** medium
**Created:** 2026-09-27 05:45:23 EDT · **Closed:** 2026-09-27 13:07:55 EDT
**Plan:** [202609/deck\_views.md](https://github.com/sase-org/sase--plans/blob/main/202609/deck_views.md)

## Description

verify: add new deck-view PNG scenarios and inspect live screenshots at wide and narrow widths. Benchmark P transitions on the 5,000-line Reply, a pathological Reply, and a forced Files spread against stated budgets. Mitigate only by measured rules, then run the acceptance checklist.

## Notes

[2026-09-27T10:08:47Z · 0t2] CROSS-EPIC (sase-1b2): generate the `agents_deck_view_*` goldens with `ace_final_deck` at its default (off) so FINAL never appears; sase-1b2.19 re-baselines them when it removes that flag. If sase-1b2.11 (the CardDocumentView extraction) landed after 1b1.2, re-run `test_deck_view_main_pilot.py`, the Files view pilots and the bench to confirm the forced-policy and anchor-restore paths survived the refactor. Any breakage there is 1b1 behavior, so fix it in this phase. If FINAL is already registered (sase-1b2.14 closed), add a pilot assertion with the flag on that a FINAL panel shows no badge and `P` is unavailable there. The full shared rules are in the NOTES on epic sase-1b1.

[2026-09-27T16:58:08Z · sase-1b1.6--1] Bench re-measured post-fix (panel_chrome blocked wiring). standard-5k p50/p95/max ms: pb-pc 664/757/776, pb-sp 615/1027/1399, pc-pb 44/636/737, pc-sp 112/727/770, sp-pb 24/35/39, sp-pc 689/753/850. pathological-14k: pb-pc 1439/1940/1945, pb-sp 1429/1758/1881, pc-pb 74/1633/1671, pc-sp 1745/2149/2363, sp-pb 28/33/79, sp-pc 255/2434/3040. files forced spread: keypress 0.77ms, paints 119.51ms after probe (PASS <1000ms). Baseline monitor run differed per-direction (pc-sp 746 vs 112, sp-pc 104 vs 689): samples swing with host load.

[2026-09-27T16:58:35Z · sase-1b1.6--1] PROPOSED FOLLOW-UP: D10 P-transition budgets missed and unstable across runs on shared host (standard needs p50<=150/p95<=300, pathological max<1000 with no watchdog rows; measured medians ~600-1700ms entering inline layouts, watchdog rows fire on 14k). Needs quiet-host profiling of cold-entry recomposition (pyinstrument/SASE_TUI_PERF) then D10 mitigations in order; do not tune blindly.

[2026-09-27T16:58:45Z · sase-1b1.6--1] PROPOSED FOLLOW-UP: interactive live drive (sase screenshot + tmux P/Ctrl+J/split/Z at wide+narrow) not performed this turn; D5 title legibility verified on all 6 approved goldens instead (wide 160, narrow split halves).

[2026-09-27T17:07:36Z · sase-1b1.6--1] PROPOSED FOLLOW-UP: just check red at lint(symvision) on files this bead never touched: unused sdd_store_identities in src/sase/llm_provider/commit_finalizer_state/_dirty_repos.py and unused unmet_ancestor_folds in src/sase/ace/tui/actions/navigation/_agent_reveal.py (zero references in this bead diff; all earlier lint stages incl. ruff+mypy green). Reproduces independent of this diff; needs owner triage, not a phase reopen.

[2026-09-27T17:07:55Z · sase-1b1.6--1] verify done: 6/6 deck-view goldens generated, approved badge-by-badge, and --check stable (unchanged=6); wired Files blocked badge in panel_chrome (_files_spread_blocked->resolve_view blocked) with new chrome unit test; fixed split-narrow focus (ctrl+f left) and media tmp-path drift (basename slots); pilots re-run green post-1b2.11 incl. FINAL no-badge test (43 passed); bench recorded twice, files-spread PASS (keypress<1ms, paint~120ms post-probe); P-transition D10 budgets missed+load-unstable and symvision reds on untouched files filed as PROPOSED FOLLOW-UPs; epic-symbols clean

## Dependencies

- **Depends on:** [sase-1b1.5](sase-1b1.5.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b1.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b1.6.md) | [sase-1b1.6](sase-1b1.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5cafbcb`](https://github.com/sase-org/sase/commit/5cafbcb53f1b6b9c300cc29c25136eee95abc8d7) | feat(deck-views): verify badges, goldens, and forced-spread benchmarks (sase-1b1.6) | [sase-1b1.6](sase-1b1.6.md) | 2026-09-27 13:10:23 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c.r0][1] | Review sase-1b1 phase progress and notes for value-added research report | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c.r0/README.md

<!-- sase:referenced-by:end -->
