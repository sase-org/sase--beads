# Bead: sase-1ab.9 — Cross-repo audit, guardrail, and deploy

[Bead Pages](../README.md) / [sase-1ab](README.md) / sase-1ab.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ss](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ss.md) · **Assignee:** `sase-1ab.9` · **Size:** medium
**Created:** 2026-09-26 00:15:15 EDT · **Closed:** 2026-09-27 07:22:12 EDT
**Plan:** [202609/sase\_turn\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_turn_rename.md)

## Description

audit-deploy: add the sase-turn terminology guard test, sweep and classify every remaining shell hit in all repos, fix tools/require_tool_run wording, note renamed identifiers on open beads, and redeploy chezmoi skills from the landed tree.

## Notes

[2026-09-27T10:35:02Z · sase-1ab.9] PROPOSED FOLLOW-UP: rename the deferred shell-followup/shell-member cluster (ShellFollowupWorkspace, launch_shell_followup, resolve_shell_next_action, SUCCESSFUL_SHELL_FOLLOWUP_OUTCOMES, shell_member_kind/shell_followup_agent fields, _fork_target fork=="shell" dead branch) in turns/followup.py, gate_turn/followup*.py, kind_next_action.py, monitor/followup.py, wait_dependency_resolution/*, monitor_state.py mirror comment; guarded by tests/test_sase_turn_terminology.py allowlist

[2026-09-27T11:21:51Z · sase-1ab.9--1] PROPOSED FOLLOW-UP: just check fails at lint (mypy) with 4 errors that reproduce identically on the clean base tree (verified via git stash: same 4 errors with working-tree changes stashed): _tree.py:622 prefix_key redefinition plus group_key tuple-type mismatches (:623, :629), and _agent_display_hint_sections.py:74 LEGACY_NAMED_PROC_SECTION_ID undefined. Unrelated to this phase (touches no TUI files); no existing bead tracks these 4 nodes (sase-15c/18q/1ay track different mypy failures).

[2026-09-27T11:22:12Z · sase-1ab.9--1] audit-deploy done: terminology guard tests/test_sase_turn_terminology.py passes (2 tests) and contract-manifest entry added (tests/test_contract_manifest.py passes); tools/require_tool_run wording fixed to SASE-agent phrasing; rename notes added to open beads sase-10p/11x/151/161/16v/19g; sase skill init --diff empty so chezmoi redeploy not due. just check red only at lint (mypy) with 4 TUI errors proven identical on clean base tree (recorded as PROPOSED FOLLOW-UP).

## Dependencies

- **Depends on:** [sase-1ab.5](sase-1ab.5.md) ✓ · ⧖ 2026-09-26
- **Depends on:** [sase-1ab.8](sase-1ab.8.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ab.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.9.md) | [sase-1ab.9](sase-1ab.9.md) | 5 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`eac55e9`](https://github.com/sase-org/sase/commit/eac55e929aac9cf1130c60f0f62196cda11b074a) | test(turn-rename): add sase-turn terminology guard plus audit-deploy wording fixes | [sase-1ab.9](sase-1ab.9.md) | 2026-09-27 07:24:52 EDT |
| sase-core | [`sase-core@912331c`](https://github.com/sase-org/sase-core/commit/912331c53149bb5da3da80feb37faea48c9fecdf) | fix(turn-rename): reword require\_tool\_run refusal from agent shell to SASE agent | [sase-1ab.9](sase-1ab.9.md) | 2026-09-27 07:28:09 EDT |
| sase-github | [`sase-github@1542750`](https://github.com/sase-org/sase-github/commit/1542750dba468dc705e709d1c58191762aea8480) | fix(turn-rename): reword require\_tool\_run refusal from agent shell to SASE agent | [sase-1ab.9](sase-1ab.9.md) | 2026-09-27 07:31:25 EDT |
| sase-telegram | [`sase-telegram@111d0c7`](https://github.com/sase-org/sase-telegram/commit/111d0c74e71d8b488b7801f31afc291f1812d9b6) | fix(turn-rename): reword require\_tool\_run refusal from agent shell to SASE agent | [sase-1ab.9](sase-1ab.9.md) | 2026-09-27 07:47:21 EDT |
| sase-research-artifacts | [`sase-research-artifacts@7be5cae`](https://github.com/sase-org/sase-research-artifacts/commit/7be5caed56a1cdc48241fb92d99a267b5d4e6f8d) | fix(turn-rename): reword require\_tool\_run refusal from agent shell to SASE agent | [sase-1ab.9](sase-1ab.9.md) | 2026-09-27 07:50:35 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ab.9--1][1] | check remaining scope | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.9.md

<!-- sase:referenced-by:end -->
