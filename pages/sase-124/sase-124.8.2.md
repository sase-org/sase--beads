# Bead: sase-124.8.2 — Preserve attention refresh intent without delaying local surfaces

[Bead Pages](../README.md) / [sase-124.8](sase-124.8.md) / sase-124.8.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-124.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-124.land.md) · **Assignee:** `sase-124.8.2` · **Size:** medium
**Created:** 2026-09-17 17:43:31 EDT · **Closed:** 2026-09-17 19:33:01 EDT
**Plan:** [202609/finish\_agents\_freshness.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_agents_freshness.md)

## Description

attention-scheduling: detach cache and network attention work from local ticks, preserve stronger pending network requests, and record poll duration and mode with deterministic scheduling regressions.

## Notes

[2026-09-17T23:32:18Z · sase-124.8.2] PROPOSED FOLLOW-UP: investigate full-suite-only loader cleanup decoupling flake — `just check` escalated to the governed full test lane and failed `tests/ace/tui/test_loader_cleanup_decoupling.py::test_rows_apply_and_loading_clears_while_cleanup_is_blocked`; immediate reruns of that test and the whole file passed in this workspace.

[2026-09-17T23:33:01Z · sase-124.8.2] Implemented detached attention inventory scheduling with mode-aware coalescing and completed-poll trace counters. Verified .venv/bin/pytest -q tests/ace/tui/test_remote_lifecycle_actions.py tests/ace/tui/test_event_handlers_auto_refresh_dirty_flags.py (66 passed), reproduction artifact file:explicit:7149138b09eabe6ff5ba5226 shows [true,false] network preservation and Agents refresh before blocked cache release, .venv/bin/pytest -q tests/ace/tui/test_loader_cleanup_decoupling.py (6 passed), and epic-symbols reports no entries. Ran just check; it escalated to the governed full test lane and failed one unrelated full-suite-only loader cleanup test that passed on immediate single-test and file reruns; recorded PROPOSED FOLLOW-UP on this phase.

## Dependencies

- **Depends on:** [sase-124.8.1](sase-124.8.1.md) ✓ · ⧖ 2026-09-17
- **Blocks:** [sase-124.8.3](sase-124.8.3.md) ✓ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-124.8.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-124.8.2/README.md) | [sase-124.8.2](sase-124.8.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9a1d5d6`](https://github.com/sase-org/sase/commit/9a1d5d67a2ba99549dbd5ae5fbbc6cf533abf64a) | fix(tui): detach attention inventory polling | [sase-124.8.2](sase-124.8.2.md) | 2026-09-17 19:35:58 EDT |
