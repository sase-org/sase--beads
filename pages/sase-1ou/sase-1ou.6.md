# Bead: sase-1ou.6 — Make Files spread page-anchor navigation converge on CI (finish sase-1a7)

[Bead Pages](../README.md) / [sase-1ou](README.md) / sase-1ou.6

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ou.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ou.land.md) · **Assignee:** `sase-1ou.6.land`
**Created:** 2026-10-28 17:04:15 EDT
**Plan:** [202610/files\_spread\_ci\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202610/files_spread_ci_landing.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/files_spread_ci_landing.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | file:explicit:c6f1c46fbe473d24b4235abb | attached via sase artifact create --bead |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/files_spread_ci_landing.md

<!-- sase:links:end -->

## Description

Files spread ctrl+j and cycle_card navigation always converges on the live page anchor, including on CI's Python 3.12 runner with Textual 8.2.8. The test_deck_spread_pilot ctrl+j node and every test_files_anchor_ownership node stay green in scheduled Full CI. sase-1a7 closes done, and the interrupted sase-1ou landing resumes.

## Notes

[2026-10-28T23:26:01Z · sase-1ou.6.land] LANDING AUDIT (2026-10-28, master aaa88b002679ac9b12a5cdc4244426daa469011a): Read this epic, its approved plan, child sase-1ou.6.1 and every child note, predecessor sase-1ou.4, parent sase-1ou, and task sase-1a7. Reviewed full child diff and live Files navigation/layout/scroll-watcher code. The virtual_size watcher re-arms only pending active Files-spread navigation through the existing generation-aware scheduler; hidden-view guard, superseding target ownership, mounted guard and two-confirm landing remain. All eight navigation method ASTs in the earlier f8a8b5a4f6 extraction equal their pre-split bodies. No timeout/assertion/baseline suppression changed. Independent targeted run on Python 3.14.7/Textual 8.0.1: all five test_files_anchor_ownership nodes plus Files ctrl+j pass (6 passed in 6.95s). Child check 919f89a55574e346e5c8768f7a890cc2 exits 1 solely for 9 KNOWN Symvision items, with no_new_failures and scoped tests passing; later commit 02716dcbc0 privatizes those reported symbols. Integration: fetched origin/master, equal to HEAD; audited intervening 02716dcbc0 and c33e975746 (agent/clan selection and stopped-status behavior), no Files navigation duplication or conflict. No PROPOSED FOLLOW-UP entries exist on this child; no new distinct follow-up to file. The reported loaded-run failures remain within sase-1a7 scope and must be judged by the required CI proof, not declined as unrelated. epic-symbols sase-1ou.6 lists none. DECISION ci_proof_runs=two is not yet satisfied: latest scheduled Full CI 40781527065 uses pre-fix 02716dcbc0. Leaving epic, task, phase sase-1ou.4 and plan status open while a monitor waits for two completed post-fix scheduled runs. Those are candidates only: inspect all Python jobs and actual watched-node execution before counting them as proof. Parent blocker: sase-1ou note #3 and reopened sase-1p6 record lost core/baseline landing edits; reverify before any parent close.

[2026-10-29T15:05:09Z · sase-1ou.6.land--1] CI RECURRENCE (2026-10-29): scheduled Full CI 40879308061 at b10abafcf07450a22334253569725ea2a2251396 contains fix aaa88b002679ac9b12a5cdc4244426daa469011a (git merge-base --is-ancestor exit 0), but Python 3.12 job 123474405005 fails tests/ace/tui/widgets/decks/test_files_anchor_ownership.py::test_visible_paged_restore_still_moves_viewport at its first post-cycle_card(1) wait, line 130. Exact diagnostic: anchor_wait: scroll_y=0 live_target=6 files_nav: scroll_y=0 max_scroll_y=0 pending=1 retry=8 generation=2 confirmed=False textual=8.2.8. Timeout remains 5.0s. URL: https://github.com/sase-org/sase/actions/runs/40879308061/job/123474405005 . The other candidate, scheduled 40825968742 at dd59c28f44c7e5fc83cc75188ca58b710d4f32f7, also contains the fix and lists no watched failure, but individual watched-node execution was not established and is not counted as passing proof. ci_proof_runs=two is NOT satisfied. This is existing epic/task work, not a new follow-up. Reopened sase-1ou.6.1 per the approved plan recurrence branch; sase-1a7 and sase-1ou.6 stay open. Need investigate why enabling trailing reserve leaves max_scroll_y=0, not merely wait for a virtual_size change that never arrives. Preserve assertions, 5s timeout, generation ownership, hidden-paged guard, and manual-scroll behavior; no baseline suppression. The previous loaded-loop max_scroll_y=0 failures are now reproduced in the required CI environment and cannot be dismissed as unrelated. INTEGRATION/TRIAGE: origin/master cddea47cc6 has 23 commits after the fix; none modifies the Files navigation/rendering, SectionView, anchor tests or settle helper. No PROPOSED FOLLOW-UP entry exists on the phase; no distinct follow-up to file. Continue the approved plan's explicit reopen-and-rerun branch. Parent sase-1ou note #5 now reports recovery of the previously lost core/baseline edits via sase-1ph; verify actual source/history before parent close, do not repeat the stale blocker as proven current.

[2026-10-29T15:06:04Z · sase-1ou.6.land--1] Durable CI failure evidence: file:explicit:c6f1c46fbe473d24b4235abb (candidate SHA ancestry, all Python job summaries, exact watched-node traceback and diagnostic). Use sase artifact read to consume it. The failure is in the first spread navigation wait before the visible-paged restore itself, so investigate trailing-reserve/extent publication rather than treating the test name as evidence of a paged restore defect. Source starting points: decks/_panel_spread_files_scroll.py::_cycle_files_spread and _on_files_scroll_extent; prompt_panel/_section_view.py::enable_section_layout_reserve and get_content_height; files_spread.py::_publish_section_layout. No production or tracked test files changed in this continuation.

[2026-10-29T15:09:46Z · sase-1ou.6.land--1] RERUN DISPATCHED (2026-10-29): executed the approved plan recurrence branch with sase bead work sase-1ou.6. Result: launched=true; restarted phase sase-1ou.6.1; preserved current land agent sase-1ou.6.land. Existing approved repair scope covers this recurrence, so no duplicate child plan or task was created. Added dependency on the reopened phase and will monitor its close plus a new phase commit on origin/master. After the repair, require two fresh scheduled CI runs containing that new commit and explicit execution/pass evidence for all watched nodes in every Python job; do not reuse the rejected candidate pair. Evidence file:explicit:c6f1c46fbe473d24b4235abb. No tracked source files changed.

## Dependencies

- **Depends on:** [sase-1ou.6.1](sase-1ou.6.1.md) ✓ · ⧖ 2026-10-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ou.6.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ou.6.land.md) | [sase-1ou.6](sase-1ou.6.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ou.6.1][1] | need parent epic context | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ou.6.1/README.md

<!-- sase:referenced-by:end -->
