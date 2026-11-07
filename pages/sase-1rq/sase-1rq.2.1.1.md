# Bead: sase-1rq.2.1.1 — Keep Master Gate green at the master tip

[Bead Pages](../README.md) / [sase-1rq.2.1](sase-1rq.2.1.md) / sase-1rq.2.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.md) · **Assignee:** `sase-1rq.2.1.1` · **Size:** medium
**Created:** 2026-11-07 10:24:47 EST · **Closed:** 2026-11-07 12:15:36 EST
**Plan:** [202611/sase\_ci\_green.md](https://github.com/sase-org/sase--plans/blob/main/202611/sase_ci_green.md)

## Description

master-gate: Master Gate is red at tip 0ba9cfc9 (run 42373447720). Its only failure is test (3) at tests/ace/tui/test_epic_panel_arrival_frames.py::test_selection_stays_highlighted_and_scrolled_into_view ('frame 11: row 14 outside scroll 2+12'). Prove whether it is deterministic or flaky on an unchanged tree. Root-cause it if you can; otherwise quarantine it with a flake follow-up. Then fix any other Master Gate red at the current tip.

## Notes

[2026-11-07T16:43:55Z · sase-1rq.2.1.1] ROOT-CAUSED both Master Gate reds (no quarantine). (1) test_epic_panel_arrival_frames::test_selection_stays_highlighted_and_scrolled_into_view (run 42373447720, test (3)): 0/54 local repros under taskset 1-2 CPU contention, but tracing showed #agent-list-container transiently grows one row (23->24) in a layout pass; an insert landing in that window needs no scroll, and when the container shrinks back Textual only clamps scroll, so the selection stays off-screen unless a later refresh highlight pass happens to re-scroll. Forcing that ordering in the real harness (terminal +1 row before plain_member, -1 after it settles) reproduces CI verbatim ("frame 11: row 14 outside scroll 2+12") without the fix and passes with it. Fix: AgentList._size_updated re-scrolls a highlight that was visible before a resize and is not after (user scroll-away left alone); new tests/ace/tui/widgets/test_agent_list_resize_keeps_highlight.py (2 of 3 fail without the fix). Targeted visual check (9 agents-tab files, 48 goldens): captures byte-identical with and without the fix; the 13 drifts there are pre-existing sase-1r2.6 territory. (2) test_event_driven_pause_fixture::test_fixture_patch_does_not_leak_from_previous_test (run 42386100885, test (7)): order-dependent on a sibling test under run_pytest --dist worksteal; fails deterministically when run alone on the unchanged tree. Rewritten order-independent: asserts the fixture wrapper __wrapped__ is the real pause (plus the sentinel check when the override test ran first); verified it now catches a real leak from a non-TUI test that the old assertion missed. sase tool run check 28399ac1 passed.

[2026-11-07T17:15:36Z · sase-1rq.2.1.1--1] Master Gate green from fix commit c732c6e3 onward: run 42392919193 (c732c6e3, the fix: AgentList._size_updated re-scrolls a highlight that a viewport shrink hid, plus an order-independent rewrite of test_fixture_patch_does_not_leak_from_previous_test) = success, every job success; next push run 42393473755 (ab6b14fb) = success. Earlier reds 42373447720 (test_selection_stays_highlighted_and_scrolled_into_view) and 42386100885 (pause-fixture leak test ordering under worksteal) were root-caused: the first was reproduced deterministically (grow -> insert -> shrink), the second fails every time when run alone on the clean tree. Both pass with the fix. sase tool run check 28399ac1 passed. No epic symbols remain. No workflow, timeout or gate setting was changed.

## Dependencies

- **Blocks:** [sase-1rq.2.1.7](sase-1rq.2.1.7.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.2.1.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.1.1.md) | [sase-1rq.2.1.1](sase-1rq.2.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c732c6e`](https://github.com/sase-org/sase/commit/c732c6e38e7b5cc3c270a9c60acb7a800186b593) | fix(tui): keep a visible agent-list highlight on screen across resizes | [sase-1rq.2.1.1](sase-1rq.2.1.1.md) | 2026-11-07 11:45:47 EST |
