# Bead: sase-19f.6.3 — Accept and preserve multiplier capacity in wait and directive editors

[Bead Pages](../README.md) / [sase-19f.6](sase-19f.6.md) / sase-19f.6.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-19f.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-19f.land.md) · **Assignee:** `sase-19f.6.3` · **Size:** medium
**Created:** 2026-09-26 04:40:45 EDT · **Closed:** 2026-09-26 07:43:03 EDT
**Plan:** [202609/queue\_multiplier\_surfaces.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_multiplier_surfaces.md)

## Description

edit-capacity: Teach the wait modal, wait actions, directive persistence, agent directive command, and prompt queue editing to accept <M>x through the Rust-backed parser. Prefill authored 1.5x, clear the opposite capacity form on edits, and preserve the multiplier on priority-only or weight-only changes. Add focused modal, persistence, and prompt-edit tests; run just check in sase.

## Notes

[2026-09-26T11:37:18Z · sase-19f.6.3--1] PROPOSED FOLLOW-UP: just check symvision red on stale --epic-symbol entries for closed beads sase-19x.4 (phase_card_block, block_meta_for_session_shell, session_reply_heading) and sase-1aa.4 (PolicyViolation, check_shipped_model_policy, format_policy_violations, validate_manifest_policy, validate_shipped_model_policy); both closed at ~11:31-11:32Z after this phase合理 fix removed sase-19f(parse_queue_capacity_value); unrelated land agents to clean up

[2026-09-26T11:43:03Z · sase-19f.6.3--1] edit-capacity done: wait modal/directive/prompt-queue accept <M>x via parse_queue_capacity_value, prefill 1.5x, clear opposite form, preserve on priority/weight-only edits. Verified: 9/9 tests/test_queue_capacity_multiplier_edits.py pass plus 74 related wait/directive tests (83 total); symvision sase-19f(parse_queue_capacity_value) whitelist removed as properly used; remaining symvision red is stale entries for just-closed sase-19x.4/sase-1aa.4 recorded as follow-up

## Dependencies

- **Depends on:** [sase-19f.6.2](sase-19f.6.2.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-19f.6.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-19f.6.3.md) | [sase-19f.6.3](sase-19f.6.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2f88d1e`](https://github.com/sase-org/sase/commit/2f88d1eaa7f34ddf03a6dd016d5487452abba064) | feat(ace-tui): accept and preserve multiplier capacity in wait and directive editors | [sase-19f.6.3](sase-19f.6.3.md) | 2026-09-26 07:45:04 EDT |
