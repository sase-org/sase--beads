# Bead: sase-17m.4.1 — Runtime, syntax, and CLI cutover to agent session (runtime-cutover)

[Bead Pages](../README.md) / [sase-17m.4](sase-17m.4.md) / sase-17m.4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.4.md) · **Assignee:** `sase-17m.4.1.land`
**Created:** 2026-09-24 13:32:27 EDT · **Closed:** 2026-09-24 23:57:02 EDT
**Plan:** [202609/agent\_session\_runtime\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_runtime_cutover.md)

## Description

Outside src/sase/ace, sase names the former agent-family concept "agent session" in every module, identifier, comment, message, and test. %id(..., session=), agent queries session:/kind:session, --next-fork session, gate spec "fork": "session", and SASE_AGENT_SESSION_ATTACH are the canonical user syntax. The retired spellings keep working only behind the legacy_agent_family_syntax sunset flag. CLI help, JSON output, the editor bridge, and the skill sources use the new vocabulary, and `sase tool run check` passes.

## Notes

[2026-09-25T03:57:02Z · sase-17m.4.1.land] Verified all eight closed child phases, every phase note, the linked runtime-cutover plan, and the eight phase commits from f2790e0e5 through a2ec65a1f. Current source has agent-session attach, names, runtime lanes, syntax flag, session query and JSON contracts, editor output, and updated skill sources. Old public identifiers and retired syntax are absent from canonical help/skills. A focused 118-test run passed for both flag states, attach, query, CLI JSON, editor, and direct plan approval. Later commits 11b9c56b0 and 561e4b6dd integrated direct approval prompts and the legacy query parser with session syntax; the subsequent command-line/tool/ACE commits do not leave an unadapted runtime consumer. No epic-symbol entries belong to this epic or its phases.

Follow-up disposition by proposing phase: .1 #2 was fixed in .1; .1 #1, .2 #1/#2, .3 #1, .4 #1, .5 #3, .6 #1, .7 #1, and .8 #1 were clean-base gate/test issues, not rename work. ACE mypy and test issues were already routed to active sase-18f and the clean-base cluster to sase-18s (+1 here); the absent-store completion failure was independently reproduced and corroborated on sase-14o (+1 here). The restart recovery-path assertion, smoke_sase_core_rs_tool_runs:75 mypy failure, and memory-generator drift test were reproduced and recorded on active sase-18f. Existing sase-18r covers the test-wait pragma; 4fb83bb4f fixed the ACE/process-tree Symvision survivors; 561e4b6dd fixed wheel-cache mypy and stale 18i exemptions; toobig is removed from check. The remaining 18i/18j symbol work belongs to those still-open epics, and 18j was notified. .4 #2 and .5 #1 are recorded as the core-contract handoff on parent sase-17m.4; .5 #2 was completed by later child phases or handed to ACE/session-pages/docs; .7 #2 and .8 #2 are recorded as parent handoffs for ACE and session-pages/docs; .7 #3 was an informational agents_sync boundary check requiring no action. .8 #3 stale flake-baseline IDs were recorded on active sase-j7. No new task was warranted where an active epic or exact duplicate already owns the work.

Current sase tool run check 1e935a0fd75a9f458f284dad70cc5b40 passes source mypy but stops at the unrelated extensionless smoke-tool type error; targeted completion kind-coverage and cli_spec tests pass. Phase .8 had previously run the escalated scoped lane with 47,218 passes and only the unrelated memory-generator drift. These external green-check blockers are recorded on sase-18f and do not reopen this rename scope.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.4.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.land/README.md) | [sase-17m.4.1](sase-17m.4.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.4.1.2][1] | parent epic scope | 1 |
| read-by | [agent:sase-17m.4.1.land][2] | Need the epic scope, children, and linked plan file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.land/README.md

<!-- sase:referenced-by:end -->
