# Bead: sase-17m.4.1.6 — Canonical session syntax and the legacy\_agent\_family\_syntax flag

[Bead Pages](../README.md) / [sase-17m.4.1](sase-17m.4.1.md) / sase-17m.4.1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.4.md) · **Assignee:** `sase-17m.4.1.6` · **Size:** medium
**Created:** 2026-09-24 13:32:35 EDT · **Closed:** 2026-09-24 20:46:40 EDT
**Plan:** [202609/agent\_session\_runtime\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_runtime_cutover.md)

## Description

syntax-flag: create the legacy_agent_family_syntax sunset flag with sase flag new. Make %id(<suffix>, session=<parent>), --next-fork session, gate spec "fork": "session", and SASE_AGENT_SESSION_ATTACH canonical. Route the retired spellings through one module that accepts them when the flag is on and rejects them with a replacement-naming error when it is off. Test both flag states.

## Notes

[2026-09-25T00:40:52Z · sase-17m.4.1.6] PROPOSED FOLLOW-UP: Resolve the existing Symvision unused-public reports for AgentSurvivorsError and Survivor in ACE kill termination and environ_has_launch_key in agent process_tree; syntax-flag compatibility symbols now pass Symvision.

[2026-09-25T00:46:40Z · sase-17m.4.1.6] Implemented canonical session syntax and legacy_agent_family_syntax sunset compatibility: canonical %id session=, --next-fork/gate fork, and SASE_AGENT_SESSION_ATTACH; legacy aliases are flag-gated while durable gates remain readable. Verified no epic-symbol entries and 318 focused tests pass. sase tool run check passes all stages through patch terminology; the remaining Symvision reports are pre-existing unrelated symbols, recorded as a PROPOSED FOLLOW-UP on this phase.

## Dependencies

- **Depends on:** [sase-17m.4.1.5](sase-17m.4.1.5.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17m.4.1.7](sase-17m.4.1.7.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.4.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.6/README.md) | [sase-17m.4.1.6](sase-17m.4.1.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`65d3dfb`](https://github.com/sase-org/sase/commit/65d3dfb1d4a641876b54015e4d8aaf583a34f9a3) | refactor(agent-session): canonical session syntax and legacy flag (sase-17m.4.1.6) | [sase-17m.4.1.6](sase-17m.4.1.6.md) | 2026-09-24 20:49:37 EDT |
