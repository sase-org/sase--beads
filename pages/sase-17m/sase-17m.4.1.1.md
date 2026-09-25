# Bead: sase-17m.4.1.1 — Agent-session attach and promotion modules

[Bead Pages](../README.md) / [sase-17m.4.1](sase-17m.4.1.md) / sase-17m.4.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.4.md) · **Assignee:** `sase-17m.4.1.1` · **Size:** medium
**Created:** 2026-09-24 13:32:29 EDT · **Closed:** 2026-09-24 14:51:11 EDT
**Plan:** [202609/agent\_session\_runtime\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_runtime_cutover.md)

## Description

attach-modules: rename agent/_family_attach_{candidates,directives,launch,resolution,types}.py, _family_promotion.py, and family_attach.py to their _agent_session_* / agent_session_attach names. Rename their types, functions, and locals, the attach env-payload JSON keys (keeping named legacy readers), and the xprompt directive fields family_attach_parent/suffix and name_family_args. Update every importer, including ACE imports only, and rename the matching tests.

## Notes

[2026-09-24T18:50:12Z · sase-17m.4.1.1] PROPOSED FOLLOW-UP: master fails several gates independent of this rename (identical set at clean HEAD): `symvision` reports ~70 private symbols imported across files (llm_provider/usage/*, ace plugins_browser_install_*, _number/_optional_text/_string_list helpers); `toobig` flags src/sase/ace/tui/widgets/decks/panel.py at 1051 lines; and 28 scoped tests fail (completion cli_spec snapshot drift, test_parser_plan/test_parser_tool help, wait_checks summary now has `deferred_unconfirmed=` in test_axe_chop_wait_checks/incremental_scans, ACE prompt-panel/LLM-calls widget tests, app import budget). `sase tool run check` cannot go green until these are fixed.

[2026-09-24T18:50:25Z · sase-17m.4.1.1] PROPOSED FOLLOW-UP: commit 9bd351b67 (wait release confirmation) merged over wire-cutover and left WaitDependencyIndexQueries using the removed `families` / `family_name` names (mypy red, runtime AttributeError); fixed here in core/wait_dependency_resolution/_index_queries.py (agent_sessions / agent_session_name) plus a missing return annotation in axe/run_agent_wait_deps.py. The core-history phase should treat the rest of core/wait_dependency_resolution as already partly renamed.

[2026-09-24T18:51:11Z · sase-17m.4.1.1] Renamed agent/_family_attach_{candidates,directives,launch,resolution,types}.py, _family_promotion.py and family_attach.py to _agent_session_attach_*/_agent_session_promotion/agent_session_attach with all types, functions, locals and every src/test importer (no ACE files needed changes; no old names remain per git grep). Attach env payload now writes agent_session_role/parent_agent_session_member_name/parent_agent_session_role_suffix; loader reads new keys first then the legacy agent_family_role/parent_family_* keys via one named helper (this also repairs old payloads that wire-cutover had left unreadable); env var stays SASE_AGENT_FAMILY_ATTACH as LEGACY_AGENT_FAMILY_ATTACH_ENV. Directive fields are agent_session_attach_parent/suffix and name_agent_session_args; the family= keyword and its user-facing text are untouched. Renamed the matching test files, updated shard_timings, added legacy/new payload tests. Verified: ruff/mypy/flags/pyscripts/changelog/terminology/validate/committed-plans pass; 452 changed+related tests pass. symvision, toobig and 28 scoped tests fail identically at clean HEAD (recorded as PROPOSED FOLLOW-UP); I also fixed a preexisting mypy break in wait_dependency_resolution (families/family_name left by wire-cutover merge).

## Dependencies

- **Blocks:** [sase-17m.4.1.2](sase-17m.4.1.2.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.4.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.1/README.md) | [sase-17m.4.1.1](sase-17m.4.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f2790e0`](https://github.com/sase-org/sase/commit/f2790e0e588628a0efe3d769c52b2faf284b5be9) | refactor(agent-session): rename attach and promotion modules (sase-17m.4.1.1) | [sase-17m.4.1.1](sase-17m.4.1.1.md) | 2026-09-24 14:52:20 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.4.1.1][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-17m.4.1.8][2] | Check PROPOSED FOLLOW-UP notes from earlier phases | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.8/README.md

<!-- sase:referenced-by:end -->
