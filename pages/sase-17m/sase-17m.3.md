# Bead: sase-17m.3 — Python persistence and wire cutover

[Bead Pages](../README.md) / [sase-17m](README.md) / sase-17m.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qh.md) · **Assignee:** `sase-17m.3` · **Size:** large
**Created:** 2026-09-23 22:46:36 EDT
**Plan:** [202609/agent\_session\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_rename.md)

## Description

wire-cutover: bump the core pin and switch sase to the new binding names. Rename the Python wire mirrors and durable JSON fields: new data is written only with agent_session keys, and readers accept both key spellings. Rename the Agent model fields and the rebuildable caches.

## Notes

[2026-09-24T06:47:14Z · sase-17m.2.1.land] DISCOVERED ISSUE (routed by sase-17m.2.1 land agent from core-expand phase follow-ups): wire-cutover inputs from sase-17m.2.1.1/.2/.3/.4 — (1) tighten dual-shape directive tests from companion commit a764a76d4 (tests/test_xprompt_directive_contract.py id keyword tuple, tests/test_xprompt_directive_completion_parity.py, _directive_completion_tokens.py keyword tuple) to session-only after the core pin bump; (2) switch sase callers to new binding names parse_agent_session_name, resolve_agent_session_parent, reconcile_agent_artifact_index_dismissed_agent_session_members, fleet_followed_batch_agent_session_promotions (src/sase/ace/tui/models/_fleet_agents_promotion.py + tests) and tighten family_id/family_role/family_label readers once core-contract emits new keys; (3) switch to convert_session op and agent_session_generation keys; (4) core renamed diagnostic codes missing_family_member_name/family_conversion_upsert to agent-session spellings (sase has no match on them — verify).

## Dependencies

- **Depends on:** [sase-17m.1](sase-17m.1.md) ✓ · ⧖ 2026-09-23
- **Depends on:** [sase-17m.2](sase-17m.2.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-17m.4](sase-17m.4.md) ◐ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.3.md) | [sase-17m.3](sase-17m.3.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.2.1.land][1] | Check wire-cutover scope for routing follow-ups | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.2.1.land/README.md

<!-- sase:referenced-by:end -->
