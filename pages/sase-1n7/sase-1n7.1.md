# Bead: sase-1n7.1 — Tabs mean pages, the view chip, and the lock

[Bead Pages](../README.md) / [sase-1n7](README.md) / sase-1n7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.52.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.52.linker.w0.md) · **Assignee:** `sase-1n7.1` · **Size:** medium
**Created:** 2026-10-19 17:08:01 EDT · **Closed:** 2026-10-19 19:22:55 EDT
**Plan:** [202610/deck\_scroll\_scope.md](https://github.com/sase-org/sase--plans/blob/main/202610/deck_scroll_scope.md)

## Description

tabs-chip: card tabs only for paged multi-card decks, a solid view chip with a lock replacing auto/fixed, a spread you-are-here title with structural ▴/▾ cues, the jump/cards footer label, and the "locked" vocabulary.

## Notes

[2026-10-19T22:42:44Z · sase-1n7.1] PROPOSED FOLLOW-UP: test_contract_manifest_matches_marker_selection is stale on this tree (extra tests/test_github_actions_install_smoke.py and test_github_actions_testpypi_drill.py) — unrelated to tabs-chip; run just refresh-contract-manifest on the owning change

[2026-10-19T22:42:58Z · sase-1n7.1] PROPOSED FOLLOW-UP: tests/agents_sync/test_commit_publication_bounded_drain.py::test_blocked_render_is_bounded_and_leaves_the_request_queued failed 15s vs 5s under high host load during just check; unrelated to tabs-chip chrome

[2026-10-19T23:22:55Z · sase-1n7.1] Verified tabs-chip chrome: paged multi-card decks show card tabs plus PAGE CARDS/PAGE BLOCKS chip; spread shows you-are-here plus structural up/down cues and no tabs; one-card omits chip and tabs; lock glyph when policy is not AUTO; footer jump vs cards; P help lock copy; locked/unlock palette aliases. Goldens recaptured (one-card and split spread+paged created; chrome updates inspected). TZ=UTC check of the new split golden was clean. sase tool run check 862709acac024df386bb9a589233c091 passed. epic-symbols: no leftovers for sase-1n7.1.

## Dependencies

- **Blocks:** [sase-1n7.2](sase-1n7.2.md) ✓ · ⧖ 2026-10-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n7.1/README.md) | [sase-1n7.1](sase-1n7.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9ece19c`](https://github.com/sase-org/sase/commit/9ece19c4af9e6569769d2e9b85e99a73b71e7d46) | feat(tui): paint deck view as chip, lock, and paged tabs | [sase-1n7.1](sase-1n7.1.md) | 2026-10-19 19:24:26 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1n7.1][1] | Need the phase scope, notes, and remaining work after compaction | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n7.1/README.md

<!-- sase:referenced-by:end -->
