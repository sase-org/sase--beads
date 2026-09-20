# Bead: sase-142.5.2 — Admit the row shapes real arrivals actually have

[Bead Pages](../README.md) / [sase-142.5](sase-142.5.md) / sase-142.5.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-142.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-142.land.md) · **Assignee:** `sase-142.5.2` · **Size:** medium
**Created:** 2026-09-20 17:09:29 EDT
**Plan:** [202609/reachable\_row\_insert.md](https://github.com/sase-org/sase--plans/blob/main/202609/reachable_row_insert.md)

## Description

reachable-insert-for-real-rows: decide on evidence whether a workflow family that arrives whole can be inserted in place, implement that answer under the existing insert-equals-rebuild contract, and either prove the shape reaches display_row_insert or name the topology invariant that blocks it.

## Notes

[2026-09-20T23:15:04Z · sase-142.5.2] sase-142.5.2 decision: whole arriving workflow families are NOT separable from the tree mutation the insert gate is written against (exit path b).

INVARIANT (proven by probe + committed tests): a family that arrives whole with a fresh parent name always adds exactly one name-root subgroup banner in STANDARD/BY_STATUS/BY_MACHINE. Structural descendants inherit the parent's grouping anchor (grouping_keys_for via presentation_anchor), so the family itself crosses the >=2 banner threshold under its own root — verified with loader-faithful rows (parent WORKFLOW + steps with generic block step-names git/gh/run, parent linkage as the snapshot loader writes). The in-place insert never mounts new banner rows: banner option ids embed tree sequence, so the kept_rows + banner-id checks decline as status_membership_change. That check sits BELOW the _is_plain_leaf_row type gate: with the type gate monkeypatched open, the same arrival still declines status_membership_change with the widget untouched. Removing the type gate alone would not reach the insert. At scope level the arrival attributes workflow_tree_change to its own panel (phase-1 predicate, per-panel since 630220713), so the panel rebuilds whole and the insert is never attempted there either.

BOUNDARY (measured, deliberately not implemented): a childless WORKFLOW parent (steps STARTING/unrendered, singleton root, no banner change) IS banner-neutral and inserts with rebuild equivalence when the type gate is held open (probe: admitted ok=True equiv=True, STANDARD + BY_STATUS). Only the conservative type clauses block it (_is_plain_leaf_row's WORKFLOW clause; scope _is_workflow_shaped). Not admitted: no evidence this apply shape occurs on athena — the loader emits parent+steps together and the soak showed 7/7 arrivals whole — and relaxing two coordinated gates for a speculative transient risks exactly the unsafe-insert failure the epic forbids. It buys the soak no metric.

SHAPES THAT DO REACH THE INSERT: plain-leaf arrivals (no clan/family/workflow relation, existing status bucket, fits the columns, no new banner) — a fresh singleton name is fine (count 1 < 2 threshold). Covered end-to-end by test_an_ordinary_arrival_inserts_its_row_without_repainting_any_panel and test_insert_leaves_the_widget_as_a_rebuild_would.

PROBE RECIPE FOR sase-142.5.4 (reverify): launch plain-leaf probes with NO workflow block (a bare `sase run` prompt referencing no #git/#gh block, so the agent arrives AgentType.RUNNING with no children), RUNNING status, short name, staggered one launch at a time, confirming each reaches rendered before the next. Expect display_row_insert on each @epic arrival; fallback tally recipe is docs/perf_runbook.md lines 544-548 (added by phase 1; decline observability via _try_insert_panel_rows fallback_reason confirmed present, no edit needed).

TESTS: tests/ace/tui/widgets/test_agent_list_try_insert_rows.py gains test_an_arriving_workflow_family_adds_its_own_banner_and_declines and test_the_family_banner_blocks_the_insert_below_the_type_gate (STANDARD + BY_STATUS). No src changes. just check + harness/diff suites green (see close note).

## Dependencies

- **Depends on:** [sase-142.5.1](sase-142.5.1.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-142.5.4](sase-142.5.4.md) ◐ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-142.5.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-142.5.2/README.md) | [sase-142.5.2](sase-142.5.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`baf07cf`](https://github.com/sase-org/sase/commit/baf07cf13ceb9bada37390b98b61cab188f086f2) | test(tui): pin the whole-family row-insert decline behind its banner invariant | [sase-142.5.2](sase-142.5.2.md) | 2026-09-20 19:18:45 EDT |
