# Bead: sase-zs.5 — Single retrying chokepoint for gh CLI calls

[Bead Pages](../README.md) / [sase-zs](README.md) / sase-zs.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0k6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0k6.md) · **Assignee:** `sase-zs.5` · **Size:** medium
**Created:** 2026-09-12 09:44:53 EDT · **Closed:** 2026-09-12 12:42:27 EDT
**Plan:** [202609/github\_network\_resilience.md](https://github.com/sase-org/sase--plans/blob/main/202609/github_network_resilience.md)

## Description

gh-runner: add one bounded, non-interactive `gh` execution boundary that applies the shared classifier, honors rate-limit and Retry-After signals, and reports structured failures.

## Notes

[2026-09-12T16:41:46Z · sase-zs.5] PROPOSED FOLLOW-UP: Align Python queue/capacity directive handling with linked sase-core queue_capacity wire field — after just check fast-forwarded linked core during verification, full-suite escalation failed 44 queue/capacity tests because collect_queue_fields now returns queue_capacity instead of capacity.

[2026-09-12T16:42:27Z · sase-zs.5] Implemented shared gh runner and JSON wrapper; verified focused pytest tests/test_github_cli.py tests/test_incoming_commits.py pass, ruff on touched files passes, symvision passes with stale phase symbols cleared/re-keyed, and sase bead epic-symbols sase-zs.5 reports no entries. just check reached full-suite escalation and failed only after linked sase-core fast-forwarded to a queue_capacity wire change; recorded PROPOSED FOLLOW-UP on this bead.

## Dependencies

- **Depends on:** [sase-zs.3](sase-zs.3.md) ✓ · ⧖ 2026-09-12
- **Blocks:** [sase-zs.6](sase-zs.6.md) ✓ · ⧖ 2026-09-12
