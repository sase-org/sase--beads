# Bead: sase-17m.5.1 — ACE agent session surfaces (ace-cutover)

[Bead Pages](../README.md) / [sase-17m.5](sase-17m.5.md) / sase-17m.5.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.5.md) · **Assignee:** `sase-17m.5.1.land`
**Created:** 2026-09-25 00:06:00 EDT
**Plan:** [202609/agent\_session\_ace\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_ace_cutover.md)

## Description

Inside ACE (src/sase/ace/**, tests/ace/**, tests/perf/**, default_config.yml, and sase.schema.json), the former agent-family concept is named "agent session" in every module, class, identifier, row kind, relation, grouping mode, trace name, perf scenario, comment, test, and golden. The visible copy reads SESSION SHELLS, SESSION, "Session" grouping, and "collapse session". Core-emitted legacy spellings stay as marked readers. Unrelated meanings of "family" are unchanged. The performance contract does not change, and `sase tool run check` passes.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.5.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.5.1.land/README.md) | [sase-17m.5.1](sase-17m.5.1.md) | 0 |
