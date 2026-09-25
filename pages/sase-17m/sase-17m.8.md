# Bead: sase-17m.8 — sase-core contract flip

[Bead Pages](../README.md) / [sase-17m](README.md) / sase-17m.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qh.md) · **Assignee:** `sase-17m.8` · **Size:** medium
**Created:** 2026-09-23 22:46:41 EDT · **Closed:** 2026-09-25 14:53:33 EDT
**Plan:** [202609/agent\_session\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_rename.md)

## Description

core-contract: breaking feat! sase-core change. Serialize the new key and value names, drop the legacy binding names, emit sessions/ link paths and session: fleet keys, and bump the changed schema versions and the fleet protocol. Keep aliases so legacy durable data still reads.

## Notes

[2026-09-24T06:47:42Z · sase-17m.2.1.land] DISCOVERED ISSUE (routed by sase-17m.2.1 land agent from core-expand phase follow-ups; full per-file list in sase-17m.2.1.4 note #1 and sase-17m.2.1.2 note #2 / sase-17m.2.1.3 note #2): core-contract must flip every pinned legacy spelling marked '// legacy agent-family spelling; flips in core-contract' (agent_scan wire agent_family/_role/_parallel/family_shell/family_root_dismissed/member/key/anchor, AGENT_SESSION_INDEX_COLUMN + SQL agent_family column/idx, runner serial_family claim, stats/relationships Session emits family, identity LEGACY_AGENT_SESSION_KIND/PAGES_DIR families/, launch family_attach_*, hold family/families, ownership convert_family + RESERVATION/CONTAINER_KIND + family_generation keys, fleet locators family_id/role/label + LEGACY_AGENT_SESSION_KEY_SEGMENT + family-<hex> fallback, gate followup family_name, owner-facts/presentation family_* fields, group canonical_global_family, editor directive family keyword metadata, fleet_api_v1.json + gateway contract.rs, family_dismissal_lineage prefix) and remove the four legacy pyo3 registrations parse_agent_family_name, resolve_agent_family_parent, reconcile_agent_artifact_index_dismissed_family_members, fleet_followed_batch_family_promotions (grep 'legacy binding name; removed in core-contract').

[2026-09-24T15:40:21Z · sase-17m.3.1.land] DISCOVERED ISSUE (routed by the sase-17m.3.1 land agent from sase-17m.3.1.3 follow-up #1 and sase-17m.3.1.4 follow-up #1): at pin eef7ca4, four core structs pin agent_session_parallel as rename="agent_family_parallel" with NO agent_session_parallel alias: runner_capacity/wire.rs:77, agent_cleanup/wire.rs:97, agent_scan/wire.rs:575 (AgentMetaWire) and fleet_owner_facts.rs:158. The Python side therefore keeps sending the legacy key through named boundary helpers: sase.core.runner_slots.capacity_session_keys_for_core, ace/tui/models/_agent_runner_slot_capacity.py, and (being added by the sase-17m.3.1 remaining-work plan) the cleanup planner's core-bound target projection. The wire-cutover regression was the cleanup wire sending agent_session_parallel, which core silently ignored, so tests/test_core_facade/test_agent_cleanup_facade.py parity [parallel-family-root, clan-scope-active-parallel-family] fails. core-contract must: (a) add alias="agent_session_parallel" (or serialize the new name) on these structs before or together with Python switching those helpers to the new key; (b) NOT drop the agent_family_parallel alias on the capacity/cleanup request wires while Python still sends it, despite the 'drop aliases on purely in-process request wires' rule, or the Rust capacity/cleanup planners silently lose parallel membership; (c) note that agent_scan/scanner.rs agent_meta_from_object derives legacy agent_clan only from agent_family_parallel. That is correct for pre-rename files and latent today because no Python writer emits either parallel key, but read agent_session_parallel too if a writer ever does. agent_stats/runner.rs:600 already reads both.

[2026-09-25T13:52:50Z · sase-17m.5.1.6.land] DISCOVERED ISSUE: proposed by sase-17m.5.1.6.3 note #1. ACE fleet readers in _fleet_agents_nodes.py and _fleet_agents_identity.py prefer labels.session_label plus summary/locator agent_session_id and agent_session, while core currently validates agent_session_label and rejects several of those new top-level keys. Align emitted and consumed fleet wire names during this phase's core-contract flip; retain legacy readers as specified.

[2026-09-25T18:53:33Z · sase-17m.8] Implemented the canonical core agent-session contract flip and regenerated the fleet API contract. Verified just test -p sase_core_py (205 passed) and git diff --check. sase tool run check built the core/gateway/LSP successfully, then stopped at the planned downstream Python mirror handoff: validate_sase_core_rs still expects scan schema 9 while core now emits 10.

## Dependencies

- **Depends on:** [sase-17m.5](sase-17m.5.md) ✓ · ⧖ 2026-09-23
- **Depends on:** [sase-17m.6](sase-17m.6.md) ✓ · ⧖ 2026-09-23
- **Depends on:** [sase-17m.7](sase-17m.7.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-17m.9](sase-17m.9.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.8/README.md) | [sase-17m.8](sase-17m.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@2a0fc2a`](https://github.com/sase-org/sase-core/commit/2a0fc2abdaea1d7fa40f93f439c902895f2eff6f) | feat(core)!: canonicalize agent-session contracts | [sase-17m.8](sase-17m.8.md) | 2026-09-25 14:55:11 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.2f.cld][1] | Check whether the core contract flip (which emits new durable keys) has landed, to assess double-migration risk with shell->turn | 1 |
| read-by | [agent:research.2f.final][2] | Check whether core-contract phase already emits agent_session_shell spellings (double-migration risk with turn rename) | 1 |
| read-by | [agent:research.2k.cld][3] | Audit: confirm the core flip landed before the sase-side mirror bump, causing the schema-mismatch outage | 1 |
| read-by | [agent:research.2k.final][4] | Verify the incident's core-flip/pin-bump phase ordering for the consolidated research report | 1 |
| read-by | [agent:sase-17m.2.1.land][5] | Check core-contract scope for routing follow-ups | 2 |
| read-by | [agent:sase-17m.8][6] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2f.cld/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2f.final/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2k.cld/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2k.final/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.2.1.land/README.md
[6]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.8/README.md

<!-- sase:referenced-by:end -->
