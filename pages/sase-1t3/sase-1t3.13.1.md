# Bead: sase-1t3.13.1 — Finish measured Agents interaction latency recovery

[Bead Pages](../README.md) / [sase-1t3.13](sase-1t3.13.md) / sase-1t3.13.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t3.13](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.13.md) · **Assignee:** `sase-1t3.13.1.land`
**Created:** 2026-11-18 15:37:13 EST · **Closed:** 2026-11-18 19:57:57 EST
**Plan:** [202611/interaction\_latency.md](https://github.com/sase-org/sase--plans/blob/main/202611/interaction_latency.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/interaction_latency.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | [bead:sase-1tt][2] | Epic whose land agent found the share-back defects and is fixing them in a remediation tale; that tale changes the same _loading_graph share-back code |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/interaction_latency.md
[2]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1tt/README.md

<!-- sase:links:end -->

## Description

Make selection, detail enrichment, and small roster updates responsive without rebuilding or retaining unrelated agent data.

## Notes

[2026-11-18T23:45:24Z · sase-1t3.13.1.land] LAND TRIAGE of child PROPOSED FOLLOW-UPs (sase-1t3.13.1.land, 2026-11-18):
(1) .1: clan-fold bench stall-log gate counts the prompt_activity initial row. Duplicate of sase-1gf; +1 recorded with 6/6 reproductions at 5b08952c6d, af07b78ac2, and 789e5d0fc5, plus the diagnosis.
(2) .2/.3: tests/test_agent_compact_workflow_loaders.py::test_failed_parent_and_step_parity. DECLINED. It no longer reproduces: it passes alone and in the whole file on HEAD 789e5d0fc5 and on pre-epic af07b78ac2, with sase_core_rs 0.44.2. The likely cause was a stale core build in the phase workspaces at the time.
(3) .3: test_blocked_render_with_young_index_lock_is_bounded load-sensitive overrun. Duplicate of sase-xo, which already tracks this node; +1 recorded.
(4) .5: selected-tribe fold level 1 p95 above its 40 ms budget. Duplicate of sase-lx; +1 recorded with A/B evidence that it is pre-existing and unchanged by this epic.
(5) .5: ordinary Agents j/k p95 above 16 ms. DECLINED as a new task. The A/B is unchanged: next p95 is 24-36 ms on af07b78ac2, 19-33 ms on HEAD, and 34-50 ms on the baseline commit 5b08952c6d itself. The baseline note's 9.71 ms is not reproducible on the same commit, so this is neither a regression nor epic-caused. The node has no budget assertion; the numbers are recorded as context on sase-lx.
(6) .5: exact-delta transient copies still scale with the full roster. Pre-existing; the epic shrank it from deep to shallow copies but missed the closure target. New task sase-1tt (bug, large) created and linked.
(7) .5: Textual ZeroDivisionError in the trace run. EPIC-CAUSED. f81ff92e05 schedules the bead-warmup follow-up with set_timer(0.0), which raises in textual/timer.py:163 and never fires (reproduced with a minimal Textual app). Kept as epic work in the remediation tale.

[2026-11-18T23:48:05Z · sase-1t3.13.1.land] LAND REVIEW: remaining epic-caused work found (sase-1t3.13.1.land). Probes used normalized make_agent rosters with 2- and 8-row deltas.
(a) 10922458c1: share_back_boundary_fast runs on the event loop after the last await in _loading_disk_delta. It fingerprints all 317 Agent fields for every worked and live row, once per published list, with no cross-list memo. That is about 250 ms at 165 rows and about 1.0 s at 660 rows of event-loop time per exact artifact delta (cProfile: 1,980 fingerprint calls at 165 rows).
(b) 10922458c1: the published graph is alias-inconsistent. A retained clan container's runtime_children and status_display_source point at worked copies of members that were shared back as live objects, so those copies are orphans in no published roster (reproduced with clan_graph and a 4-member clan). Shared live rows can also keep references to replaced rows.
(c) f81ff92e05: the warmup follow-up uses set_timer(0.0), which raises ZeroDivisionError and drops the follow-up.
Not epic-caused: A/B j/k bench runs show the same numbers at 5b08952c6d, af07b78ac2, and HEAD 789e5d0fc5. Selection-phase header worker, viewport runtime patching, and surfaced-row warmup bounds were reviewed and look correct. Integration with concurrent af07b78ac2 (compact projected-record copies) is honored through prepare_projected_agent_copy. Remediation is planned as a medium tale whose final step closes this epic and parent phase sase-1t3.13.

[2026-11-19T00:57:43Z · sase-1t3.13.1.land] LAND CLOSEOUT — Agents interaction latency — 2026-11-18

All five phases were reviewed and remain closed.

Fixes:
- Moved exact-delta boundary finalization and closure-consistent share-back into the existing worker step. One identity memo is shared across boundary lists, owned rows relink Agent references to the decided published objects, and the unused public fingerprint helper was removed. Changed: src/sase/ace/tui/actions/agents/_loading_disk_delta.py, src/sase/ace/tui/actions/agents/_loading_graph.py, src/sase/ace/tui/models/_agent_graph.py.
- Set the bead-warmup follow-up timer floor to 50 ms so a pending warmup request is not dropped. Changed: src/sase/ace/tui/actions/agents/_loading_bead_warmup.py.
- Added closure, stale-reference, worker-thread, unchanged-row, capacity, fleet, named-proc, exception, and follow-up-scan regressions. Changed: tests/test_agents_tab_delta_copy_fast_path.py and tests/ace/tui/test_agents_bead_warmup.py.

Share-back measurements, using normalized 165/660-row rosters and 2/8-row deltas:
- Before: about 250 ms / 1,000 ms on the event loop per exact delta at 165 / 660 rows; 1,980 fingerprint calls at 165 rows.
- After worker prep / share-back / post-await scalar bookkeeping ms: 165 rows, 2 deltas: 45.77 / 7.40 / 0.77; 165 rows, 8 deltas: 47.79 / 7.33 / 0.65; 660 rows, 2 deltas: 196.61 / 34.10 / 2.12; 660 rows, 8 deltas: 206.05 / 37.34 / 2.25. The post-await measurement is scalar bookkeeping only, not the full apply span. Share-back is about 15–18% of worker prep.

Verification:
- Focused combined suite: 254 passed in 9.51s.
- just fmt passed.
- just symvision passed: all public/private classes and functions are used properly.
- Required check ToolRun 5e0a93f77c4e2b8dc8d6c2d347b0980f ran 62,055 passed, 17 skipped, 1 failed. The unrelated axe node tests/axe/test_axe_chop_batch_recovery.py::test_older_generation_does_not_cancel_a_batch_without_recorded_generation reproduced unchanged in ToolRun fa3de9e517308a662305410923ea6724 and was +1 corroborated on sase-1tm and noted on active chop-recovery epic sase-1tc.3.1. The check also reports the already-recorded mypy issue at src/sase/axe/_chop_batch_recovery_observations.py:85, documented in sase-1tc.3.1 note 4. Neither failure is in the changed ACE latency paths.
- No new public symbols remain on this epic; epic-symbol lists were empty.

Existing follow-up triage remains as recorded here: +1 on sase-1gf, sase-lx, and sase-xo; sase-1tt tracks transient full-roster shallow copies; two proposals were declined. No memory files were changed.

[2026-11-19T00:57:57Z · sase-1t3.13.1.land] Verified all phases .1-.5, moved exact-delta share-back off the event loop and made published graphs closure-consistent, fixed the zero-interval bead-warmup timer, and recorded 165/660-row measurements and verification in the epic note. just fmt and just symvision passed; focused integration suite passed 254 tests. Required check ToolRun 5e0a93f77c4e2b8dc8d6c2d347b0980f reported one unrelated axe cancellation test failure (reproduced unchanged, corroborated on sase-1tm and noted on active epic sase-1tc.3.1) and the previously recorded mypy failure in sase-1tc.3.1 note 4. Follow-up triage remains recorded: sase-1gf/sase-lx/sase-xo +1, sase-1tt created, two proposals declined.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.13.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.13.1.land.md) | [sase-1t3.13.1](sase-1t3.13.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d152f20`](https://github.com/sase-org/sase/commit/d152f200b294deabb84cac52b2e5d606a2017837) | fix(ace): move exact-delta share-back off the UI loop | [sase-1t3.13.1](sase-1t3.13.1.md) | 2026-11-18 20:01:38 EST |
| sase--plans | [`sase--plans@78bbde9`](https://github.com/sase-org/sase--plans/commit/78bbde9fbc8c59aac936c37fa488ca0883b6e35b) | docs(plan): mark interaction latency landing complete | [sase-1t3.13.1](sase-1t3.13.1.md) | 2026-11-18 20:03:24 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1t3.13.1.2][1] | Need parent epic decisions and parent phase context for the assigned child phase | 1 |
| read-by | [agent:sase-1t3.13.1.3--1][2] | Need parent epic decisions governing this phase | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.13.1.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.13.1.3.md

<!-- sase:referenced-by:end -->
