# Bead: sase-m4.5 — Resolve the artifact-scan performance failure

[Bead Pages](../README.md) / [sase-m4](README.md) / sase-m4.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.01o](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.01o.md) · **Assignee:** `sase-m4.5` · **Size:** small
**Created:** 2026-08-14 14:20:31 EDT · **Closed:** 2026-08-14 14:42:16 EDT
**Plan:** [202608/stabilize\_github\_actions.md](https://github.com/sase-org/sase--plans/blob/main/202608/stabilize_github_actions.md)

## Description

performance-floor: use repeatable measurements to optimize a regression or evidence a narrowly calibrated threshold.

## Notes

[2026-08-14T18:40:12Z · sase-m4.5] PROPOSED FOLLOW-UP: investigate full-suite-only TUI flakes — just check escalated to the full pytest suite and failed tests/ace/tui/modals/test_snippet_name_modal.py::test_matches_filter_order_and_tab_completion plus tests/ace/tui/test_logs_pane.py::test_logs_tab_g_and_shift_g_scroll_detail_extremes, but both passed when rerun directly.

[2026-08-14T18:42:16Z · sase-m4.5] Updated scan_agent_artifacts synthetic_6p_200pp scan_facade floor to 2.15x with 2026-08-14 repeated measurements/profile rationale. Verified just install; just bench-agent-scan target runs x3 (medians 241.38, 247.51, 245.47 ms); just phase7-perf-check passed twice (agent-scan medians 240.69 and 241.31 ms under 257.98 ms ceiling); failed full-suite just check once on two unrelated TUI flakes that passed directly and were recorded as PROPOSED FOLLOW-UP; reran just check and it passed.

[2026-08-14T18:43:16Z · sase-m4.5] Verified targeted agent-scan medians 241.38, 247.51, 245.47 ms; just phase7-perf-check passed twice with medians 240.69 and 241.31 ms; just check passed on rerun.

## Dependencies

- **Blocks:** [sase-m4.6](sase-m4.6.md) ✓ · ⧖ 2026-08-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m4.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m4.5/README.md) | [sase-m4.5](sase-m4.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7a6e004`](https://github.com/sase-org/sase/commit/7a6e00416f21519d27f4ff6ca0fa2970862f033a) | perf: recalibrate agent scan regression floor | [sase-m4.5](sase-m4.5.md) | 2026-08-14 14:43:50 EDT |
