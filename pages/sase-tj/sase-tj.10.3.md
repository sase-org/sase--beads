# Bead: sase-tj.10.3 — Put the Agent pane in the fast-startup inventory and rebaseline the goldens

[Bead Pages](../README.md) / [sase-tj.10](sase-tj.10.md) / sase-tj.10.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-tj.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-tj.land.md) · **Assignee:** `sase-tj.10.3` · **Size:** medium
**Created:** 2026-08-25 15:02:48 EDT · **Closed:** 2026-08-25 18:43:08 EDT
**Plan:** [202608/agent\_pane\_landing\_gaps.md](https://github.com/sase-org/sase--plans/blob/main/202608/agent_pane_landing_gaps.md)

## Description

visual: add the agents descriptor to _fast_artifacts_subtabs so the whole fast-policy corpus renders the shipped sub-tab strip, rebaseline every affected artifacts_* PNG golden, add the six Agent-pane snapshots the parent epic's land phase required, and give the mount test a bounded wait so it stops flaking under the parallel lane.

## Notes

[2026-08-25T22:43:08Z · sase-tj.10.3] Verified epic-symbols empty; just check passed; just test-visual -q passed with 810 passed, 1 skipped; Agent pane visual snapshots, mount/navigation focus tests, and artifacts j/k benchmark passed.

[2026-08-25T23:02:04Z · sase-tj.10.3] PROPOSED FOLLOW-UP: Stabilize AXE constrained-width visual snapshot wait — full `just test-visual -q` repeatedly times out in `test_axe_constrained_width_no_wrap_png_snapshot` under xdist while the node passes in isolation.

## Dependencies

- **Depends on:** [sase-tj.10.2](sase-tj.10.2.md) ✓ · ⧖ 2026-08-25

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e8de34f`](https://github.com/sase-org/sase/commit/e8de34fe0c52a13610fd78ae865f982ffde1b4c6) | feat: Put the Agent pane in the fast-startup inventory and rebaseline and rebase the goldens (sase-tj.10.3) | [sase-tj.10.3](sase-tj.10.3.md) | 2026-08-26 06:37:43 EDT |
