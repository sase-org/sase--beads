# Bead: sase-1vd.4 — Discoverability cues on the question pane

[Bead Pages](../README.md) / [sase-1vd](README.md) / sase-1vd.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1gp](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1gp.md) · **Assignee:** `sase-1vd.4` · **Size:** small
**Created:** 2026-11-26 10:49:29 EST · **Closed:** 2026-11-26 15:58:00 EST
**Plan:** [202611/question\_copy\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202611/question_copy_panel.md)

## Description

pane-cues: show copy progress on the question pane border, underline declared snippets in the prose, and list declared items missing from the prose in a muted "also copyable" block so no copiable value is hidden.

## Notes

[2026-11-26T20:11:03Z · sase-1vd.4] PROPOSED FOLLOW-UP: 80x24 question-text scroll box exports empty even on the pre-change code path (plain-str Static, also-block hidden) — investigate whether #user-question-text-scroll renders for real users at 80x24 or is an SVG-export-only artifact

[2026-11-26T20:57:51Z · sase-1vd.4--1] PROPOSED FOLLOW-UP: sase tool run check full lane failed only on tests/test_global_state_leak_detector.py::test_fail_on_poison_mode_fails_pytest_on_poison and ::test_protocol_drain_clears_refresh_thread_restarted_after_fixtures (both 60s subprocess timeouts under xdist load, gw5); both pass 3/3 in isolation on this tree and on the clean base tree, and the whole detector file + new pane-cues tests pass together under -n 4 (38 passed); matches known flake class tracked by sase-t6 for this file under the full parallel lane

[2026-11-26T20:58:00Z · sase-1vd.4--1] Pane cues done and verified: 12 tests in tests/ace/tui/test_question_pane_cues.py pass; 3 new PNG goldens captured/inspected; copy-panel goldens rechecked clean; ruff/mypy/symvision gates green. Full check lane showed only 2 failures in tests/test_global_state_leak_detector.py, both 60s subprocess timeouts under xdist load that pass 3/3 in isolation on this tree and on the clean base tree and match the known sase-t6 flake class for that file; recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-1vd.3](sase-1vd.3.md) ✓ · ⧖ 2026-11-26
- **Blocks:** [sase-1vd.5](sase-1vd.5.md) ◐ · ⧖ 2026-11-26
- **Blocks:** [sase-1vd.7](sase-1vd.7.md) ✓ · ⧖ 2026-11-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vd.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vd.4.md) | [sase-1vd.4](sase-1vd.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`758745c`](https://github.com/sase-org/sase/commit/758745cb400d7846cd630ee0285e4a58a1036ec3) | feat(ace): show copy progress cues on the question pane | [sase-1vd.4](sase-1vd.4.md) | 2026-11-26 15:59:37 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1vd.4--1][1] | Need the phase scope and design file for close triage after check failure | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vd.4.md

<!-- sase:referenced-by:end -->
