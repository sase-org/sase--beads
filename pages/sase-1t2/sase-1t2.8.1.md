# Bead: sase-1t2.8.1 — Durable hijack latches across agent handoffs

[Bead Pages](../README.md) / [sase-1t2.8](sase-1t2.8.md) / sase-1t2.8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t2.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t2.8.md) · **Assignee:** `sase-1t2.8.1.land`
**Created:** 2026-11-16 04:09:07 EST · **Closed:** 2026-11-16 15:16:28 EST
**Plan:** [202611/hijack\_latch\_boundaries.md](https://github.com/sase-org/sase--plans/blob/main/202611/hijack_latch_boundaries.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/hijack_latch_boundaries.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 5 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/hijack_latch_boundaries.md

<!-- sase:links:end -->

## Description

Complete sase-1t2.8 with durable, cancellable hijacks that suppress successors at safe agent-turn boundaries.

## Notes

[2026-11-16T20:16:28Z · sase-1t2.8.1.land] Land verification for sase-1t2.8.1 (durable hijack latches).

STEP 1: All 7 phases are closed and every child note was reviewed. The contract was spot-verified in source:
- sase-core c58ecb80/e9b1cf04 add latched state, latch/apply_latch/cancel_latch events, latched_at/boundary/boundary_outcome/suppressed_followup/forced/owner_identity fields, reconcile and 120s force policy, and latched eligibility for finalizing and staged-pending turns. The sase pin 969096d0 contains them.
- agent/hijack/latch.py exposes request/observe/apply/cancel/moot/force.
- HijackLatchedError (spawn_guard.py) is not a WorkspaceClaimError and is re-raised ahead of every fallback.
- locks.py documents the lock order.
- Runner checkpoints exist at staged adoption, replay, in-process successor, retry, detached delivery, and run-end moot.
- The stale sweep calls reconcile_latched_records.
- The TUI shows pending overlays with cancel/force.
- The CLI has -c/-e/-n with exit 3, and the docs are updated.

STEP 2 integration: commits landed during the epic (0731d06c5a, e27b302028, 00d01b4f9d, 75ed2a1239, 6917629c59, ac19f907ae, dc09b5eba3, e1d81ee6c6, f8c2763ae3) are compatible:
- The TUI decision fingerprint includes latch state and boundary, and offer modes include latched.
- Hijack name resolution goes through the new indexed find_named_agent.
- The split stale-sweep and stop-orchestrator modules carry the latch wiring.

EPIC-CAUSED FIX IN THIS LANDING: sase-1t2.8.1.5's mirror_hijack_overlays_to_containers read agent.is_agent_session_container_row directly and crashed apply_hijack_ledger_presentation for duck-typed rows (tests/fakey/test_agent_hijack_e2e.py::test_hijack_reload_escalate_inherits_both_repos_through_finalizer). It now uses getattr like its sibling checks, and the e2e plus canary files pass.

Wrapped check b8effd9f5a0f125e125085a356ac012f: all lint gates, symvision, and epic-symbol freshness pass. The test lane escalated to the full suite: 61297 passed, 11 failed, all KNOWN or FLAKY (agent archive/lookup and provider-drain), and the verdict is no_new_failures. That evidence was noted on active epic sase-1t3.6.1, where sase-1t3.6.1.2 already proposed them.

The land phase's missing chaos checkpoint inventory and exemptions were recorded on sase-1t2.13.

FOLLOW-UP TRIAGE:
- sase-1t2.8.1.1 clippy needless_bool: duplicate, corroborated via +1 on sase-1t1.
- sase-1t2.8.1.3/.4/.5/.6 symvision reset_lower_macros_cache/reset_project_identity_caches: declined, resolved upstream by ac19f907ae, which deleted both helpers.
- sase-1t2.8.1.6 #2:
  - fakey hijack e2e: epic-caused, fixed here.
  - gate_turn test_creator_origin_retention: declined, fixed upstream by f8c2763ae3 (fixture TTL), 3/3 pass.
- sase-1t2.8.1.7 stale sase-1t3.6.1.2 epic-symbol rows: declined, removed upstream by e1d81ee6c6.
- Discovered during landing: the finalizer provenance_id exceeds the 160-byte core bound on long config paths, which breaks the finalizer canaries under raw pytest with the long agent TMPDIR (the governed run_pytest TMPDIR passes 4/4). Filed as sase-1t4 (bug, small).

No --epic-symbol entries remain.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.8.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.8.1.land/README.md) | [sase-1t2.8.1](sase-1t2.8.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`81dfe57`](https://github.com/sase-org/sase/commit/81dfe5710ea123542f9426a1abafe7bd01c17bbb) | fix(ace): tolerate duck-typed rows when mirroring hijack overlays | [sase-1t2.8.1](sase-1t2.8.1.md) | 2026-11-16 15:19:07 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:ef][1] | Check child-epic progress for cross-epic conflict report | 1 |
| read-by | [agent:sase-1t2.8.1.1][2] | Need the parent epic decisions and implementation context | 1 |
| read-by | [agent:sase-1t2.8.1.4][3] | Need parent epic decisions for the assigned owner-recovery phase | 2 |
| read-by | [agent:sase-1t2.8.1.5][4] | Need parent epic DECISIONS and phase status | 2 |
| read-by | [agent:sase-1t2.8.1.7][5] | Need the epic's DECISIONS and named requirements before implementing the phase | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ef/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.8.1.1/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.8.1.4/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.8.1.5/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.8.1.7/README.md

<!-- sase:referenced-by:end -->
