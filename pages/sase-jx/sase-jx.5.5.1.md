# Bead: sase-jx.5.5.1 — Align the chop-detail API documentation with selected-run rendering

[Bead Pages](../README.md) / [sase-jx.5.5](sase-jx.5.5.md) / sase-jx.5.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-jx.5.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-jx.5.land/README.md) · **Assignee:** `sase-jx.5.5.1` · **Size:** xsmall
**Created:** 2026-08-12 14:02:32 EDT · **Closed:** 2026-08-12 14:17:20 EDT
**Plan:** [202608/finish\_jx5\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202608/finish_jx5_landing.md)

## Description

align_selected_run_contract: update the stale update_chop_display argument documentation that still says the header only describes the newest sampled run and run_idx zero; document the actual schema-v2 behavior in which run_ratios is aligned to raw history and the displayed run index controls the overrun segment, then run the focused status-section tests and the repository check required for a source change.

## Notes

[2026-08-12T18:17:20Z · sase-jx.5.5.1] Updated update_chop_display's overrun docstring to describe schema-v2 behavior: run_ratios is aligned to raw run history and the header segment renders overrun.run_ratios[run_idx] for whichever raw run is selected (not only run_idx=0). Ran focused tests/ace/tui/widgets/test_axe_dashboard_status_section.py (14 passed) and just check (all lint gates + escalated full test suite passed, exit 0).

[2026-08-12T18:18:07Z · sase-jx.5.5.1] Fixed update_chop_display docstring to describe schema-v2 behavior: overrun segment reflects overrun.run_ratios[run_idx] for the selected raw run, not just the newest run. Verified via focused status-section tests (14 passed) and full just check (all lint gates + escalated full test suite, exit 0).

## Dependencies

- **Blocks:** [sase-jx.5.5.2](sase-jx.5.5.2.md) ✓ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-jx.5.5.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-jx.5.5.1/README.md) | [sase-jx.5.5.1](sase-jx.5.5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c184102`](https://github.com/sase-org/sase/commit/c18410204785d62e7017ebba119f9c59f1ef301b) | docs(ace): fix update\_chop\_display docstring for selected-run overrun | [sase-jx.5.5.1](sase-jx.5.5.1.md) | 2026-08-12 14:19:04 EDT |
