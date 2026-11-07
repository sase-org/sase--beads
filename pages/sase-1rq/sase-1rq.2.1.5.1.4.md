# Bead: sase-1rq.2.1.5.1.4 — Integrate the repairs and prove Full CI green

[Bead Pages](../README.md) / [sase-1rq.2.1.5.1](sase-1rq.2.1.5.1.md) / sase-1rq.2.1.5.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.2.1.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.1.5.md) · **Assignee:** `sase-1rq.2.1.5.1.4` · **Size:** medium
**Created:** 2026-11-07 11:09:42 EST · **Closed:** 2026-11-07 18:04:59 EST
**Plan:** [202611/full\_ci\_remaining\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202611/full_ci_remaining_repairs.md)

## Description

verify-full-ci: confirm all child fixes and sase-1r2.6's bulk golden repair landed, reuse or dispatch one qualifying Full CI run, monitor it across turns, repair remaining in-scope reds, and publish exact first-attempt job evidence for the land agent. Never close the parent phase from this worker.

## Notes

[2026-11-07T21:06:06Z · sase-1rq.2.1.5.1.4] INTEGRATION (turn 1): ancestry verified on origin/master — files-reserve da1561407a, reply-preservation 92fc89d83f, visual-fixtures 960646e8ce (all ancestors of 5922991bcf and 618dbb5fcf). sase-1r2.6 bulk repair 48d0c3ea was NOT on master (only in a stale workspace + bundle); TAKEN OVER per the plan stale-owner rule (note on sase-1r2.6) and landing via this turn host completion (keep). Combined-tree verification (5922991bcf + 48d0c3ea): focused Files/Main regressions 14 passed (test_files_anchor_ownership, test_main_deck_reply_steal_recovery, test_main_deck_redelivery_hold); the three visual selectors (stranded resolve modal, beads empty, renamed generic session root) check clean twice (normal + TZ=UTC, unchanged=3, no unstable); full `sase tool run test-visual` 23c36bb7 check clean 1148 unchanged/0 updated with 2 nodes passing on built-in recapture; `sase tool run check` ec3202ee succeeded. Reference run 42391485032 (5692321a2e, pre-fix) test(3.12) red node test_chooser_arms_enter_after_recovery_panel_opens is already fixed on master by 578a317bcf (30s arm window + aged mount stamp). No qualifying Full CI run exists yet; a staged WATCHING CI monitor waits for the landing, dispatches full.yml once (reusing any non-cancelled run containing the fix instead), and watches it.

[2026-11-07T21:06:11Z · sase-1rq.2.1.5.1.4] PROPOSED FOLLOW-UP: flaky tests/ace/tui/visual/test_ace_png_snapshots_agents_archive_actions.py::test_archive_restored_row_with_toast_png_snapshot — failed first pass in full `sase tool run test-visual` 23c36bb7 (assert "is back in the inbox" after the j/settle/stabilize sequence: the restore toast was gone by the final assertion under load) and passed on recapture; the test also monkeypatches _load_archive_bundle with a SimpleNamespace agent lacking .status, so the archive-reader-hydrate pump task raises AttributeError in update_display during the test. No bead matches the node.

[2026-11-07T21:06:17Z · sase-1rq.2.1.5.1.4] PROPOSED FOLLOW-UP: corroborating evidence for sase-1l5 (no new task) — tests/pager/visual/test_time_band_png_snapshots.py::test_time_band_png_snapshot[past-True-size1] failed first pass and passed on recapture in full `sase tool run test-visual` 23c36bb7 on the combined tree (5922991bcf + 48d0c3ea), same time-band family as the tracked [cause-False-size1] drift.

