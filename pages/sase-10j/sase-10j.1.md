# Bead: sase-10j.1 — Superseded failed shell members stop blocking family waits

[Bead Pages](../README.md) / [sase-10j](README.md) / sase-10j.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.0i.f0` · **Assignee:** `sase-10j.1` · **Size:** medium
**Created:** 2026-09-13 21:53:04 EDT · **Closed:** 2026-09-13 23:54:20 EDT
**Plan:** [202609/failed\_monitor\_blocks\_family\_wait.md](https://github.com/sase-org/sase--plans/blob/main/202609/failed_monitor_blocks_family_wait.md)

## Description

wait-supersession: classify monitor/gate shell members on ArtifactCandidate and exclude a terminal-failed, follow-up-less shell member from the family's effective generation when a newer same-kind shell member exists in the same generation, with reproduction tests for the sase-zt.6.5.3 incident.

## Notes

[2026-09-14T03:52:42Z · sase-10j.1] PROPOSED FOLLOW-UP: just check fmt-py-check gate is broken on master, unrelated to this phase — tests/monitor/test_monitor_followup.py and tests/monitor/test_monitor_start_nested_cwd.py (both last touched by 649b04f79a) fail `ruff format --check`, blocking every agent's `just check` at the first gate until reformatted.

[2026-09-14T03:53:27Z · sase-10j.1] PROPOSED FOLLOW-UP: just check symvision gate is broken on master, unrelated to this phase — _resolve_ref_from_link_index in src/sase/ace/tui/actions/hints/_files.py is imported as a private symbol by a non-test file, blocking every agent's `just check` at the symvision gate until made public or the import removed.

[2026-09-14T03:54:20Z · sase-10j.1] Added ArtifactCandidate.shell_member_kind (monitor/gate, populated in _add_prepared via new shell_member_kind_for_meta, which also fixes gate_id extraction for the asdict(AgentMetaWire) wire-snapshot paths); extended _family_members_after_shell_handoffs in _index_entities.py to exclude a terminal, follow-up-less shell member superseded by a strictly-newer same-kind shell member in the same generation, leaving handoffs_present computed on pre-exclusion candidates unchanged, so family_candidate/_family_entity/family_candidate_for_root and terminal_blocking_artifacts_for_name all pick this up for free. Verified: reproduced the sase-zt.6.5.3 incident shape (start-failed --mon + --mon-0 retry handoff) resolving family/is_resolved/terminal_blocking_artifacts_for_name and chop ready.json in new tests; added gate-symmetry and different-kind-does-not-supersede tests; all existing fail-closed tests in test_monitor_wait_dependency.py/test_gate_wait_dependency.py pass unchanged (91/91 across the three touched test files). Ran just install, then verified ruff format/lint + mypy (whole repo, clean) scoped to changed files, toobig, keep-sorted, and just test-scoped (50 pre-existing failures, none in changed files or wait_dependency_resolution). just check's fmt-py-check and symvision gates fail on pre-existing, unrelated master issues (recorded as PROPOSED FOLLOW-UP notes on this bead) untouched by this diff. epic-symbols: none.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.kellys\_mbp.sase-10j.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.kellys_mbp.sase-10j.1/README.md) | [sase-10j.1](sase-10j.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3d74d69`](https://github.com/sase-org/sase/commit/3d74d690a2f55474ea8c297da9db67d9dca4f744) | fix(wait-dependency): stop superseded failed shell members from blocking family waits | [sase-10j.1](sase-10j.1.md) | 2026-09-13 23:56:29 EDT |
