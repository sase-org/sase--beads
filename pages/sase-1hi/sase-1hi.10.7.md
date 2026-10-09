# Bead: sase-1hi.10.7 — Plan Decisions landing finish: fix the broken Verdict, tint, receipts, and the missing route coverage

[Bead Pages](../README.md) / [sase-1hi.10](sase-1hi.10.md) / sase-1hi.10.7

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1hi.10.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.10.land.md) · **Assignee:** `sase-1hi.10.7.land`
**Created:** 2026-10-08 13:17:02 EDT
**Plan:** [202610/plan\_decisions\_landing\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202610/plan_decisions_landing_finish.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/plan_decisions_landing_finish.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/plan_decisions_landing_finish.md

<!-- sase:links:end -->

## Description

Finish the work the sase-1hi.10 land audit found incomplete or broken. ACE shows every Verdict control and tints the chosen branch from the first frame. The epic-caused red tests on master pass. sase bead work reuses accepted answers without re-resolving them. Stale reviews leave a durable record that every surface can recover from. The %auto receipt reaches the ACE inbox. Shell completion scopes -D ids to the named proposal. Telegram receipts, stale recovery, and the sheet budget match the parent plan. The goldens show all of this.

## Notes

[2026-10-08T19:21:08Z · sase-1i5.9.1.2.1.3] plan-tui (sase-1i5.9.1.2.1.3) applied the missing signature-cache + short-label corrections: _cache_associated_plan_sheet now keys by plan/sibling (mtime_ns,size) incl. absent siblings and cached misses, reuses metadata tier so unchanged plans are never re-read; the two stale full-label assertions now assert short Verdict labels (Launch coder / Commit plan) with full labels in tooltips. All 8 target nodes + 946 neighbors pass.

[2026-10-08T23:12:29Z · sase-1hi.10.7.land] LAND TRIAGE of child PROPOSED FOLLOW-UPs (sase-1hi.10.7.land on master 67df4cfba5): (1) BeadBoardSnapshot unused-public from sase-1hi.10.7.1 #1, .10.7.2 #1 and .10.7.4 #3: declined as a new task. It is already routed to open epic sase-1h8 as a DISCOVERED ISSUE note naming BeadBoardSnapshot, and sase-1hi.10.land recorded it in its +1 on sase-1hp. Not caused by this epic. (2) From .10.7.3 #1, test_member_loader_reuses_reply_and_prompt_precedence: duplicate of sase-1ia. +1 recorded with a serial repro. test_agent_session_conversation_sections_are_always_full (EXPANDED, EXHAUSTIVE and override params still fail) shows the same expanded-prompt-stays-raw symptom, so it was folded into the sase-1ia +1 rather than filed separately. test_lane_following_narrates_epic_progress_and_since and test_shared_host_executor_handles_feedback_rejection_and_races now pass on master (fixed by 34829c0360 and later commits), and test_agy_usage_probe_timeout_with_rate_limit_stderr_is_rate_limited passed on rerun (a one-off flake). Declined: no longer reproducible. (3) From .10.7.4 #1, the two Agents-deck visual nodes (spread_deck_sticky, left_right_search_committed): reproduced on master and filed as new task sase-1ii (ci, large, ready). (4) Land-audit discoveries, not child proposals: agents_session_panel_two_digit_roster_120x40 passed on a focused rerun, so declined as not reproduced. sase-telegram test_integration.py failed twice under an ad-hoc -n 8 run but passes serially, and sase-telegram's own check lane is serial (phase .10.7.5 check 5288b71524b7ef03a4d9a86eac648933 green), so declined as an artifact of the ad-hoc parallel run.

[2026-10-08T23:15:17Z · sase-1hi.10.7.land] LAND AUDIT (sase-1hi.10.7.land, master 67df4cfba5, sase-telegram db624d3): the epic is not complete. gate (.10.7.1): all nine code items are on master and the focused suites pass (173), but most owed item-10 tests are missing, and the stale_review, restamp, memory-guard and receipt-inbox tests are partial or check the wrong thing. cli (.10.7.2): complete. The -S helpers and selector cache keys survive 7922974062, the snapshot is current, and 93+293 tests pass. tui (.10.7.3): items 3, 5, 6 and 7 are done, and the 67df4cfba5 test split lost no tests. Two real defects remain. (a) The chosen-branch bold green tint never renders, because Textual layers spans by start offset and token spans win; the goldens show the chosen line in plain syntax colour. (b) The closed-modal stale reopen pushes a bare PlanApprovalModal with no dismiss callback or action runner, so a submit there is dropped. Also, the unscoped .gate-review-actions width went from 42 to 44, which changed the custom_gate and sudo rails (a generic-gate regression the plan forbade). goldens (.10.7.4): plan goldens updated and inspected, but they bake in defect (a) and the generic rail regression. telegram (.10.7.5): receipt headers, stale/error recovery, feedback settlement and the three-step budget are done (770 pass). The coder launch-failure claim ignores sase's real gate-turn followup_error and misreads side_effects errors. The expandable stage puts all choices into one blockquote detached from their decisions. Keyboard, external-settle, PDF, stale-refresh and retry tests are missing. Integration: no later commit reverted epic work. 1914591ab4 makes the _gate_source/_gate_caller pops defensive only (kept for legacy bundles). Remaining work is proposed as a child epic with parent_bead sase-1hi.10.7.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1hi.10.7.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.10.7.land.md) | [sase-1hi.10.7](sase-1hi.10.7.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1hi.10.7.2][1] | Need epic DECISIONS | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1hi.10.7.2/README.md

<!-- sase:referenced-by:end -->
