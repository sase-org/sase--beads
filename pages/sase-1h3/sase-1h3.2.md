# Bead: sase-1h3.2 — Instruction manifest wire schema in sase-core, binding, adapter, and pin move

[Bead Pages](../README.md) / [sase-1h3](README.md) / sase-1h3.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0xc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0xc.md) · **Assignee:** `sase-1h3.2` · **Size:** medium
**Created:** 2026-10-06 12:43:26 EDT · **Closed:** 2026-10-06 14:13:21 EDT
**Plan:** [202610/e2\_instruction\_bundles\_shadow\_mode.md](https://github.com/sase-org/sase--plans/blob/main/202610/e2_instruction_bundles_shadow_mode.md)

## Description

manifest-wire: add the instruction manifest v1 wire types, closed vocabulary, invariants, and common_digest to sase-core with a dict binding, a golden cross-language fixture, a thin sase adapter, and the sase-core pin move.

## Notes

[2026-10-06T18:13:05Z · sase-1h3.2--1] PROPOSED FOLLOW-UP: tests/test_agent_name_registry_rebuild_pending.py::test_registry_rebuild_keeps_live_identity_pending_claim fails only under full-suite parallel load (rebuild.call_count 1 vs 0) but passes 8/8 in isolation; it imports only sase.agent.names and is untouched by manifest-wire — likely stale-registry timing flake, needs quarantine or retry

[2026-10-06T18:13:21Z · sase-1h3.2--1] manifest-wire done and verified: sase-core instruction_manifest module+binding+fixtures pass sase tool run check in sase-core checkout; sase adapter+parity tests 10/10 pass; tools/check_sase_core_rs_bindings passes (804/804 incl. 2 new bindings); just check 52916 passed with 1 unrelated load-only registry-test flake (8/8 isolated, filed as follow-up) + 2 KNOWN symvision; epic-symbols clean; pin move left to host land (both repos uncommitted per host-owned completion)

## Dependencies

- **Blocks:** [sase-1h3.3](sase-1h3.3.md) ◐ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h3.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h3.2.md) | [sase-1h3.2](sase-1h3.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@fa39036`](https://github.com/sase-org/sase-core/commit/fa390362a556fe156701ee6bdf505411d4f0f7c5) | feat(instructions): instruction manifest v1 wire schema, binding, and golden fixture (sase-1h3.2) | [sase-1h3.2](sase-1h3.2.md) | 2026-10-06 14:15:22 EDT |
| sase | [`ec6ffa3`](https://github.com/sase-org/sase/commit/ec6ffa33a8019ccc4c7121199fb707774796682b) | feat(instructions): manifest-wire sase adapter, parity fixture, and docs (sase-1h3.2) | [sase-1h3.2](sase-1h3.2.md) | 2026-10-06 14:19:33 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1h3.2--1][1] | verify phase scope and completion | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h3.2.md

<!-- sase:referenced-by:end -->
