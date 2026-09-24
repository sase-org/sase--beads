# Bead: sase-17m.3.1.3 — Python wire mirrors hydrate either spelling

[Bead Pages](../README.md) / [sase-17m.3.1](sase-17m.3.1.md) / sase-17m.3.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.3.md) · **Assignee:** `sase-17m.3.1.3` · **Size:** medium
**Created:** 2026-09-24 02:56:46 EDT · **Closed:** 2026-09-24 06:32:33 EDT
**Plan:** [202609/agent\_session\_wire\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_wire_cutover.md)

## Description

wire-mirrors: rename the agent-session fields and types in the src/sase/core wire mirrors (scan markers and conversion, agent_scan_wire_family_shell.py to agent_scan_wire_agent_session_shell.py, launch, cleanup, group-archive, runner-slot, hold, gate hand-off, monitor follow-up, wait-dependency index) and the fleet nodes, rows, promotion, and follow store. Each hydrates from either spelling and sends new spellings to core.

## Notes

[2026-09-24T09:45:51Z · sase-17m.3.1.3] PROPOSED FOLLOW-UP: core-contract: pinned core capacity struct accepts agent_session/agent_session_role/agent_session_shell_* aliases but has no agent_session_parallel alias, so capacity_session_keys_for_core still sends legacy agent_family_parallel

[2026-09-24T10:06:54Z · sase-17m.3.1.3] PROPOSED FOLLOW-UP: durable-json: wait-dep index domain vocabulary still family-named (families dict, ArtifactCandidate.family_name, FamilyCandidate, family_candidate_for_root, _family_entity, kind==family) — rename with the source-kind value flip

[2026-09-24T10:07:23Z · sase-17m.3.1.3] PROPOSED FOLLOW-UP: agent-model/runtime-cutover: ACE _capacity_record_from_agent, AgentListEntry fields, and sase agent list -j output keys still emit agent_family spellings — confirm owner

[2026-09-24T10:07:52Z · sase-17m.3.1.3] PROPOSED FOLLOW-UP: runtime-cutover: SASE_AGENT_FAMILY_ATTACH env payload keys, spawn_family_successor params, and launch-request agent_meta.agent_family dotted-path reads still legacy

[2026-09-24T10:19:40Z · sase-17m.3.1.3] PROPOSED FOLLOW-UP: symvision private-import gate fails identically at base HEAD (73 violations in 41 untouched files) — pre-existing just check blocker, needs an owner outside wire-cutover

[2026-09-24T10:32:33Z · sase-17m.3.1.3] wire mirrors hydrate either spelling and emit new spellings; verified: 12 new either-spelling/emission tests incl real sase_core_rs round trips (scan, capacity, fleet locator), 4000+ focused tests green, ruff+mypy+fmt green; just check blocked only by pre-existing symvision failures proven identical at base HEAD; core still lacks agent_session_parallel capacity alias (follow-up noted)

## Dependencies

- **Depends on:** [sase-17m.3.1.2](sase-17m.3.1.2.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17m.3.1.4](sase-17m.3.1.4.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.3.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.3/README.md) | [sase-17m.3.1.3](sase-17m.3.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b855380`](https://github.com/sase-org/sase/commit/b855380098eddf57ed0e60b9d5dce764fee64264) | refactor(agent-session): Python wire mirrors hydrate either spelling (sase-17m.3.1.3) | [sase-17m.3.1.3](sase-17m.3.1.3.md) | 2026-09-24 06:34:26 EDT |
