# Bead: sase-1io.7.6 — Clear the last Full CI reds and ship sase v0.18.0

[Bead Pages](../README.md) / [sase-1io.7](sase-1io.7.md) / sase-1io.7.6

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1io.7.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1io.7.land.md) · **Assignee:** `sase-1io.7.6.land`
**Created:** 2026-10-09 14:56:41 EDT
**Plan:** [202610/ship\_v0\_18\_0\_after\_full\_ci\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/ship_v0_18_0_after_full_ci_fixes.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/ship_v0_18_0_after_full_ci_fixes.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/ship_v0_18_0_after_full_ci_fixes.md

<!-- sase:links:end -->

## Description

Full CI is green on a sase master tip that also has a green Master Gate, release PR 299 merges, and `pip install sase==0.18.0` works from PyPI, so the interrupted landing of epic sase-1io.7 can close.

## Notes

[2026-10-09T21:37:01Z · sase-1io.7.6.land] LAND TRIAGE (sase-1io.7.6.land, 2026-10-09). Code phases verified on origin/master tip 7c6039f1e6. ready_gate=known_miss is in the Justfile --gate-allow list and the perf runbook states the measured miss (not the 1.03 pass); sase-1j5 note #1 records that. Reply-card fix is _apply_ready_deck_card plus preferred-card over anchor, with show_reply_card (one press) and test_cycle_focused_deck_card_applies_when_view_lags. reconcile_prompt_with_live_auto_state is public; no private import remains. No --epic-symbol entries. Intervening commits c836ee5071, 6dd92ea0e3, 735eac764b, and 555405701d do not duplicate or conflict; 6dd92ea0e3 only added an sase-1j6 epic-symbol in the Justfile and bootstrap boot identity, and the later public rename still compiles against it. Release not shipped yet: PyPI sase 0.17.1, PR 299 still based on 73c128074d. Dispatched Full CI 37993930903 and publish.yml 37993934298 on 7c6039f1e6.

FOLLOW-UPS: 7.6.1#1 tail-ghost -> +1 on sase-1ib (new local parallel-lane failure; not a new bead; passes on a clean base, not caused by this epic). 7.6.2#1 symvision private import -> declined, fixed by 7c6039f1e6; Master Gate lint on 37992380866 succeeded. 7.6.2#2 select_main_card retry migration and 7.6.2#3 tighten test_main_ctrl_j_in_spread -> declined as new tasks. Both are non-failing test cleanups (feature type, not agent-creatable) and are not defects this epic caused; the CI-red snapshot callers already use show_reply_card. 7.6.2#4 handoff database-is-locked -> +1 on sase-18t. 7.6.2#4 test_fast_success_matches_inline exit 124 -> new large flake sase-1j9 (ready), related to sase-18t; passes in isolation on a clean base, not caused by this epic. Master Gate 37992380866 failed only tests/ace/tui/test_plugins_browser_pane_cached_open.py::test_mutation_completion_after_unmount_invalidates_memo (3 catalog calls vs 2) in shard test (7). 7/7 isolation passes on this tip; no commit since green MG 37972110667 touches that test. Filed large flake sase-1ja and used the one allowed failed-job rerun. Not caused by this epic.

[2026-10-09T23:05:17Z · sase-1io.7.6.land--1] RELEASE NOT SHIPPED (sase-1io.7.6 land, 2026-10-09, after monitor 8k7qzg6tkecd). Tip 7c6039f1e6. PyPI sase is still not 0.18.0. PR 299 stayed OPEN, MERGEABLE, title chore(master): release 0.18.0, base 7c6039f1e6, head 1eb1fbf9a52fc9f545daabe41352bc48d6901704. Do not merge it while Master Gate or Full CI is red.

Runs waited by /tmp/sase-1io-ci-wait.sh:
- Master Gate failed-job rerun 37992380866: failure. Same sase-1ja node, tests/ace/tui/test_plugins_browser_pane_cached_open.py::test_mutation_completion_after_unmount_invalidates_memo, assert 3 == 2. That was the one allowed retry. Do not rerun it. Fix _handle_code_update_completion: after pop_screen, is_mounted can still be true under shard load and the no-change path calls _start_load.
- Full CI 37993930903: failure. perf-floors succeeded (ratio:ready known miss owned by sase-1j5 did not fail the job). full / test (3.12) and full / test (3.13) succeeded. full / test (3.14) job 114039268827 failed once on tests/llm_provider/test_subprocess_utf8_decode.py::test_stream_json_lines_dispatches_stderr_during_a_large_stdout_burst (assert 1200 < 1200). That is existing flake sase-1ht; this land recorded a +1. Not caused by this epic. A later ship may retry that job once, not twice, and must not edit the test to get green.
- full / visual-test job 114039268743 timed out after 15s in tests/ace/tui/visual/test_ace_png_snapshots_agents_decks.py::test_agents_decks_single_main_paged_png_snapshot waiting for card_ids == {context, reply} and RenderMode.PAGED. The same node failed Full CI 37947270619 before phase sase-1io.7.6.2. That phase fixed ctrl+j drops and this snapshot does not press ctrl+j, so the paged-threshold wait is still red. This is remaining epic work, not a new task bead. Do not raise the timeout.
- publish.yml 37993934298: success (publish_existing=false regenerated PR 299). Re-dispatch publish.yml and full.yml on the tip that contains the fix. Re-dispatch commands for the next ship: gh workflow run full.yml --repo sase-org/sase and gh workflow run publish.yml --repo sase-org/sase -f publish_existing=false.

TRIAGE THIS TURN (do not recreate these beads):
- sase-1ja: retry failed; child epic will fix the root cause. Supplementary note on sase-1ja, no second bead, no +1 (this land filed it).
- visual paged snapshot: declined as a new task. It is the Full CI red phase sase-1io.7.6.2 did not clear, so the child epic's fix phase owns it.
- sase-1ht: +1 for the 3.14 stderr-burst failure on run 37993930903. Declined as epic code work.
- Prior LAND TRIAGE note stands: sase-1ib +1 tail-ghost; symvision private import declined because 7c6039f1e6 fixed it; select_main_card retry migration and the spread-assertion tighten declined as non-failing feature cleanups agents cannot file; sase-18t +1 database-is-locked handoff; sase-1j9 soft-ceiling exit 124; sase-1ja extra catalog load.

Close note, when a later land actually closes this epic after v0.18.0 is on PyPI, must include those triage outcomes. sase bead epic-symbols sase-1io.7.6 was empty at this check. Do not use --force.

[2026-10-10T13:25:03Z · sase-1io.7.6.land] LAND VERIFICATION (sase-1io.7.6 land, 2026-10-10). Epic code is on origin/master tip 35a97a0e1e and still matches the DECISIONS. Release is not shipped. PyPI sase is 0.17.1; sase-core-rs is 0.37.2. PR 299 is OPEN, MERGEABLE, UNSTABLE, title chore(master): release 0.18.0, head 146ac48cf4. release-core-floor-smoke on run 38043045593 failed because sase-core-rs 0.37.2 is missing 7 bindings master now imports: advance_auto_restart_ledger, agent_auto_restart_wire_schema_version, auto_restart_lineage_root, auto_restart_recovery_is_in_flight, claim_auto_restart_ledger, classify_agent_failure, derive_auto_restart_episode. Those bindings belong to in-progress epic sase-1j6.10. Do not cut a core release from this epic.

Verified on the tree:
- ready_gate=known_miss: Justfile bead-perf-scale-gate still passes ratio:ready in --gate-allow. docs/perf_runbook.md states the measured miss and calls the old 1.03 pass load noise. Full CI 38029274494 perf-floors succeeded.
- Reply-card: a36b5c90ca is on master. show_reply_card is one press after the cycle-ready wait. _apply_ready_deck_card and test_cycle_focused_deck_card_applies_when_view_lags are still present. CI-red snapshot callers use show_reply_card.
- reconcile_prompt_with_live_auto_state is public in run_agent_runner_refresh.py. bootstrap.py and the tests import that public name. No _reconcile_prompt_with_live_auto_state import remains.
- sase bead epic-symbols sase-1io.7.6 is empty.
- Integration: commits after fb1186a229, excluding this epic's three commits (fb1186a229, a36b5c90ca, 7c6039f1e6), do not revert those fixes. Later auto-restart, flag-retirement, and agents-query commits do not duplicate them. They do make current master unrealeasable for reasons this epic did not cause.

CI evidence, not this epic's commits:
- Full CI 38029274494 at e770955a46 failed. perf-floors succeeded. lint failed rule 7: closed flag bead sase-s7 still has typed_launch_units (owned by in-progress sase-1jc, phase sase-1jc.12). visual-test failed on unrelated golden create/update (word-definition, mini-macro, timeband, agents_final_*, and others). test legs failed on auto-restart, completion-snapshot, help text, config schema, marker audits, and similar nodes. test_agents_decks_single_main_paged_png_snapshot was not in that visual failure list.
- Master Gate 38053026930 at 9b7fb99ef7 failed lint on unused public ArtifactIndexProjection (sase-1jc.6 already proposed that follow-up) and failed tests including autonomy flag shape, node-finder import, contract manifest, terminate processes, marker audits, and test_collect_journal_updates_bundle_window. The sase-1ja node did not fail that run. Shard test (8) passed its tests and then failed the temp-leak guard.
- Full CI 38052645920 and Master Gate 38054544472 were still running at this check. Do not treat them as proof.

FOLLOW-UP OUTCOMES (do not re-file):
- 7.6.1#1 tail-ghost: already +1 on sase-1ib. Declined as a new bead. Not caused by this epic.
- 7.6.2#1 symvision private import: declined. Fixed by 7c6039f1e6 and still public at this tip.
- 7.6.2#2 select_main_card retry migration: declined. Non-failing cleanup. Gate and monitor callers still use it; the CI-red snapshot callers use show_reply_card. Not agent-creatable feature work.
- 7.6.2#3 tighten test_main_ctrl_j_in_spread: declined. Non-failing cleanup, not a defect this epic caused.
- 7.6.2#4 database-is-locked handoff: already +1 on sase-18t. Declined as a new bead.
- 7.6.2#4 test_fast_success_matches_inline exit 124: already filed as sase-1j9. Declined as a new bead. Not caused by this epic.
- sase-1ht stderr-burst: already +1 from the prior land on Full CI 37993930903. Declined as epic code work.
- Paged snapshot timeout from Full CI 37993930903: declined as a new task and declined as a new fix phase. It did not reappear in Full CI 38029274494's visual failure list. A later ship run that reproduces it owns the fix then. Do not raise the timeout.
- sase-1ja: kept as this epic's remaining code fix, not a second bead. Master Gate 37992380866 failed it twice (assert 3 == 2) on the no-change path in _handle_code_update_completion. The suspected is_mounted-after-pop path is still in plugins_browser_sase_update_procs.py. The child plan's mount-race phase fixes that root cause and notes sase-1ja. Do not file a duplicate.

Child epic proposed for the remaining work only: fix that mount race, then ship v0.18.0 once sase-1j6.10 and sase-1jc have closed and the gates are green. This epic does not absorb their in-flight edits and does not cut another sase-core-rs release. Do not use --force.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1io.7.6.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1io.7.6.land.md) | [sase-1io.7.6](sase-1io.7.6.md) | 0 |
