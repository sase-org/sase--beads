# Bead: sase-1ko.6 — Channel-aware, occurrence-exact scoreboard counting and the conformance check

[Bead Pages](../README.md) / [sase-1ko](README.md) / sase-1ko.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.13.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.13.linker.w0.md) · **Assignee:** `sase-1ko.6` · **Size:** medium
**Created:** 2026-10-13 18:10:36 EDT · **Closed:** 2026-10-13 23:18:47 EDT
**Plan:** [202610/e3\_explicit\_delivery\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202610/e3_explicit_delivery_cutover.md)

## Description

channel-counting: count layers across native and explicit channels by occurrence, not containment. Use what partial transcripts show. Add the bundle-marker column and helper marker checks, and associate sessions by marker and session id. Fix the Claude auto-memory and Muse double-attribution misreads. Add the `instructions.conformance` doctor check.

## Notes

[2026-10-14T03:18:34Z · sase-1ko.6] PROPOSED FOLLOW-UP: Stabilize baseline ACE transcript and delivery-plan tests — a clean HEAD snapshot reproduced 8 of 11 selected failures (seven TUI raw-prompt/hint-cache/preview assertions and the delivery-plan fallback-notification monkeypatch); full-check import-budget failure passed in isolation. Phase-specific conformance tests pass after the matching-precedence fix.

[2026-10-14T03:18:47Z · sase-1ko.6] Verified formatting/Ruff/mypy and focused conformance tests (including real channel markers and session-id precedence). Full just check reported 55,612 passed and 27 failures; identified baseline TUI and delivery-plan failures reproduced on clean HEAD and were recorded as a proposed follow-up. epic-symbols reports none.

## Dependencies

- **Depends on:** [sase-1ko.3](sase-1ko.3.md) ✓ · ⧖ 2026-10-13
- **Depends on:** [sase-1ko.5](sase-1ko.5.md) ✓ · ⧖ 2026-10-13
- **Blocks:** [sase-1ko.7](sase-1ko.7.md) ✓ · ⧖ 2026-10-13
- **Blocks:** [sase-1ko.8](sase-1ko.8.md) ✓ · ⧖ 2026-10-13
- **Blocks:** [sase-1ko.9](sase-1ko.9.md) ✓ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1ko.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ko.6/README.md) | [sase-1ko.6](sase-1ko.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`26a12b6`](https://github.com/sase-org/sase/commit/26a12b63df1c995c6d24a408f43991f8cdca0e44) | feat(instructions): add channel-aware conformance scoreboard | [sase-1ko.6](sase-1ko.6.md) | 2026-10-13 23:20:38 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ko.6][1] | Check prior phase notes before planning | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ko.6/README.md

<!-- sase:referenced-by:end -->
