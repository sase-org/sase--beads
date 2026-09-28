# Bead: sase-1bu.4 — Publishing, convergence, and honest freshness

[Bead Pages](../README.md) / [sase-1bu](README.md) / sase-1bu.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tb.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tb.w0.md) · **Assignee:** `sase-1bu.4` · **Size:** medium
**Created:** 2026-09-27 19:03:23 EDT · **Closed:** 2026-09-28 04:05:00 EDT
**Plan:** [202609/goal\_ledger.md](https://github.com/sase-org/sase--plans/blob/main/202609/goal_ledger.md)

## Description

publish-sync: after each integration, reconcile live markers for touched goals. Mint ids only after a fetch and detect collisions. Add the unpublished outbox, a push leg on the sidecar auto-sync tick, a push-retry counter, a single-flight TTL background fetch, bounded fresh fetches, and the synced-ago watermark.

## Notes

[2026-09-28T08:04:24Z · sase-1bu.4--1] PROPOSED FOLLOW-UP: full just check reports 29 failures (16 NEW incl. agent_completion ordered_groups/humanizes_vcs/no-plan-io, directive tribe_spellings, axe repeat_env n_injected/n_absent/wait_chats, completion snapshot drift, timezone_display_guard, header_panel half-page scroll) that reproduce identically on the clean base tree with this phase stashed; not caused by publish-sync changes

[2026-09-28T08:05:00Z · sase-1bu.4--1] publish-sync done: outbox, chop push leg, push_attempts counters, fetch-before-mint with collision retry, post-integration reconcile (fails open), watermark/sync_status/single-flight fetch worker. Verified: tests/goals/test_goal_publish_sync.py 21 passed; tests/goals+test_bead/test_sync_remote_push 51 passed; ruff clean; toobig clean for touched files; symvision exit 0; epic-symbols empty. Full just check 29 failures reproduce identically on clean base, recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-1bu.3](sase-1bu.3.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bu.5](sase-1bu.5.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bu.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bu.4.md) | [sase-1bu.4](sase-1bu.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6afcdb6`](https://github.com/sase-org/sase/commit/6afcdb67ed2f609c43f8a55d9379fb95ff220814) | feat(goals): publishing, convergence, and honest freshness (sase-1bu.4) | [sase-1bu.4](sase-1bu.4.md) | 2026-09-28 04:07:28 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bu.4--1][1] | Need phase scope and design to repair verify failures | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bu.4.md

<!-- sase:referenced-by:end -->
