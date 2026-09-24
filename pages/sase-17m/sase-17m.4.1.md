# Bead: sase-17m.4.1 — Runtime, syntax, and CLI cutover to agent session (runtime-cutover)

[Bead Pages](../README.md) / [sase-17m.4](sase-17m.4.md) / sase-17m.4.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.4.md) · **Assignee:** `sase-17m.4.1.land`
**Created:** 2026-09-24 13:32:27 EDT
**Plan:** [202609/agent\_session\_runtime\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_runtime_cutover.md)

## Description

Outside src/sase/ace, sase names the former agent-family concept "agent session" in every module, identifier, comment, message, and test. %id(..., session=), agent queries session:/kind:session, --next-fork session, gate spec "fork": "session", and SASE_AGENT_SESSION_ATTACH are the canonical user syntax. The retired spellings keep working only behind the legacy_agent_family_syntax sunset flag. CLI help, JSON output, the editor bridge, and the skill sources use the new vocabulary, and `sase tool run check` passes.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.4.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.land/README.md) | [sase-17m.4.1](sase-17m.4.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.4.1.2][1] | parent epic scope | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.2/README.md

<!-- sase:referenced-by:end -->
