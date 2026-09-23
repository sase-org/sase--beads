# Bead: sase-16n.11.7 — Finish the project tag (+sase) landing-gap fixes

[Bead Pages](../README.md) / [sase-16n.11](sase-16n.11.md) / sase-16n.11.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-16n.11.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-16n.11.land.md) · **Assignee:** `sase-16n.11.7.land`
**Created:** 2026-09-23 14:10:51 EDT · **Closed:** 2026-09-23 15:39:13 EDT
**Plan:** [202609/project\_tags\_landing\_gaps\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202609/project_tags_landing_gaps_finish.md)

## Description

Fix the defects the sase-16n.11 landing audit found in its own work. sase-core: a macOS-red CI test, and accept joining lines. sase-nvim: tag colors never show, and palette overrides get lost. sase: a follow-up monitor regression, a warm-refresh that does nothing, pager tag styling, and a history-filter blocking load. Also integrate the new tribe PROMPTS chip, and close the remaining test and doc gaps.

## Notes

[2026-09-23T18:29:24Z · sase-16y.land] DISCOVERED ISSUE (sase-16y.land, relaying sase-16y.1 PROPOSED FOLLOW-UP): at master ed8172fda 8 bead-work nodes fail on a pristine tree, expecting a '+sase' project tag but rendering '#git:sase': tests/test_bead/test_work_rendering.py::TestRenderEdgeCases::test_vcs_context_prefixes_every_regular_epic_segment, test_work_rendering_changespec.py::TestPatchRendering (4 nodes), test_work_task_rendering.py::test_task_prompt_has_exact_single_segment_order_and_feedback_tail, test_cli_work_task.py::test_task_work_launches_one_checkpointed_agent[OPEN/READY] and ::test_task_work_foreign_full_id_uses_owner_launch_context. Also tests/completion/test_snapshot.py (2 nodes) drifts on description_digest of 'sase prompt edit/run/select' (project-tag help text); fix with just sync-completion-spec.

[2026-09-23T19:39:13Z · sase-16n.11.7.land] Verified all 4 phases against code: core-accept (sase-core fb1ca29: accept deletion ends at ref, glued-match find_at resume, pre-v5 catalog fallback, macOS case-variant test builds records directly, cleanups; sase-core master CI green incl. macOS; sase pin fb1ca29), nvim-tokens (sase-nvim 9378313: set/list modifier_set, record-based override tracking, picker warn+cancel, trailing space), backend-regressions (1230ed8da: tag-token prefix check, peek-only history filter, conftest cache reset, assertions, raw/json skip, occupant_kind, docs), tui-tag-surfaces (00badb84e: warm rebuild of detail/modals with pilot test, resolved-only per-project pager accents outside fences, tribe chip via known_project_tag_for). Landing fixes: epic note #1 (8 bead-work nodes expecting +sase rendered #git:sase because project_tag_for now returns unknown names unchanged) fixed with an autouse pinned tag catalog in tests/test_bead/conftest.py; completion snapshot digest drift fixed via just sync-completion-spec. Integration: reviewed all master commits since 14:10 (clans, jump footer, llm-provider usage, plugins browser, sase-16t scope toasts) - none render VCS refs or duplicate tag logic; no changes needed. Follow-ups: sase-16n.11.7.3 PROPOSED FOLLOW-UP (stale sase-16y MemberJumpSection epic-symbol) declined - already retired by afc72c698. just check fails only on symvision for other epics' symbols (ClanSummaryDigest/sase-170, llm_provider capability cache/_probe_meta, plugins browser mark_all_message); focused tests (bead, completion, project tags) pass via sase tool run test. No epic-symbol entries.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16n.11.7.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.11.7.land/README.md) | [sase-16n.11.7](sase-16n.11.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f456a8b`](https://github.com/sase-org/sase/commit/f456a8b3b11758abe409287c39dd7c6a6bc22362) | test(project-tags): pin tag catalog for bead launch tests and sync completion spec | [sase-16n.11.7](sase-16n.11.7.md) | 2026-09-23 15:42:39 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16y.land][1] | children | 5 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16y.land/README.md

<!-- sase:referenced-by:end -->
