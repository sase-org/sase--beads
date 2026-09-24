# Bead: sase-17m.4.1.6 — Canonical session syntax and the legacy\_agent\_family\_syntax flag

[Bead Pages](../README.md) / [sase-17m.4.1](sase-17m.4.1.md) / sase-17m.4.1.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.4.md) · **Assignee:** `sase-17m.4.1.6` · **Size:** medium
**Created:** 2026-09-24 13:32:35 EDT
**Plan:** [202609/agent\_session\_runtime\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_runtime_cutover.md)

## Description

syntax-flag: create the legacy_agent_family_syntax sunset flag with sase flag new. Make %id(<suffix>, session=<parent>), --next-fork session, gate spec "fork": "session", and SASE_AGENT_SESSION_ATTACH canonical. Route the retired spellings through one module that accepts them when the flag is on and rejects them with a replacement-naming error when it is off. Test both flag states.

## Dependencies

- **Depends on:** [sase-17m.4.1.5](sase-17m.4.1.5.md) ◐ · ⧖ 2026-09-24
- **Blocks:** [sase-17m.4.1.7](sase-17m.4.1.7.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.4.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.6/README.md) | [sase-17m.4.1.6](sase-17m.4.1.6.md) | 0 |
