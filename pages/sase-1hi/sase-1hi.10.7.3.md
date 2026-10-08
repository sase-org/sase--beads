# Bead: sase-1hi.10.7.3 — ACE Verdict that fits the rail, first-frame tint with syntax kept, cheap settle polling, real stale reload, and the epic-caused red tests

[Bead Pages](../README.md) / [sase-1hi.10.7](sase-1hi.10.7.md) / sase-1hi.10.7.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1hi.10.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.10.land.md) · **Assignee:** `sase-1hi.10.7.3` · **Size:** large
**Created:** 2026-10-08 13:17:05 EDT · **Closed:** 2026-10-08 15:46:57 EDT
**Plan:** [202610/plan\_decisions\_landing\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202610/plan_decisions_landing_finish.md)

## Description

tui: scope Verdict CSS so all five tale controls and every epic control sit inside the rail, keep Decisions visible at 90 columns, tint on first display while keeping syntax colours, poll only the open modal's bundle, reopen or rebuild on stale_review with values kept, fix the four tests the first pass broke, and clean up dead caches.

## Notes

[2026-10-08T19:46:41Z · sase-1hi.10.7.3--3] PROPOSED FOLLOW-UP: check run 23abb36ce6e29b59d62bbdc1b394b232 flagged 8 NEW; 3 match plan KNOWN (snippet cpu budget sase-1g3, hinted raw prompt sase-1hy/sase-1i9/sase-1ia, foreign race exempt sase-1hs). The other 5 reproduce on clean base via stash (master without this phase): test_agent_session_conversation_sections_are_always_full, test_member_loader_reuses_reply_and_prompt_precedence, test_lane_following_narrates_epic_progress_and_since, test_shared_host_executor_handles_feedback_rejection_and_races; plus test_agy_usage_probe_timeout_with_rate_limit_stderr_is_rate_limited which passed on isolated rerun (flaky). Pre-existing, not this phase.

[2026-10-08T19:46:57Z · sase-1hi.10.7.3--3] Sec1 rail containment: #plan-verdict-scoped CSS keeps all Verdict controls inside rail at 120x40 and 90x40, short toggle labels with full text on tooltip — test_compact_verdict_stays_inside_rail_with_stylesheet. Sec2 first-frame tint: span-cache ensure in compose+on_mount, tint overlays token styles via Text.stylize, dead _chosen block removed, draft edits skip validate/recache/relex — test_first_frame_tint_keeps_syntax + test_draft_edit_avoids_revalidate_relex. Sec3 settled polling reads only the open modal's bundle with mtime-signature cache — test_settled_polling_reads_only_open_modal. Sec4 stale_review real reload: closed pushes new modal with merged esc_drafts, open rebuilds rows/fold/spans in place — test_stale_review_reloads_revision_keeping_values (closed+open). Sec5 short-label fixes (test_plan_modal_bundle_loading_stays_off_the_message_pump, test_group_submit_uses_current_branch_selection) + signature-keyed sheet cache with sibling reload — test_sibling_mtime_change_reloads_sheet. Sec6 freeze clear path extended in test_freeze_banner_visible_and_submit_blocked. Sec7 cleanups: _PLAN_SHEET_CACHE deleted, __all__ trimmed, tmp_path threaded in test_plan_decision_ace. Check 23abb36ce6e29b59d62bbdc1b394b232: 75 KNOWN (incl. plan-listed sase-1hr/sase-1hy/sase-1i9/sase-1ia/sase-1ic/sase-1g3/sase-1hs/sase-1hp backlog); 8 triaged NEW all pre-existing — 3 match plan KNOWN, 5 reproduced on clean base via stash (see PROPOSED FOLLOW-UP note), agy probe flaky-passed on rerun. All 14 phase covering tests pass; mypy clean on touched file. epic-symbols empty. Ancestors untouched.

## Dependencies

- **Blocks:** [sase-1hi.10.7.4](sase-1hi.10.7.4.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1hi.10.7.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.10.7.3.md) | [sase-1hi.10.7.3](sase-1hi.10.7.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b49f9bc`](https://github.com/sase-org/sase/commit/b49f9bcb2818eb89eaa282ac59ef1cf7567ef71c) | feat(ace): verdict rail fit, first-frame tint, cheap settle polling, real stale reload (sase-1hi.10.7.3) | [sase-1hi.10.7.3](sase-1hi.10.7.3.md) | 2026-10-08 15:48:34 EDT |
