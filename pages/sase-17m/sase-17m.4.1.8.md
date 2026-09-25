# Bead: sase-17m.4.1.8 — Skill sources, leftover tests, and classification sweep

[Bead Pages](../README.md) / [sase-17m.4.1](sase-17m.4.1.md) / sase-17m.4.1.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.4.md) · **Assignee:** `sase-17m.4.1.8` · **Size:** medium
**Created:** 2026-09-24 13:32:38 EDT · **Closed:** 2026-09-24 23:29:40 EDT
**Plan:** [202609/agent\_session\_runtime\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_runtime_cutover.md)

## Description

skills-sweep: update the sase_run, sase_gate, sase_pipe, sase_questions, sase_monitor, and sase_agents_status skill sources and with_feedback.yml. Rename any family-named test files still in scope and update the shard-timing and flake baselines. Classify every remaining non-ACE famil hit, record hand-offs on sase-17m.4, and run sase tool run check.

## Notes

[2026-09-25T03:27:13Z · sase-17m.4.1.8] PROPOSED FOLLOW-UP: sase tool run check cannot go green from this phase; every remaining failure reproduces on the clean origin/master tip and is outside the agent-session rename: (1) mypy tools/sase_core_wheel_cache:433/604 (arg-type, var-annotated) and tools/smoke_sase_core_rs_tool_runs:75 (var-annotated); (2) symvision: unused public sase-18j triage symbols (tool/triage_inputs.py gather_*/triage_knobs, core/tool_run.py tool_run_triage_*/tool_run_failures) and sase-18i epic-symbol whitelist entries (CoderPlacement, PlanGateHistory, RetiredGate) that no longer suppress; (3) tests/main/test_init_memory_committed_drift.py::test_repo_project_memory_notes_match_generator_output (generator output differs for tools/*.md shims); (4) tests/test_sase_core_wheel_cache_tool.py:490 fixed-sleep-missing-pragma when it was flagged earlier. All other lint gates and 47218 scoped tests pass.

[2026-09-25T03:27:23Z · sase-17m.4.1.8] PROPOSED FOLLOW-UP: session-pages/docs-memory: tests/test_agent_tribe_terminology.py:39 lists docs/agent_families.md (rename with the doc); tests/test_pr_tags.py and tests/test_vcs_log_tags.py assert sidecar families/<name>.md URLs; tests/sdd/test_hosted_links.py, tests/sdd_store/test_sidecar_init_*.py and tests/main/test_repo_init_plan.py assert the sidecar families/ directory; src/sase/sase_agent.py, sdd/hosted_links.py, sdd/_init_files.py, sdd/templates/sidecar-agents-README.md and sdd/assets/agents-directory-map.png.prompt.md keep families/ paths and family wording for session-pages.

[2026-09-25T03:27:33Z · sase-17m.4.1.8] PROPOSED FOLLOW-UP: tests/reproducible_flake_baseline.txt has 12 stale ids unrelated to this rename (tests/test_core_vcs_log.py and tests/main/test_artifact_cli_link_health.py no longer exist; several function ids no longer match a def in test_completion_candidates_contract.py, test_keymaps_display_help.py, test_prompt_panel_section_navigation_targets.py, test_monitor_resume.py). This phase fixed the two family-named ids (fakey test_monitor_capacity_e2e / test_pipe_e2e) that earlier renames had left stale.

[2026-09-25T03:29:40Z · sase-17m.4.1.8] skills-sweep done. Skill sources (sase_run/gate/pipe/questions/monitor/agents_status) and with_feedback.yml use agent-session vocabulary and session= / --next-fork session / "fork": "session" syntax; sase skill init --diff previewed, nothing deployed. Renamed 6 family-named loader test files, fixed 2 stale flake-baseline ids, and swept ~218 non-ACE test files (test names, locals, prose, fixtures; legacy fixtures keep legacy names/markers). Fixed real src stragglers found by the sweep: retry_prompt dropped family instead of session (retry kept session=), plan direct-approval placement/receipt/cards (mode session, agent_session field, legacy family receipt key still read), dispatch/launch.py checked session_id instead of agent_session_id, workflow_loader removed-kind error text, relaunch_prompt error wording, gate --next-fork now advertises canonical choices (completion kind coverage). Fixed stale ACE-side test expectations from the syntax/query phases (kill-and-edit family=, AgentCatalogRow.family, query goldens) and regenerated cli_spec. Classification: every remaining famil hit outside ACE is (a) unrelated, (b) legacy reader/core-mirror, (c) flag module, or (d) sidecar families/ paths; ACE/core-contract/telegram/docs hand-offs recorded on sase-17m.4. Verified: just fix clean, ruff/keep-sorted/flags/pyscripts/changelog/terminology/validate/committed-plans pass, symvision reports only upstream sase-18i/18j symbols, diff-scoped test lane 47218 passed with 1 failure (test_init_memory_committed_drift) that reproduces on clean HEAD; epic-symbols clean. sase tool run check stops at mypy tools/smoke_sase_core_rs_tool_runs:75, an upstream failure recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-17m.4.1.7](sase-17m.4.1.7.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.4.1.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.8/README.md) | [sase-17m.4.1.8](sase-17m.4.1.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a2ec65a`](https://github.com/sase-org/sase/commit/a2ec65a1f44f6c15dab488f4df7797d49c00cf2c) | refactor(agent-session): sweep skill sources, leftover tests, and stragglers (sase-17m.4.1.8) | [sase-17m.4.1.8](sase-17m.4.1.8.md) | 2026-09-24 23:31:26 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.4.1.8][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-17m.4.1.land][2] | Need the child scope and notes | 1 |
| read-by | [agent:sase-18f.land][3] | Check whether leftover-tests phase already covers the 34 dialect test failures | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.8/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.land/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.land/README.md

<!-- sase:referenced-by:end -->
