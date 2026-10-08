# Bead: sase-1hi.3 — Compile, resolve, freeze, and stamp decisions in the plan gate

[Bead Pages](../README.md) / [sase-1hi](README.md) / sase-1hi.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.5n](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.5n.md) · **Assignee:** `sase-1hi.3` · **Size:** large
**Created:** 2026-10-07 18:48:25 EDT · **Closed:** 2026-10-08 00:15:35 EDT
**Plan:** [202610/plan\_decisions.md](https://github.com/sase-org/sase--plans/blob/main/202610/plan_decisions.md)

## Description

gate: move the sase-core pin, adapt the Python wire and Archived mode, scaffold the `plan_decisions` beta flag, resolve memory scope and verify quotes at validate/propose/gate build, compile `decision_<id>` raw schema properties and `payload.decisions`, pin them in kind validation, normalize inputs before the receipt, bind submissions to the displayed review revision, freeze definitions during review, carry provisional values into feedback replans, and stamp immutable answers into the durable plan on every approval route.

## Notes

[2026-10-08T04:14:45Z · sase-1hi.3--2] PROPOSED FOLLOW-UP: symvision is red on 64 pre-existing unused public symbols across ~40 files outside this phase's scope (instructions/cache, instructions/render, amd/memory_units, axe/run_agent_wait_deps, core/bead_read_facade, core/created_epics, wait_dependency_resolution, ace/tui epic-follow models, llm_provider/commit_finalizer_git_status, sdd/_store_maintenance, sdd/_commit_store, doctor/checks_instructions, agent/launch_provenance, macro/_input_hint_wire, instructions/manifests, scripts/_chop_incremental_index, and more). Evidence: pristine HEAD (c7190fb99a) fails symvision identically once the fatal private-misuse error is bypassed (HEAD reports 66 unused; this tree reports 64, the delta being 19 this phase introduced and fixed, plus 2 this phase newly consumes). These were masked on master because the dead private _list_bead_state_changes_silent in src/sase/bead/_sync_git.py (added in 39dc48f03c, zero callers, deleted by this phase to unblock the fatal) aborted the symvision run before the unused scan. Do NOT bulk-privatize: several (EpicFollow*, wait-epic, instructions cache/compiler symbols) may be awaited by later phases of other open epics and need --epic-symbol keying to their owning beads instead. Suggested owner: whoever owns the wait/instructions/bead follow-ups; start from the symvision unused-public list.

[2026-10-08T04:14:56Z · sase-1hi.3--2] Verification for close: sase tool run check run to completion 2026-10-08. GREEN: fmt (python/markdown/generated docs), model policy, keep-sorted, ruff, mypy (5660 files), feature-flags schema (regenerated via tools/sync_feature_flags_schema --write), pyscripts, test-waits, changelog, patch/stitch terminology. RED only: symvision 64 pre-existing unused publics (see PROPOSED FOLLOW-UP note; none in this phase's files). Flag-on/off checks run and passing: tests/test_plan_decisions_gate.py flag tests (test_flag_off_rejects_decisions_key, test_flag_on_shows_decision_schema_rows) plus full gate file (13 passed); tests/test_plan_validate.py + tests/test_validate_sase_core_rs_tool.py (49 passed); direct-approval/committed/cli-answer/executor/sync-state files (60 passed); plan-gate suites incl. validation, execution, capacity, wait, feedback-input (92 passed). Symvision fixes in this phase's files: privatized 7 file-local helpers + _PlanDecisionError in sdd/plan_decisions.py; deleted dead sheet_binding/summary_binding/prompt_block_binding/compile_result_decisions_schema/DirectDecisionStamp; privatized feedback_rows_for_bundle/feedback_decision_rows, _render_provisional_decisions_section, _PlanDecision/_PlanDecisionChoice/_PlanDecisionCallout; deleted dead is_host_collected_property; deleted dead private _list_bead_state_changes_silent (pre-existing, verified failing on pristine HEAD). No --epic-symbol entries for sase-1hi.3 (sase bead epic-symbols clean).

[2026-10-08T04:15:35Z · sase-1hi.3--2] Gate phase complete: compile/resolve/freeze/stamp decisions in the plan gate with plan_decisions flag on/off coverage (flag-off rejects decisions key; flag-on shows decision schema rows). Verification notes on bead; only pre-existing symvision items remain (follow-up note). No epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-1hi.1](sase-1hi.1.md) ✓ · ⧖ 2026-10-07
- **Depends on:** [sase-1hi.2](sase-1hi.2.md) ✓ · ⧖ 2026-10-07
- **Blocks:** [sase-1hi.4](sase-1hi.4.md) ◐ · ⧖ 2026-10-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1hi.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.3.md) | [sase-1hi.3](sase-1hi.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ab48f19`](https://github.com/sase-org/sase/commit/ab48f1904e2afc67f7ff1a5c471808c176c4e6d8) | feat(plan): compile, resolve, freeze, and stamp decisions in the plan gate | [sase-1hi.3](sase-1hi.3.md) | 2026-10-08 00:18:01 EDT |
