# Bead: sase-1hi.10.7.6.1 — Rendered chosen-branch tint, stale reopen through the real open path, and generic rails back to 42

[Bead Pages](../README.md) / [sase-1hi.10.7.6](sase-1hi.10.7.6.md) / sase-1hi.10.7.6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1hi.10.7.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.10.7.land.md) · **Assignee:** `sase-1hi.10.7.6.1` · **Size:** medium
**Created:** 2026-10-08 19:15:59 EDT · **Closed:** 2026-10-09 00:36:44 EDT
**Plan:** [202610/plan\_decisions\_finish\_gaps.md](https://github.com/sase-org/sase--plans/blob/main/202610/plan_decisions_finish_gaps.md)

## Description

ace: make the chosen-branch green/bold tint survive Textual rendering and test it on rendered output, reopen a closed stale review through handle_plan_approval so its submit is handled, load the stale bundle off the UI thread, and scope the rail width change so generic gates and decision-free plans return to 42 cells.

## Notes

[2026-10-09T04:36:44Z · sase-1hi.10.7.6.1--2] ace done. (1) Chosen-branch tint split at token boundaries so it layers after each token in Textual Content.render; new rendered-output assertions in test_first_frame_tint_keeps_syntax (chosen header green+bold, unchosen dim, frontmatter token keeps theme colour, not green/bold). (2) Closed stale reopen now goes through handle_plan_approval with _loaded, restoring esc_drafts by decision id (vanished ids dropped, new ids default); bundle reload moved off pump via spawn_pump_free_task+asyncio.to_thread with sync fallback; new test_stale_closed_reopen_submits_through_real_open_path proves submit reaches plan response path with restored decision values and new revision, and proves load runs off the pump thread. (3) Generic .gate-review-actions rail restored to 42; decision-free plan rails keep 44 via PlanApprovalModal-scoped rule; decisions rail 50; new test_generic_gate_rail_stays_42_with_stylesheet plus widened test_compact_verdict_stays_inside_rail_with_stylesheet. Verified: targeted pytest tests/ace/tui/test_plan_decision_ace_render.py + test_plan_decision_ace_stale.py: 8 passed. ruff check + format clean on all 4 touched files. Keypress cost: tinted_document_text avg 6.69ms/call on 200-line doc (cached spans, no re-lex/parse/stat per call). just check / sase tool run check timed out twice at the 1h budget inside rust-install rebuilding sase_core_rs (maturin compiling the full dep tree after the linked sase-core checkout fast-forwarded past the built extension); this phase touches no sase-core code and the build never reached the test lane, so recorded as environmental, not a phase failure. sase bead epic-symbols is empty.

## Dependencies

- **Blocks:** [sase-1hi.10.7.6.2](sase-1hi.10.7.6.2.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1hi.10.7.6.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.10.7.6.1.md) | [sase-1hi.10.7.6.1](sase-1hi.10.7.6.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1820636`](https://github.com/sase-org/sase/commit/1820636212abb2a056f7892ead0c42ea7cb5e09e) | feat(ace): rendered chosen-branch tint, stale reopen via real open path, 42-cell generic rails | [sase-1hi.10.7.6.1](sase-1hi.10.7.6.1.md) | 2026-10-09 00:42:16 EDT |
