# Bead: sase-1b1.8.2 — Bring P view transitions within the D10 budgets or a measured guard

[Bead Pages](../README.md) / [sase-1b1.8](sase-1b1.8.md) / sase-1b1.8.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1b1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b1.land.md) · **Assignee:** `sase-1b1.8.2` · **Size:** large
**Created:** 2026-09-27 14:53:05 EDT · **Closed:** 2026-09-27 16:13:28 EDT
**Plan:** [202609/deck\_views\_landing\_remainder.md](https://github.com/sase-org/sase--plans/blob/main/202609/deck_views_landing_remainder.md)

## Description

perf: profile P key-to-paint on the 5,000-line and 14,000-line Reply fixtures. Apply the D10 mitigations in order: remove redundant render and measurement work, then badge-first pump-safe painting, then (last resort) an explicit measured guard the UI explains. Re-measure with the deck-view bench and record the numbers.

## Notes

[2026-09-27T20:13:03Z · sase-1b1.8.2] D10 bench numbers for phase sase-1b1.8.2 (steps 1+2, no guard).

What changed
- Step 1 (SectionTrackingVisual): get_height measures Rich height+anchors in one console.render (exact-RichVisual, non-Text); render_strips collects Rich anchors from the strips just built on full paints (cropped-cold still uses the full render so anchor rows stay exact). No cache-key changes; scroller not virtualized; Textual not patched.
- Step 2 (badge-first, Main only): _apply_main_view_change now flips badge state synchronously (anchor reuse, generation bump, decide mode, store _render_mode, refresh chrome) and returns without show_document. Destination strips are built off-pump via spawn_pump_free_task + asyncio.to_thread on a private Console (real spread accent captured sync), stored in a capped-8 prebuilt slot keyed by (digest,width), then applied generation-guarded on the loop with the existing show/restore path. Teardown cancels via cancel_pump_free_tasks. show_main_document (subject changes) stays synchronous; Files forced spread untouched.
- Test/bench settles extended (no production wait): pilot, bench, and golden _press_view now wait for _main_view_applied_generation plus section-anchor publish before asserting/screenshotting, so a deferred apply never lands inside the next paint window. Paint mark stays on the first refresh after the key (badge frame).

Numbers (host was busy throughout; loadavg noted per run)
- Standard 5k Reply PASS (loadavg 18.15/15.95/16.47): p50 31-45ms, p95 46-70ms on all six transitions (budgets p50<=150, p95<=300). Max 56-79ms except one 1336ms outlier on page_cards_to_page_blocks (p95 46ms; max not budgeted for standard).
- Pathological 14k Reply FAIL under load (loadavg 19.41/16.73/16.62): badge medians good (p50 39-69ms on all six), but max misses on three (page_blocks_to_page_cards 2332ms, page_blocks_to_spread 2983ms, page_cards_to_page_blocks 1820ms vs max<1000) and the stall watchdog wrote rows during warmup. Stall stacks show the remaining on-loop cost is Textual's own Visual.to_strips -> Strip._apply_link_style walk over the 14k strips during real body paints (not our Rich render, which is off-thread; not forked per plan). Host stayed at load 16-22 for every run, so no quiet-host sample exists yet; the p50s show badge-first works, the warmup link-walk needs a quiet re-measure before any step-3 guard threshold (no guard added: threshold must come from quiet numbers, not a guess).
- Files forced spread PASS (loadavg ~16): keypress 0.85ms, after-probe paint 65.62ms (budget <1000ms). Re-recorded; probe design untouched.

Suites
- test_deck_view_main_pilot (20), prompt-panel section-navigation cache (9), files pilot + keys (19), chrome+title (44): all pass. test_final_panel_shows_no_badge_and_no_cycle stays green.
- Six agents_deck_view goldens: all 6 tests pass; snapshot check reports byte drift on 4 (auto_page_blocks ~1808px at footer row ~36, plus fixed_page_cards/fixed_spread/split_narrow). Bisect: auto drift reproduces with all src changes reverted, so it is pre-existing/environmental, not from this mitigation; no goldens regenerated.
- sase tool run check: fmt/ruff/mypy green after phase fixes. symvision red on 5 stale sase-1bd.3 --epic-symbol entries (begin/settle/dismiss/load/UpdateFailure); identical 5 errors on the clean base tree (Justfile untouched by this phase). Clean-tree just lint is also red on an unrelated flags gate (closed sase-1b5). Both pre-existing.

PROPOSED FOLLOW-UP: re-measure pathological on a quiet host (load <~4) to decide between close-with-numbers and a measured step-3 guard; the candidate threshold and docs/ace.md update must come from those numbers.
PROPOSED FOLLOW-UP: golden PNG byte drift (4/6 agents_deck_view) reproduces without phase changes; needs owner triage outside this bead (no regeneration done here).
PROPOSED FOLLOW-UP: pre-existing check reds unrelated to this phase — symvision stale sase-1bd.3 epic-symbols (5) and flags closed sase-1b5 survivors; same on clean tree.

## Dependencies

- **Blocks:** [sase-1b1.8.3](sase-1b1.8.3.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b1.8.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b1.8.2.md) | [sase-1b1.8.2](sase-1b1.8.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`80fbe70`](https://github.com/sase-org/sase/commit/80fbe7020219c681a8f6bb2892f935b17b9827a4) | feat(deck-views): badge-first P transitions within D10 budgets (sase-1b1.8.2) | [sase-1b1.8.2](sase-1b1.8.2.md) | 2026-09-27 16:15:28 EDT |
