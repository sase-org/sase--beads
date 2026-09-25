# Bead: sase-17m.2.1.3 — Fleet core and gateway

[Bead Pages](../README.md) / [sase-17m.2.1](sase-17m.2.1.md) / sase-17m.2.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17m.2.md) · **Assignee:** `sase-17m.2.1.3` · **Size:** medium
**Created:** 2026-09-23 22:54:52 EDT · **Closed:** 2026-09-24 01:32:08 EDT
**Plan:** [202609/agent\_session\_core\_expand.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_core_expand.md)

## Description

fleet: rename fleet_family.rs to fleet_agent_session.rs and the family concept in fleet_*, fleet_contract, and sase_gateway. Add the fleet_followed_batch_agent_session_promotions binding, accept session: logical-key segments and session-<hex> fallback ids on input, and keep fleet_api_v1.json and emitted keys unchanged.

## Notes

[2026-09-24T05:30:22Z · sase-17m.2.1.3] Phase fleet exit: remaining famil hits in owned files are (a) legacy spellings pinned for core-contract - serde rename/alias on agent_session_id/family_id (locators.rs, resolution.rs OwnerResolutionFactsWire), agent_session_label/family_label, agent_session_role/family_role, candidate agent_session_root_dismissed/agent_session_member/agent_session_key/agent_session_anchor, OwnerPresentationFactsWire agent_session_role/agent_session_parallel(no alias, legacy input only); LEGACY_AGENT_SESSION_KEY_SEGMENT family segment + family-<hex> fallback emit; family_dismissal_lineage error prefix; fleet_api_v1.json + gateway contract.rs byte-identical (committed_ passes); (b) legacy binding fleet_followed_batch_family_promotions kept next to new agent_session name; (c) legacy-input fixtures family-1/family-2/family-resolved/lane + agent_family/family_id JSON keys in tests; (d) unrelated: target_family cfg, clan/family rendering prose in byte-identical contract. No sase workspace change needed: emitted keys/contract unchanged.

[2026-09-24T05:30:54Z · sase-17m.2.1.3] PROPOSED FOLLOW-UP: core-contract flips family_id/family_label/family_role/agent_family_role/agent_session member-key-anchor-root_dismissed/agent_family_parallel serde spellings, LEGACY_AGENT_SESSION_KEY_SEGMENT + family-<hex> fallback emit, family_dismissal_lineage prefix, fleet_api_v1.json + gateway contract.rs, and removes fleet_followed_batch_family_promotions binding (files: fleet_contract/locators|resolution|status|projection|follows, fleet_presentation, fleet_owner_facts, fleet_catalog, fleet_agent_session, sase_gateway contract+contracts, sase_core_py fleet/mod)

[2026-09-24T05:31:23Z · sase-17m.2.1.3] PROPOSED FOLLOW-UP: wire-cutover switches sase src/sase/ace/tui/models/_fleet_agents_promotion.py + tests from fleet_followed_batch_family_promotions to fleet_followed_batch_agent_session_promotions and tightens family_id/family_role/family_label readers to the new binding output

[2026-09-24T05:32:08Z · sase-17m.2.1.3] fleet phase done: fleet_family.rs->fleet_agent_session.rs + concept renamed across fleet_*, fleet_contract, sase_gateway; new fleet_followed_batch_agent_session_promotions binding next to legacy; session:/session-<hex> accepted on input via logical_key_matches/canonical_logical_key; fleet_api_v1.json + emitted keys byte-identical. Verified: just fast clean; sase_core fleet, gateway fleet (68), committed_ contract (2), sase_core_py fleet (5) pass; sase tool run check green. First full run hit 4 gateway route failures matching known flake sase-15g (504/snapshot_refresh); all 4 pass isolated.

## Dependencies

- **Depends on:** [sase-17m.2.1.2](sase-17m.2.1.2.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-17m.2.1.4](sase-17m.2.1.4.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.2.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.2.1.3/README.md) | [sase-17m.2.1.3](sase-17m.2.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@b814a0f`](https://github.com/sase-org/sase-core/commit/b814a0fc08ad5a94aba5863fa4550b3622ac9126) | refactor(fleet): rename family to agent session with session key acceptance | [sase-17m.2.1.3](sase-17m.2.1.3.md) | 2026-09-24 01:35:09 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.2.1.3][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-17m.2.1.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.2.1.3/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.2.1.land/README.md

<!-- sase:referenced-by:end -->
