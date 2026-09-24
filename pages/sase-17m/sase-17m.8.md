# Bead: sase-17m.8 — sase-core contract flip

[Bead Pages](../README.md) / [sase-17m](README.md) / sase-17m.8

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qh.md) · **Assignee:** `sase-17m.8` · **Size:** medium
**Created:** 2026-09-23 22:46:41 EDT
**Plan:** [202609/agent\_session\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_rename.md)

## Description

core-contract: breaking feat! sase-core change. Serialize the new key and value names, drop the legacy binding names, emit sessions/ link paths and session: fleet keys, and bump the changed schema versions and the fleet protocol. Keep aliases so legacy durable data still reads.

## Notes

[2026-09-24T06:47:42Z · sase-17m.2.1.land] DISCOVERED ISSUE (routed by sase-17m.2.1 land agent from core-expand phase follow-ups; full per-file list in sase-17m.2.1.4 note #1 and sase-17m.2.1.2 note #2 / sase-17m.2.1.3 note #2): core-contract must flip every pinned legacy spelling marked '// legacy agent-family spelling; flips in core-contract' (agent_scan wire agent_family/_role/_parallel/family_shell/family_root_dismissed/member/key/anchor, AGENT_SESSION_INDEX_COLUMN + SQL agent_family column/idx, runner serial_family claim, stats/relationships Session emits family, identity LEGACY_AGENT_SESSION_KIND/PAGES_DIR families/, launch family_attach_*, hold family/families, ownership convert_family + RESERVATION/CONTAINER_KIND + family_generation keys, fleet locators family_id/role/label + LEGACY_AGENT_SESSION_KEY_SEGMENT + family-<hex> fallback, gate followup family_name, owner-facts/presentation family_* fields, group canonical_global_family, editor directive family keyword metadata, fleet_api_v1.json + gateway contract.rs, family_dismissal_lineage prefix) and remove the four legacy pyo3 registrations parse_agent_family_name, resolve_agent_family_parent, reconcile_agent_artifact_index_dismissed_family_members, fleet_followed_batch_family_promotions (grep 'legacy binding name; removed in core-contract').

## Dependencies

- **Depends on:** [sase-17m.5](sase-17m.5.md) ◐ · ⧖ 2026-09-23
- **Depends on:** [sase-17m.6](sase-17m.6.md) ◐ · ⧖ 2026-09-23
- **Depends on:** [sase-17m.7](sase-17m.7.md) ◐ · ⧖ 2026-09-23
- **Blocks:** [sase-17m.9](sase-17m.9.md) ◐ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.8/README.md) | [sase-17m.8](sase-17m.8.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.2f.cld][1] | Check whether the core contract flip (which emits new durable keys) has landed, to assess double-migration risk with shell->turn | 1 |
| read-by | [agent:sase-17m.2.1.land][2] | Check core-contract scope for routing follow-ups | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2f.cld/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.2.1.land/README.md

<!-- sase:referenced-by:end -->