[2026-11-07T23:04:32Z · sase-1rq.2.1.5.1.4--1] PROPOSED FOLLOW-UP: flaky tests/ace/tui/visual/test_ace_png_snapshots_agents_agent_session_panel_gate.py::test_agent_session_gate_turns_narrow_png_snapshot — in Full CI 42414511192 (attempt 1, dd5567e580) visual-test first pass timed out after 15s at wait_for_svg_contains(page, 'jump') (line 132, the footer wait added by the landed sase-1r2.6 repair); the timeout frame's footer still showed the agent-row hints (<enter> choose action, Ctrl+J/Ctrl+K cards) and no reply-card '-K jump' hint, so select_navigable_main_card(page, 'reply') returned without focus actually landing (or a later refresh reset it) under 3-worker load; passed on built-in recapture in 4.59s. The wait now fails loudly instead of capturing a stale footer, but the root cause is the unconfirmed card focus — select_navigable_main_card should wait for focus confirmation (e.g. focused-card state) before returning. No bead tracks this node.

[2026-11-07T23:04:39Z · sase-1rq.2.1.5.1.4--1] PROPOSED FOLLOW-UP: corroborating evidence for sase-1f9 (pager history PNG goldens intermittently render wrong) — tests/pager/visual/test_history_png_snapshots.py::test_history_png_snapshot[past-frame-False-size1] mismatched on Full CI 42414511192 visual-test first pass (dd5567e580): the '1 newer' header label rendered ~4 columns further right than the golden (layout/width-settle race, not missing chrome); passed on built-in recapture. Evidence: artifact ace-visual-first-attempt-diffs (13592820408) of run 42414511192.

[2026-11-07T23:04:59Z · sase-1rq.2.1.5.1.4--1] VERIFIED GREEN: Full CI full.yml run 42414511192 (https://github.com/sase-org/sase/actions/runs/42414511192), event workflow_dispatch, GitHub attempt 1, head dd5567e5801095c709f7145dd7d6cdfe2a7d8673, conclusion success at 2026-11-07T22:55:11Z. git merge-base --is-ancestor confirms the head contains da1561407a (Files reserve), 92fc89d83f (Reply preservation), 960646e8ce (stranded modal/empty Beads) and FIX_SHA dd5567e580 (taken-over sase-1r2.6 109-golden AGENT PROMPT repair + capacity hostname pin). Jobs (names validated against .github/workflows/ci.yml): prepare, build-core, lint, perf-floors, test (3.12), test (3.13), test (3.14), visual-test, ace-page-group-isolation, tutorial-tests all success; docs-build and release-core-floor-smoke skipped as designed. visual-test: created=0 updated=0 unchanged=1148 stale=0, with 2 nodes passing on built-in recapture (separate from the GitHub attempt, which stayed 1): test_agent_session_gate_turns_narrow_png_snapshot (footer 'jump' wait timed out, reply focus not landed) and pager test_history_png_snapshot[past-frame-False-size1] ('1 newer' label offset); both recorded as PROPOSED FOLLOW-UP. quarantined=[]. ci_evidence published via sase var on agent sase-1rq.2.1.5.1.4--1. Scheduled run 42418116452 on the same SHA was in_progress at close. No epic symbols. Reproduce: gh run list --repo sase-org/sase --workflow full.yml --branch master -L 5

## Dependencies

- **Depends on:** [sase-1rq.2.1.5.1.1](sase-1rq.2.1.5.1.1.md) ✓ · ⧖ 2026-11-07
- **Depends on:** [sase-1rq.2.1.5.1.2](sase-1rq.2.1.5.1.2.md) ✓ · ⧖ 2026-11-07
- **Depends on:** [sase-1rq.2.1.5.1.3](sase-1rq.2.1.5.1.3.md) ✓ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.2.1.5.1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.1.5.1.4.md) | [sase-1rq.2.1.5.1.4](sase-1rq.2.1.5.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`dd5567e`](https://github.com/sase-org/sase/commit/dd5567e5801095c709f7145dd7d6cdfe2a7d8673) | fix(ci): land the AGENT PROMPT golden repair and capacity hostname pin | [sase-1rq.2.1.5.1.4](sase-1rq.2.1.5.1.4.md) | 2026-11-07 16:07:57 EST |
