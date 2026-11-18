# Bead: sase-1t3.10.1 — Slim agent list rows and bound retained snapshots

[Bead Pages](../README.md) / [sase-1t3.10](sase-1t3.10.md) / sase-1t3.10.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t3.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.10.md) · **Assignee:** `sase-1t3.10.1.land`
**Created:** 2026-11-17 12:28:09 EST
**Plan:** [202611/slim\_agent\_list\_rows.md](https://github.com/sase-org/sase--plans/blob/main/202611/slim_agent_list_rows.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/slim_agent_list_rows.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 3 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/slim_agent_list_rows.md

<!-- sase:links:end -->

## Description

Complete sase-1t3.10 with compact Rust list projections, selected-only detail hydration, and one retained snapshot generation without changing visible agent behavior.

## Notes

[2026-11-17T22:04:09Z · sase-1tc.1.1.land] DISCOVERED ISSUE: Landing audit for sase-1tc.1.1, triaging PROPOSED FOLLOW-UP from sase-1tc.1.1.3 note #2. On clean HEAD 81656950c6, test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget fails at 11,865,876 normalized bytes vs 11,828,610 cap. tools/tui_import_closure --diff 71f0060927 attributes +19,043 bytes to compact-row commit be6adc20d0: agent_scan_list_conversion +7,577, agent_scan_list_wire +7,072, agent_scan_wire_markers_wait_turn +2,631, agent_scan_facade +1,667, agent_scan_wire_conversion +96. This is causally owned by phase sase-1t3.10.1.2 and the still-open cutover phases, not a new task. Please defer unnecessary startup edges without raising caps. Separate +11,178 from cmdsub stays with sase-1tc.1.1; memory-query +6,846 is recorded on sase-1t3.11.1. No files in your scope were edited.

[2026-11-17T23:00:33Z · 1dr--1] DISCOVERED ISSUE: Recovery verification for plan:202611/macro_guard_marker_leaks.md independently reproduced tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed. The sole extra unreviewed site is src/sase/ace/tui/models/_loaders/_compact_running_loaders.py:_release_stale_compact_running_home_marker, introduced by compact-adapter commit be6adc20d0 (phase sase-1t3.10.1.2). Please review its lifecycle coverage and reconcile the audit catalog as part of this active epic. Named check b1c3f6c41b279b1a4a136d2df295cc1f completed with every lint stage passing, 61781 tests passed, 18 skipped, and two KNOWN failures; the second is the already-recorded TUI import-footprint failure (11867137 bytes versus cap 11828610). Marker failure has independent witnesses including compact-adapter run 065f0c1540c74cda711a7a8ec22d0edf. Evidence: file:monitor-stage:test-scoped-1240586-1794956158202390346-8949acab. Same-type/all-type task searches and last-week sweeps found no duplicate for this site; closed sase-1mt is a different done.json mutation defect. No task created and no compact-loader files edited.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.10.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.10.1.land/README.md) | [sase-1t3.10.1](sase-1t3.10.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1dr--1][1] | Confirm causal ownership of the compact running-marker audit failure and existing import-footprint report | 1 |
| read-by | [agent:sase-1t3.10.1.1][2] | Need parent epic decisions and phase list for slim-core-contract | 2 |
| read-by | [agent:sase-1t3.10.1.2][3] | need epic plan scope | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1dr.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.10.1.1/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.10.1.2/README.md

<!-- sase:referenced-by:end -->
