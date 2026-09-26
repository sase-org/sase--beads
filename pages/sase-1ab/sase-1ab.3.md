# Bead: sase-1ab.3 — Runtime, syntax, and CLI cutover

[Bead Pages](../README.md) / [sase-1ab](README.md) / sase-1ab.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ss](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ss.md) · **Assignee:** `sase-1ab.3` · **Size:** large
**Created:** 2026-09-26 00:15:08 EDT · **Closed:** 2026-09-26 13:44:06 EDT
**Plan:** [202609/sase\_turn\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_turn_rename.md)

## Description

runtime-cutover: rename every non-TUI package, module, and identifier (gate_shell, shells, plan_shell, question_shell, ...). Make the turn CLI flags, gate-spec spellings, and config key canonical behind the legacy_sase_shell_syntax sunset flag, and update CLI help and JSON output, the scheduler job, telemetry, xprompts, and skill sources.

## Notes

[2026-09-26T17:43:05Z · sase-1ab.3--1] PROPOSED FOLLOW-UP: rule-7 flag lint (tool_receipts/sase-1am) is owned by epic sase-1ah, not this phase. sase-1am closed 2026-09-26T17:00Z while its registry definition survives, so 'sase tool run check' stops at _lint-flags. Triaged by sase-1ap.2 and sase-1aq.2 already. Owner: remove the flag definition per tools/check_feature_flags rule 7 (read sase memory sase_flags first).

[2026-09-26T17:43:20Z · sase-1ab.3--1] PROPOSED FOLLOW-UP: bump sase-core-revision.txt past the turn cutover so the Rust scanner/index emits agent_session_turn + turn_kind instead of agent_session_shell + shell_kind. Until then the LEGACY_AGENT_SESSION_SHELL_KEY reader bridge (plan_chain + core/wire, added this phase) must stay. Removing the bridge before the pin bump re-breaks every scan-backed gate_turn/monitor lookup (find_gate_turn_by_gate_id, list_gate_turns). Owned by the sase-core side; coordinate with the core repo.

[2026-09-26T17:43:30Z · sase-1ab.3--1] PROPOSED FOLLOW-UP: finish the non-TUI 'gate shell' prose sweep (~200 hits: docstrings, comments, log lines in history/, question_gate_turn/, scripts/sase_chop_gate_turn_reclaim.py, _plan_approval_response.py). Left as-is because chop-SDK log contracts (tests/test_chop_sdk.py) and chat-history assertions pin the current strings; rename src + tests together. 'Agent-shell'/'Proc-shell' prose belongs to the agent_session-rename and TUI/proc phases, not this one.

[2026-09-26T17:43:45Z · sase-1ab.3--1] PROPOSED FOLLOW-UP: 'just test-scoped' (diff-closure lane) timed out at the 9-minute inline budget with zero failures through ~70 percent. Focused suites covering every touched area pass (gate_turn, turns, plan/question_gate_turn, wire cutover, keys, legacy syntax, fakey incl. capacity e2e, core facade). Re-run the scoped lane to completion before landing if the tree is still this wide.

[2026-09-26T17:44:06Z · sase-1ab.3--1] Runtime cutover complete: fixed the scan-backed gate_turn lookup break (LEGACY_AGENT_SESSION_SHELL_KEY reader bridge for the pre-cutover Rust core), repaired rename fallout (test kwarg mismatches, duplicate imports/__all__ keys, mypy attrs, feature-flags schema sync, skill markdown). Focused suites pass (gate_turn/turns/plan/question_gate_turn/wire/fakey e2e). 'sase tool run check' is green through ruff+mypy+all lints except foreign rule-7 (tool_receipts/sase-1am, owned by sase-1ah); leftovers recorded as PROPOSED FOLLOW-UP notes. Parent epic stays open.

## Dependencies

- **Depends on:** [sase-1ab.2](sase-1ab.2.md) ✓ · ⧖ 2026-09-26
- **Blocks:** [sase-1ab.4](sase-1ab.4.md) ◐ · ⧖ 2026-09-26
- **Blocks:** [sase-1ab.5](sase-1ab.5.md) ◐ · ⧖ 2026-09-26
- **Blocks:** [sase-1ab.6](sase-1ab.6.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ab.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.3.md) | [sase-1ab.3](sase-1ab.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d5fc758`](https://github.com/sase-org/sase/commit/d5fc75864f0afb44b5f9fa7d1c21b6d4d913916d) | feat(runtime): cut over gate shell to gate turn | [sase-1ab.3](sase-1ab.3.md) | 2026-09-26 13:46:45 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ab.3--1][1] | continue runtime_turn_cutover: verify bead state before epic-symbols refresh and close | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.3.md

<!-- sase:referenced-by:end -->
