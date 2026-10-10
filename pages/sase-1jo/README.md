# Bead: sase-1jo — Databricks NYC application follow-ups

[Bead Pages](../README.md) / sase-1jo

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.6k](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.6k.md) · **Assignee:** `sase-1jo.land`
**Created:** 2026-10-10 15:45:42 EDT · **Closed:** 2026-10-10 16:43:05 EDT
**Plan:** [202610/databricks\_followups.md](https://github.com/sase-org/sase--plans/blob/main/202610/databricks_followups.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/databricks_followups.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/databricks_followups.md

<!-- sase:links:end -->

## Description

Every recommendation in the research report databricks_nyc_cv_and_role_pitches.md that an agent can safely finish is done: the public CV repo is free of stale claims with all five PDFs rebuilt, the interview-prep material exists, and the eval-pilot harness is built. A concise databricks_nyc_cv_and_role_pitches_v2.md report next to the original lists exactly what Bryan still has to do himself.

## Notes

[2026-10-10T20:37:44Z · sase-1jo.land] FOLLOW-UP TRIAGE (landing, before the remaining-work tale). No new task beads.

No child note contains a PROPOSED FOLLOW-UP entry. Reviewed sase-1jo.1 notes 1-2, sase-1jo.2 notes 1-2, sase-1jo.3 notes 1-2, and sase-1jo.4 note 1.

Declined as separate tasks:
- Interview prep is 288 lines against an "about 250" target. It has the six design-story cards, the four Agent Quality topics, the eval_pilot=skip gap, and no drafted Google-exit answer. The extra lines are those required sections. Not a defect.
- The v2 gaps are unfinished work of this epic, not an independent task. databricks_nyc_cv_and_role_pitches_v2.md is 32 lines. It omits the commit-SHA table (including 978ebc0), the Greenhouse API check, bryanbugyi.com, the exact GitHub and pdflatex next steps, the LinkedIn checklist pointer, the Omnigent pointer, and the launch-post follow-up.
- The epic description still says the eval harness is built. The reviewer decision eval_pilot=skip is authoritative. sase-1jo.3 closed with no code, and tools/agent_eval_pilot/ does not exist. The close note will say so. Not a new task.

Integration checked, no edit required:
- First sase-1jo commit is CV c46ba84 (2026-10-10 19:53Z). Later sase commits 5f47d11935 (archive search CLI) and 2c9f761210 (provider-instructions sunset flags) do not change the seven-harness list in README.md, the plugin list in docs/plugins.md, or the SQLite telemetry fact. CV claims still match.
- Research commits after 2fe342a, other than the v2 report 15020bd, are artifact-link persistence by sase-1jo.2 and sase-1jo.4.
- Open omnigent-ai/omnigent issues with runner or worktree in the title all have an assignee (checked 2026-10-10). The finished v2 should keep the original report's pointer.
- gh api /users/bbugyi200 on 2026-10-10: bio is still {day: "SWE at Google", night: "Batman of the internet"}, company null, hireable null, location Cranford, NJ, blog bryanbugyi.com.
- Greenhouse re-fetch on 2026-10-10: both jobs have a null application_deadline. 8379331002 is New York in location and office. 8842963002 location.name is New York City, New York, and offices[0] is San Francisco, California. The current v2 does not record that split.

Verified complete, left out of the tale:
- base_cv_sase=add is in c46ba84. Page counts are base 3, Batman 2, Google 2, LangChain 2. Google ends May 2026 in those four PDFs. Prometheus, Grafana, Gemini, and "33 pipeline" are gone. The Databricks CV was not in that commit and is still 2 pages, with its TODO(bryan) comments still present. Base bullets match Databricks bullets 1, 2, and 6, without the Omnigent line.
- eval_pilot=skip was honored. No harness and no real runs.

[2026-10-10T20:43:05Z · sase-1jo.land] Verified sase-1jo.1 c46ba84: base_cv_sase=add, Google ends May 2026, page counts 3/2/2/2, stale Prometheus/Grafana/Gemini/33-pipeline claims gone, Databricks CV untouched. Verified sase-1jo.2 2fe342a: six design-story cards, Agent Quality brief, eval_pilot=skip, no Google-exit draft. Verified sase-1jo.3 closed with no harness, matching eval_pilot=skip. Completed the v2 report against the phase spec in this turn (first draft 15020bd; 978ebc0 is the pre-epic Databricks CV). Greenhouse re-checked, GitHub profile re-checked, bryanbugyi.com slug re-checked, Omnigent runner/worktree issues re-checked. No PROPOSED FOLLOW-UP notes. No sase integration edit: 5f47d11935 and 2c9f761210 do not change the harness, plugin, or telemetry claims. No parent bead.

[2026-10-10T20:45:57Z · sase-1jo.land] just symvision after close fails only on unrelated unused-public-symbol findings; no sase-1jo epic-symbol entries remain (epic-symbols lists nothing) and this turn changed no sase source file. Findings: agent_archive_corpus_cache.py (AgentArchiveCorpusCacheKey, CachedAgentArchiveCorpus, archive_corpus_cache_key, invalidate_agent_archive_corpus_cache, link_facet_signature), ace/tui/modals/update_failure_geometry.py (action_footer_lines, choose_outer_width, content_cell_width, footer_groups_for_width, hint_lines, is_cramped, logical_lines, max_cell_width, max_outer_size, pack_footer_lines, required_outer_width), agent/auto_restart/history.py (project_for_done). Left unrepaired per the closeout plan.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1jo.1](sase-1jo.1.md) | CV repo cleanup and PDF rebuilds | ✓ closed | medium | 2026-10-10 | 1 | 0 |
| [sase-1jo.2](sase-1jo.2.md) | Interview-prep pack | ✓ closed | medium | 2026-10-10 | 1 | 1 |
| [sase-1jo.3](sase-1jo.3.md) | SASE agent-eval pilot harness | ✓ closed | large | 2026-10-10 | 1 | 0 |
| [sase-1jo.4](sase-1jo.4.md) | Remaining-work report (v2) | ✓ closed | small | 2026-10-10 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1jo: Databricks NYC application follow-ups [closed]"]
    n1["sase-1jo.1: CV repo cleanup and PDF rebuilds [closed]"]
    n2["sase-1jo.2: Interview-prep pack [closed]"]
    n3["sase-1jo.3: SASE agent-eval pilot harness [closed]"]
    n4["sase-1jo.4: Remaining-work report (v2) [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n1 -.-> n4
    n2 -.-> n4
    n3 -.-> n4
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1jo.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1jo.1/README.md) | [sase-1jo.1](sase-1jo.1.md) | 0 |
| [bbugyi200.apollo.sase-1jo.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1jo.2/README.md) | [sase-1jo.2](sase-1jo.2.md) | 1 |
| [bbugyi200.apollo.sase-1jo.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1jo.3.md) | [sase-1jo.3](sase-1jo.3.md) | 0 |
| [bbugyi200.apollo.sase-1jo.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1jo.4/README.md) | [sase-1jo.4](sase-1jo.4.md) | 1 |
| [bbugyi200.apollo.sase-1jo.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1jo.land.md) | [sase-1jo](README.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--research | [`sase--research@2fe342a`](https://github.com/sase-org/sase--research/commit/2fe342a01ae76e025a939a5a8dae220ed6d800f2) | docs(research): add Databricks NYC interview-prep pack | [sase-1jo.2](sase-1jo.2.md) | 2026-10-10 16:05:17 EDT |
| sase--research | [`sase--research@15020bd`](https://github.com/sase-org/sase--research/commit/15020bda925074c23342aa378641649ade8fd5c0) | feat(research): add Databricks application follow-up report | [sase-1jo.4](sase-1jo.4.md) | 2026-10-10 16:20:31 EDT |
| sase--plans | [`sase--plans@bf49a73`](https://github.com/sase-org/sase--plans/commit/bf49a7334a4e1048dfc7949797c3e4aafbe76fe8) | docs(plans): mark databricks follow-up epic and v2 closeout plans done | [sase-1jo](README.md) | 2026-10-10 16:48:02 EDT |
| sase--research | [`sase--research@9227d14`](https://github.com/sase-org/sase--research/commit/9227d141b8afedc27e2b7690a5c55fe977d30bb5) | docs(research): bring databricks v2 report up to closeout spec | [sase-1jo](README.md) | 2026-10-10 16:49:29 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jo.2][1] | Need parent epic context and remaining phases | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1jo.2/README.md

<!-- sase:referenced-by:end -->
