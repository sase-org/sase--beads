# Bead: sase-1eu.7 — Pager three panes with MRU ctrl+w and a target preview

[Bead Pages](../README.md) / [sase-1eu](README.md) / sase-1eu.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ve](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ve.md) · **Assignee:** `sase-1eu.7` · **Size:** medium
**Created:** 2026-10-02 11:34:00 EDT · **Closed:** 2026-10-02 20:13:08 EDT
**Plan:** [202610/three\_pane\_splits.md](https://github.com/sase-org/sase--plans/blob/main/202610/three_pane_splits.md)

## Description

pager-three-panes: behind three_pane_splits, enable pager nest, turn and erase, with transactional third-view mounts and fit refusal. Retarget ctrl+w to the MRU pane with a lifted target frame, show a three-pane footer and help, and add T-shape goldens.

## Notes

[2026-10-03T00:11:59Z · sase-1eu.7] PROPOSED FOLLOW-UP: close sase-1er as fixed by pager-grid-adapter plus this phase (q/Esc/exhausted-Backspace/same-key survivor-mounted Pilot assertions now in tests/pager/test_app_split.py and test_app_three_panes.py, all green)

[2026-10-03T00:12:21Z · sase-1eu.7] PROPOSED FOLLOW-UP: 80x24 and 205x65 live look pass on real pager documents (120x40 covered by inspected T-shape goldens; harness drives sase tui so reaching a live pager needs interactive navigation)

[2026-10-03T00:12:32Z · sase-1eu.7] Findings: sase-1es.6 still open at handoff; proceeded because dependency sase-1eu.6 already landed and this phase builds on its tree (old _ensure_body body API). Rebase onto sase-1es.6 before landing if it merges first.

[2026-10-03T00:13:08Z · sase-1eu.7] Pager three panes behind three_pane_splits verified: nest/turn/erase via press_split(nest=True) with the flag-off rotate preserved; transactional third-view mounts (fit-check, mount, revalidate, publish; orphan removed on race); fit refusal at 7 rows x 32 cols per pane with alternative-naming toasts; 3-pane turn guarded; close of any of the three keeps a live MRU survivor (q/Esc/Backspace/same-key/ctrl+x asserted mounted, rendering, scrolling); ctrl+w captures the MRU target with a 70pct preview frame, doubled focuses it, landing navigates the captured pane with destination-only history and cancels with a message when the target vanished; footer shows ^F/^B pane and armed ^W target glyph+name; help rows and docs/pager.md (one-rule grammar, seven-geometry diagram) updated. Tests: 21 new Pilot tests, model/footer/help unit additions, 5 new 120x40 T-shape+preview goldens (existing goldens byte-identical, visual check-mode clean); full pager suite 661 passed; sase tool run check verdict pass.

## Dependencies

- **Depends on:** [sase-1eu.5](sase-1eu.5.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1eu.6](sase-1eu.6.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1eu.8](sase-1eu.8.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eu.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eu.7/README.md) | [sase-1eu.7](sase-1eu.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e076ff4`](https://github.com/sase-org/sase/commit/e076ff435cbab2f5cf0ba455128a4ee999bc3c40) | feat(pager): three-pane nest/turn/erase with MRU ctrl+w preview | [sase-1eu.7](sase-1eu.7.md) | 2026-10-02 20:15:26 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eu.7][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eu.7/README.md

<!-- sase:referenced-by:end -->
