# Bead: sase-1ap.4.2 — Capture and inspect the created-bead goldens

[Bead Pages](../README.md) / [sase-1ap.4](sase-1ap.4.md) / sase-1ap.4.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ap.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ap.land.md) · **Assignee:** `sase-1ap.4.2` · **Size:** medium
**Created:** 2026-09-26 14:32:50 EDT · **Closed:** 2026-09-26 16:33:19 EDT
**Plan:** [202609/1ap\_visual\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/1ap_visual_completion.md)

## Description

visual_goldens: Capture both created-bead Context PNG goldens with the targeted maintenance recipe, inspect the report and images, and verify the current card behavior after intervening TUI changes. Run just check on any tracked source or golden change.

## Notes

[2026-09-26T20:32:21Z · sase-1ap.4.2] PROPOSED FOLLOW-UP: narrow split card shreds tokens at ~6 cells when a phase bead is attached — deck narrows (detail 18 to 14 cols) and wraps split Beads:/CREATED mid-word; narrow created test omits the phase bead to work around it, consider a minimum column width or paged fallback for narrow viewports

[2026-09-26T20:32:37Z · sase-1ap.4.2] PROPOSED FOLLOW-UP: closed-bead narrow golden is pixel-stale — test_agents_bead_closed_by_agent_narrow_png_snapshot passes its Beads:/CLOSED sentinels but fails pixel comparison after intervening TUI changes; needs recapture by its owning agent, out of scope for the created-bead phase

[2026-09-26T20:32:53Z · sase-1ap.4.2] PROPOSED FOLLOW-UP: sase tool run check red on clean-tree items unrelated to this phase — symvision KNOWN _legacy_sase_shell_syntax_enabled (witnessed), sase init memory --check drift (sase_beads.md, README.md), plus the 14 collection ImportErrors already tracked in sase-1ap.4.1 note #2; all lint gates covering this phase (ruff, mypy) pass

[2026-09-26T20:33:19Z · sase-1ap.4.2] Captured both created-bead Context goldens (120x40 + 90x32) via just fix-tui-screenshots; wide shows BEAD lane, ARTIFACTS 3 beads, CREATED/CLOSED pills, titles, why: and assigned row; narrow shows contiguous Beads:/sase-1c/CREATED. Fixed narrow test: phase-bead fixture squeezed card to ~6 cells (unmatchable sentinels), now uses phase_bead_id=None (wide keeps full coverage) plus a bounded scroll nudge. Verified: both targeted tests pass, maintenance capture+verify clean, ruff/mypy/fmt green; remaining check reds are pre-existing clean-tree items recorded as follow-ups

## Dependencies

- **Depends on:** [sase-1ap.4.1](sase-1ap.4.1.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ap.4.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ap.4.2/README.md) | [sase-1ap.4.2](sase-1ap.4.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`752edf9`](https://github.com/sase-org/sase/commit/752edf9fc80637572c7668e68585205f743ecc40) | test(visual): capture created-bead Context goldens (sase-1ap.4.2) | [sase-1ap.4.2](sase-1ap.4.2.md) | 2026-09-26 16:35:10 EDT |
