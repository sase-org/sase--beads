# Bead: sase-17m.3 — Python persistence and wire cutover

[Bead Pages](../README.md) / [sase-17m](README.md) / sase-17m.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qh.md) · **Assignee:** `sase-17m.3` · **Size:** large
**Created:** 2026-09-23 22:46:36 EDT · **Closed:** 2026-09-24 13:15:45 EDT
**Plan:** [202609/agent\_session\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_rename.md)

## Description

wire-cutover: bump the core pin and switch sase to the new binding names. Rename the Python wire mirrors and durable JSON fields: new data is written only with agent_session keys, and readers accept both key spellings. Rename the Agent model fields and the rebuildable caches.

## Notes

[2026-09-24T06:47:14Z · sase-17m.2.1.land] DISCOVERED ISSUE (routed by sase-17m.2.1 land agent from core-expand phase follow-ups): wire-cutover inputs from sase-17m.2.1.1/.2/.3/.4 — (1) tighten dual-shape directive tests from companion commit a764a76d4 (tests/test_xprompt_directive_contract.py id keyword tuple, tests/test_xprompt_directive_completion_parity.py, _directive_completion_tokens.py keyword tuple) to session-only after the core pin bump; (2) switch sase callers to new binding names parse_agent_session_name, resolve_agent_session_parent, reconcile_agent_artifact_index_dismissed_agent_session_members, fleet_followed_batch_agent_session_promotions (src/sase/ace/tui/models/_fleet_agents_promotion.py + tests) and tighten family_id/family_role/family_label readers once core-contract emits new keys; (3) switch to convert_session op and agent_session_generation keys; (4) core renamed diagnostic codes missing_family_member_name/family_conversion_upsert to agent-session spellings (sase has no match on them — verify).

[2026-09-24T14:48:38Z · sase-17m.3.1.7] HAND-OFF runtime-cutover (from sase-17m.3.1.7 verify): src/sase/agents/cli_list.py still emits agent_family / agent_family_role JSON keys (lines 100-101, no legacy comment); CLI output keys are yours per wire-cutover scope boundary. Unrelated meanings of family left alone (model_family, vcs_family, RelationKind.FAMILY, font-family).

[2026-09-24T14:48:50Z · sase-17m.3.1.7] HAND-OFF ace-cutover (from sase-17m.3.1.7 verify): fleet row/node/identity readers hydrate family_role / agent_family_role / family_label / family_id with legacy comments; ACE module, label, row-kind, and CSS names untouched. agent_bundle.py LEGACY_AGENT_FIELD_NAMES table is the permanent dismissed-bundle migration reader.

[2026-09-24T14:49:00Z · sase-17m.3.1.7] HAND-OFF core-contract (from sase-17m.3.1.7 verify): Python still sends legacy agent_family_parallel to the core capacity struct via capacity_session_keys_for_core and _agent_runner_slot_capacity.py (core has no agent_session_parallel alias yet); AgentSessionNameKind.FAMILY value stays until the emitted-value flip. Pinned core eef7ca4 includes core-expand ae9dbf6; new agent-session binding names verified present in built extension.

[2026-09-24T17:18:35Z · sase-17m.3.1.land] VERIFIED by sase-17m.3.1.land (2026-09-24) after the child epic closed. The phase auto-closed as delegated work landed. Child epic sase-17m.3.1 covers the whole wire-cutover scope: core pin 9956773 plus new binding names (3.1.1); canonical keys and accessor, with every deprecated plan_chain alias now migrated and deleted (3.1.2 + land); wire mirrors, including the wait-dep vocabulary, launch attach fields, and dismissal report fields (3.1.3 + land); Agent model fields (3.1.4); durable JSON (3.1.5); name registry schema v3 (3.1.6). Note #1 inputs: directive tests were tightened and binding names switched in 3.1.1. The ownership op literal is now convert_session (core accepts the alias). Python sends no family_generation key, and neither renamed diagnostic code matches anything in sase. Hand-offs #2-#4 still stand for runtime-cutover, ace-cutover, and core-contract. For core-contract, cleanup_targets_for_core is a new agent_family_parallel boundary alongside capacity_session_keys_for_core, and the core scanner still reads only agent_family_parallel.

## Dependencies

- **Depends on:** [sase-17m.1](sase-17m.1.md) ✓ · ⧖ 2026-09-23
- **Depends on:** [sase-17m.2](sase-17m.2.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-17m.4](sase-17m.4.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17m.3.md) | [sase-17m.3](sase-17m.3.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.2.1.land][1] | Check wire-cutover scope for routing follow-ups | 2 |
| read-by | [agent:sase-17m.3.1.land][2] | Need phase notes (hand-offs recorded by 3.1.7) | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.2.1.land/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.land/README.md

<!-- sase:referenced-by:end -->
