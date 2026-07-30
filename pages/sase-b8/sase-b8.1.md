# Bead: sase-b8.1 — Shared agent-lane vocabulary

[Bead Pages](../README.md) / [sase-b8](README.md) / sase-b8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b8.1` · **Size:** small
**Created:** 2026-07-30 14:32:34 UTC · **Closed:** 2026-07-30 14:50:19 UTC
**Plan:** [202607/family\_scoped\_agent\_provenance.md](https://github.com/sase-org/sase--plans/blob/main/202607/family_scoped_agent_provenance.md)

## Description

lanes: add the Python lane projection (lane name, lane kind, lane page path) composed from existing Rust core primitives, so every later phase resolves member -> lane identically.

## Notes

[2026-07-30T14:50:19Z · sase-b8.1] Added src/sase/agent_lanes.py (AgentLaneRef, lane_ref_for_agent, lane_ref_for_lane_name, lane_page_path, lane_name) as a pure projection over parse_agent_family_name/normalize+globalize_owned_agent_name/agent_link_target, with a guarded get_reserved_family_names read for bare lane labels. Added tests/test_agent_lanes.py (16 cases: solo->itself, member->family, nested foo.bar--code, legacy athena.* and global alice.athena.* spellings, registry-family vs real-solo lane names, registry-failure degradation, member spelling via the read-time path, lane_name projection matrix). Whitelisted the five symbols in the Justfile symvision invocation via --epic-symbol for their consuming phases (b8.2/b8.5/b8.7). Verified: just install; just _lint-symvision clean; just check green through fmt/lint/toobig; new tests pass; full just test + just test-visual pass (the two validate failures -- init skills drift and the 202607/prompts plan link -- reproduce on a stashed clean tree, and the intermittent xprompt-selector/PNG-countdown failures pass in isolation).

## Dependencies

- **Blocks:** [sase-b8.2](sase-b8.2.md) ✓
- **Blocks:** [sase-b8.3](sase-b8.3.md) ✓
- **Blocks:** [sase-b8.4](sase-b8.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b8.1/README.md) | [sase-b8.1](sase-b8.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`c537f7e`](https://github.com/sase-org/sase/commit/c537f7e03de7315d07f041def613cbba0bcde354) | feat(agents): add shared agent-lane vocabulary | [sase-b8.1](sase-b8.1.md) | 2026-07-30 14:51:14 |
