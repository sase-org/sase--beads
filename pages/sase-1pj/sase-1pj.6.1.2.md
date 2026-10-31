# Bead: sase-1pj.6.1.2 — Recover pipe and inline successors exactly once

[Bead Pages](../README.md) / [sase-1pj.6.1](sase-1pj.6.1.md) / sase-1pj.6.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pj.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.6.md) · **Assignee:** `sase-1pj.6.1.2` · **Size:** medium
**Created:** 2026-10-31 08:56:54 EDT · **Closed:** 2026-10-31 12:35:23 EDT
**Plan:** [202610/staged\_handoff\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202610/staged_handoff_recovery.md)

## Description

successor-replay: persist successor identity before continuation side effects, replay pipe adoption without allocating another successor, and provide the common detached continuation path used when the original runner is gone.

## Notes

[2026-10-31T16:35:01Z · sase-1pj.6.1.2] PROPOSED FOLLOW-UP: Restore the TUI app import-budget gate on the clean base — the current and merge-base closures both load 2863 sase.* modules against the 2861 cap, with zero module delta; attribute and defer the existing excess or update its named rationale.

[2026-10-31T16:35:06Z · sase-1pj.6.1.2] PROPOSED FOLLOW-UP: Stabilize create-project availability under full-suite xdist load — the review-button test observed `checking` after 0.6 seconds once in the full 4-worker suite, then passed in the focused rerun.

[2026-10-31T16:35:23Z · sase-1pj.6.1.2] Implemented persisted successor identity and replay for staged pipe/inline handoffs, detached delivery, loop restoration, and exact launch timestamps. Verified the targeted recovery suites (24 passed plus detached-child tests) and marker-path audit. `sase tool run check` passed formatting, Ruff, mypy, Symvision, and the other lint/validation stages; scoped tests reported 59,391 passed, 17 skipped, and 3 failures. The marker-audit failure was fixed and its targeted suite passed; the create-project timing failure passed on focused rerun. Recorded follow-ups for the clean-base TUI import-budget excess (2863 vs cap 2861, zero import-closure delta) and the xdist timing flake. `epic-symbols` reports no leftovers for this phase; the two public API symbols are keyed to open recovery phase sase-1pj.6.1.6.

## Dependencies

- **Depends on:** [sase-1pj.6.1.1](sase-1pj.6.1.1.md) ✓ · ⧖ 2026-10-31
- **Blocks:** [sase-1pj.6.1.3](sase-1pj.6.1.3.md) ◐ · ⧖ 2026-10-31
- **Blocks:** [sase-1pj.6.1.6](sase-1pj.6.1.6.md) ◐ · ⧖ 2026-10-31

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.6.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.6.1.2/README.md) | [sase-1pj.6.1.2](sase-1pj.6.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9c17b84`](https://github.com/sase-org/sase/commit/9c17b8454bfd553f6888e2b91717fbb23e12646e) | feat(axe): replay staged successors exactly once | [sase-1pj.6.1.2](sase-1pj.6.1.2.md) | 2026-10-31 12:37:04 EDT |
