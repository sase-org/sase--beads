# Bead: sase-1ab.10.2 — Rename-stale tests and CLI contracts

[Bead Pages](../README.md) / [sase-1ab.10](sase-1ab.10.md) / sase-1ab.10.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ab.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.land.md) · **Assignee:** `sase-1ab.10.2` · **Size:** medium
**Created:** 2026-09-27 08:44:28 EDT · **Closed:** 2026-09-27 09:11:14 EDT
**Plan:** [202609/sase\_turn\_rename\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_turn_rename_finish.md)

## Description

test-repair: bring the 24 deterministic rename-stale test nodes to the turn and named-proc contracts, refresh the completion spec, caption the turn completion slots, and make the proc_wire_schema_version lookup optional so the pinned bindings check passes against the published core.

## Notes

[2026-09-27T13:04:00Z · sase-1ab.10.2] PROPOSED FOLLOW-UP: kind_coverage still fails on tool/receipt slots owned by sase-1ah; turn slots fixed here

[2026-09-27T13:04:11Z · sase-1ab.10.2] PROPOSED FOLLOW-UP: bindings gate still missing 11 pre-flip/other-epic bindings (2 turn bindings await sase-1ab.10.3 core-flip/pin-bump; 3 tool_run_receipt owned by sase-1ah; project_finalizer_node_view owned by sase-1b2; 5 prompt-stash trash bindings owned by their epic); proc_wire_schema_version made optional here

[2026-09-27T13:10:47Z · sase-1ab.10.2] PROPOSED FOLLOW-UP: just check symvision flags private _mapping in src/sase/core/finalizer_run_view.py (untouched by this phase; likely sase-1b2 or sase-1ay symvision backlog)

[2026-09-27T13:11:14Z · sase-1ab.10.2] 22/24 listed nodes pass; turn slots captioned, snapshot refreshed, proc_wire_schema_version optional with mirror fallback. Verified: 146 tests pass across all touched areas plus contract/terminology suites; ruff/mypy/fmt gates green. Remainders are foreign-owned (recorded as PROPOSED FOLLOW-UP notes): kind_coverage tool/receipt slots (sase-1ah), symvision _mapping in finalizer_run_view.py (sase-1b2/sase-1ay). No epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-1ab.10.3](sase-1ab.10.3.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1ab.10.5](sase-1ab.10.5.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ab.10.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ab.10.2/README.md) | [sase-1ab.10.2](sase-1ab.10.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`46c7e68`](https://github.com/sase-org/sase/commit/46c7e68a8050978bd9c8aa8a3c4bca7193a9bb2e) | fix(turn-rename): repair rename-stale tests and CLI contracts | [sase-1ab.10.2](sase-1ab.10.2.md) | 2026-09-27 09:13:36 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ab.10.2][1] | Need full description and notes | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ab.10.2/README.md

<!-- sase:referenced-by:end -->
