# Bead: sase-1hi.6 — ACE Decisions section, compact Verdict, and decision-aware inbox

[Bead Pages](../README.md) / [sase-1hi](README.md) / sase-1hi.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.5n](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.5n.md) · **Assignee:** `sase-1hi.6` · **Size:** large
**Created:** 2026-10-07 18:48:29 EDT · **Closed:** 2026-10-08 03:39:54 EDT
**Plan:** [202610/plan\_decisions.md](https://github.com/sase-org/sase--plans/blob/main/202610/plan_decisions.md)

## Description

tui: build the ACE Decisions accordion above a compact docked Verdict with the outcome sentence, new gate keys, a document pane that folds the frontmatter and lights the chosen branch, draft persistence, revision-bound submits on every path, a settled-elsewhere state, toast/inbox/gate-card/PLAN-lane decision rendering, and new visual goldens.

## Notes

[2026-10-08T07:39:21Z · sase-1hi.6--2] PROPOSED FOLLOW-UP: test_macro_string_literals_avoid_xprompt_terms fails on untouched tests/history/test_continuation_replay_hydration_basic.py ("%xprompts_enabled:false" strings); reproduces without this bead diff, pre-existing not caused by ACE decisions

[2026-10-08T07:39:29Z · sase-1hi.6--2] PROPOSED FOLLOW-UP: test_candidates_fast_path_child_cpu_budget[snippet] and test_hinted_raw_prompt_moves_to_identity_and_keeps_its_markers fail only under the full parallel lane and pass in isolation; treat as parallel-lane flakes, rerun serially before attributing

[2026-10-08T07:39:36Z · sase-1hi.6--2] PROPOSED FOLLOW-UP: symvision stale --epic-symbol sase-1hi.5(summary_binding) in Justfile owned by tracked bead sase-o7; not keyed to sase-1hi.6, left untouched

[2026-10-08T07:39:43Z · sase-1hi.6--2] PROPOSED FOLLOW-UP: visual goldens from plan:202610/ace_decisions.md not built (plan_gate_tale_decisions_*, epic decisions, inbox gate card, plan toast); fixtures must use real plan gate builder and existing plan_gate_* goldens need one compact-Verdict update group via just fix-tui-screenshots

[2026-10-08T07:39:54Z · sase-1hi.6--2] ACE decisions accordion + compact Verdict landed: sheet/rows/document modules, gate keys, submit paths carry decision_* + review_revision, toast/inbox/gate-card/PLAN rendering, docs + keymap tables. Verified: 99 targeted tests pass (plan_decision_ace, modal title, keymaps, gate footer, notification plan gate) + 17 config-schema keymap tests; just fmt clean; sase bead epic-symbols sase-1hi.6 empty. Full just check (49m) shows only pre-existing/parallel-flake failures recorded as PROPOSED FOLLOW-UP notes; visual goldens deferred as follow-up.

## Dependencies

- **Depends on:** [sase-1hi.4](sase-1hi.4.md) ✓ · ⧖ 2026-10-07
- **Blocks:** [sase-1hi.9](sase-1hi.9.md) ✓ · ⧖ 2026-10-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1hi.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.6.md) | [sase-1hi.6](sase-1hi.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`edb0120`](https://github.com/sase-org/sase/commit/edb0120aecf99141c4c3b9a20023aab97d2e0a74) | feat(ace): plan decisions accordion with compact verdict and decision-aware inbox | [sase-1hi.6](sase-1hi.6.md) | 2026-10-08 03:55:03 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1hi.6--2][1] | verify epic symbols before close | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.6.md

<!-- sase:referenced-by:end -->
