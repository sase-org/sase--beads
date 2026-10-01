# Bead: sase-1ef.2 — State pill, past frame, destination footer, and versioned trail

[Bead Pages](../README.md) / [sase-1ef](README.md) / sase-1ef.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0v2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0v2.md) · **Assignee:** `sase-1ef.2` · **Size:** medium
**Created:** 2026-10-01 15:31:47 EDT · **Closed:** 2026-10-01 18:24:35 EDT
**Plan:** [202610/pager\_version\_clarity.md](https://github.com/sase-org/sase--plans/blob/main/202610/pager_version_clarity.md)

## Description

badge: route every history colour through a theme-aware style set; replace the subject chip with a four-state pill; draw a past-accent gutter rail through pinned bodies; make the footer name where each time key goes; suffix trail crumbs with their version; add a pill legend to help.

## Notes

[2026-10-01T22:24:00Z · sase-1ef.2] PROPOSED FOLLOW-UP: full-check flake tests/test_agent_name_registry_rebuild_pending.py::test_registry_rebuild_keeps_live_identity_pending_claim failed once in the 51k-test scoped lane but passes in isolation (8 passed) and has zero references to pager code; likely parallel-lane interference, needs a re-run/triage

[2026-10-01T22:24:14Z · sase-1ef.2] PROPOSED FOLLOW-UP: white block artifact at the left edge of dirty now-strip time-band rows (visible in history_dirty and timeband_now goldens, pre-exists this phase); band phase sase-1ef.3 owns that row

[2026-10-01T22:24:35Z · sase-1ef.2] Badge phase done and verified: HistoryStyles theme set passes contrast/hue rules on all 20 builtin themes (new test_history_styles.py, 9 tests); four-state pill with fixed shedding forms replaces the chip, pill never cropped (widths 30-200 loop); past/deleted gutter rail with goto>change>rail precedence and blue changed marks; destination footer verbs with single E; versioned trail suffixes shed before label truncation; pill legend in help. Unit suites green (163 passed incl. app_history/app_history_diff/timeline/provider), just check lint gates green (ruff/mypy/symvision/fmt), targeted PNG goldens regenerated + new history_past-frame (visual --check clean, 58 unchanged). One full-check scoped-lane failure in test_agent_name_registry_rebuild_pending is unrelated (passes isolated, no pager refs) and recorded as follow-up.

## Dependencies

- **Depends on:** [sase-1ef.1](sase-1ef.1.md) ✓ · ⧖ 2026-10-01
- **Blocks:** [sase-1ef.3](sase-1ef.3.md) ◐ · ⧖ 2026-10-01
- **Blocks:** [sase-1ef.4](sase-1ef.4.md) ◐ · ⧖ 2026-10-01

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ef.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ef.2/README.md) | [sase-1ef.2](sase-1ef.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e0bdb33`](https://github.com/sase-org/sase/commit/e0bdb334e9ad678d05dc7a621c2f2251cb09f677) | feat(pager): state pill, past frame, destination footer, and versioned trail | [sase-1ef.2](sase-1ef.2.md) | 2026-10-01 18:43:14 EDT |
