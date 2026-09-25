# Bead: sase-17m.5.1.6.5 — Repair the retry agent-session visual case

[Bead Pages](../README.md) / [sase-17m.5.1.6](sase-17m.5.1.6.md) / sase-17m.5.1.6.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.5.1.6.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.5.1.6.land.md) · **Assignee:** `sase-17m.5.1.6.5.land`
**Created:** 2026-09-25 10:02:05 EDT · **Closed:** 2026-09-25 12:16:04 EDT
**Plan:** [202609/retry\_session\_visual\_gap.md](https://github.com/sase-org/sase--plans/blob/main/202609/retry_session_visual_gap.md)

## Description

The retry countdown visual test and golden use the renamed agent session and pass verification.

## Notes

[2026-09-25T16:16:04Z · sase-17m.5.1.6.5.land] Verified epic sase-17m.5.1.6.5 is complete.

Child sase-17m.5.1.6.5.1 (retry-visual) is closed done. Source and commit ced0b15e0 match the close note: test_real_loader_plan_agent_session_retry_countdown_png_snapshot queries "retry-session"; the fixture already names retry-session; git grep finds no retry-family; only agents_retry_e2e_plan_session_countdown_120x40.png changed; inspected golden shows retry-session in the list row, SESSION header, and 2 shells. Unrelated retry goldens (fakey countdown/fallback/chain) were not touched.

Integration: HEAD is that stitch. Concurrent ACE TUI commits since epic start (waiting-chip 8e82089e8, deck picker ce1336eec, note-preview wrap 204a4993e) are ancestors of the golden regen, so this snapshot already includes them. Nothing else should now consume retry-session; no duplicate or conflict remains.

FOLLOW-UP OUTCOMES (from 5.1.6.5.1 #1, not caused by this epic — load-flaky, pass in isolation):
- test_weight_two_land_agent_session_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap: corroboration on existing sase-12f (+1); node was renamed from *family* by the cutover.
- test_inline_caller_group_sigkill_leaves_no_survivors: new ready flake task sase-19c (related sase-16b, retired umbrella sase-ct).
- test_sudo_local_flow_never_persists_canary_credentials: new ready flake task sase-19d (related sase-ct, sase-15h).
sase bead epic-symbols reported no --epic-symbol entries.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.5.1.6.5.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.5.1.6.5.land.md) | [sase-17m.5.1.6.5](sase-17m.5.1.6.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@1691f9f`](https://github.com/sase-org/sase--plans/commit/1691f9f71092042f2118b8e1593e6b1d525e0c61) | docs(plans): mark ACE agent-session cutover plans done (sase-17m.5.1) | [sase-17m.5.1.6.5](sase-17m.5.1.6.5.md) | 2026-09-25 13:35:05 EDT |
