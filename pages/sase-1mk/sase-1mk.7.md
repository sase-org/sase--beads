# Bead: sase-1mk.7 — Fix the link-follow and prompt mid-word Master Gate flakes

[Bead Pages](../README.md) / [sase-1mk](README.md) / sase-1mk.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.11b](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.11b.md) · **Assignee:** `sase-1mk.7` · **Size:** medium
**Created:** 2026-10-18 09:58:30 EDT · **Closed:** 2026-10-18 11:54:41 EDT
**Plan:** [202610/ship\_v0\_18\_0\_owned\_blockers.md](https://github.com/sase-org/sase--plans/blob/main/202610/ship_v0_18_0_owned_blockers.md)

## Description

gate-pilots: root-cause sase-1lr, the bounded-panes scan one-off, and the mid-word peek family including sase-1l7.

## Notes

[2026-10-18T15:54:21Z · sase-1mk.7] Beads/plans link-follow: inventory misses complete MISSING while _loading or pending_query (snapshot already authoritative; truncated archive stays PENDING until deep scan). Mid-word peek: product 350ms reveal unchanged; tests now _hold_reveal_beat and wait_for instead of pause(0.6). Stress 25x pytest -n 8 on the five modules: 106 passed/iter, 0 fail. just fix clean. sase tool run check 84016a2d1df84390d485a2f232e86f0a: lint/mypy/symvision green, 56424 passed, 1 unrelated NEW flake.

[2026-10-18T15:54:22Z · sase-1mk.7] PROPOSED FOLLOW-UP: test_handoff_end_to_end_publishes_one_notification SQLite lock flake — tests/tool/test_settlement_retention.py::test_handoff_end_to_end_publishes_one_notification failed sase tool run check 84016a2d1df84390d485a2f232e86f0a with RuntimeError: tool run store is busy: database is locked (NEW, no owner); isolation pytest passed in 4.02s on this tree. Same signature as open flake sase-18t (already has +1s on this exact node). Untouched by this phase.

[2026-10-18T15:54:41Z · sase-1mk.7] Root-caused sase-1lr (beads/plans inventory miss stayed PENDING while _loading or query-in-flight; complete MISSING from loaded snapshot, keep truncated archive PENDING until deep scan) and sase-1l7 mid-word peek family (tests raced 350ms reveal; hold beat + wait_for). Stress 25x -n 8 of five modules: 106 passed/iter, 0 fail. just fix clean. sase tool run check 84016a2d1df84390d485a2f232e86f0a: lint green, 56424 passed; 1 unrelated settlement_retention SQLite lock flake (sase-18t) isolated-pass 4.02s. Did not close parent sase-1mk or task beads sase-1lr/sase-1l7/sase-1g8.

## Dependencies

- **Blocks:** [sase-1mk.8](sase-1mk.8.md) ✓ · ⧖ 2026-10-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1mk.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1mk.7/README.md) | [sase-1mk.7](sase-1mk.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f27d630`](https://github.com/sase-org/sase/commit/f27d630c8202e735adf6e55561e21f6980ed9811) | fix(tui): complete link-follow misses during pane refresh | [sase-1mk.7](sase-1mk.7.md) | 2026-10-18 11:56:27 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1mk.7][1] | Need current notes and remaining epic-symbol status before close | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1mk.7/README.md

<!-- sase:referenced-by:end -->
