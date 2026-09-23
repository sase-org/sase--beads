# Bead: sase-16n.11.7 — Finish the project tag (+sase) landing-gap fixes

[Bead Pages](../README.md) / [sase-16n.11](sase-16n.11.md) / sase-16n.11.7

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-16n.11.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-16n.11.land.md) · **Assignee:** `sase-16n.11.7.land`
**Created:** 2026-09-23 14:10:51 EDT
**Plan:** [202609/project\_tags\_landing\_gaps\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202609/project_tags_landing_gaps_finish.md)

## Description

Fix the defects the sase-16n.11 landing audit found in its own work. sase-core: a macOS-red CI test, and accept joining lines. sase-nvim: tag colors never show, and palette overrides get lost. sase: a follow-up monitor regression, a warm-refresh that does nothing, pager tag styling, and a history-filter blocking load. Also integrate the new tribe PROMPTS chip, and close the remaining test and doc gaps.

## Notes

[2026-09-23T18:29:24Z · sase-16y.land] DISCOVERED ISSUE (sase-16y.land, relaying sase-16y.1 PROPOSED FOLLOW-UP): at master ed8172fda 8 bead-work nodes fail on a pristine tree, expecting a '+sase' project tag but rendering '#git:sase': tests/test_bead/test_work_rendering.py::TestRenderEdgeCases::test_vcs_context_prefixes_every_regular_epic_segment, test_work_rendering_changespec.py::TestPatchRendering (4 nodes), test_work_task_rendering.py::test_task_prompt_has_exact_single_segment_order_and_feedback_tail, test_cli_work_task.py::test_task_work_launches_one_checkpointed_agent[OPEN/READY] and ::test_task_work_foreign_full_id_uses_owner_launch_context. Also tests/completion/test_snapshot.py (2 nodes) drifts on description_digest of 'sase prompt edit/run/select' (project-tag help text); fix with just sync-completion-spec.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16n.11.7.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.11.7.land/README.md) | [sase-16n.11.7](sase-16n.11.7.md) | 0 |
