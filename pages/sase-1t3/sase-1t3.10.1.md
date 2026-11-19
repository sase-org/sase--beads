# Bead: sase-1t3.10.1 — Slim agent list rows and bound retained snapshots

[Bead Pages](../README.md) / [sase-1t3.10](sase-1t3.10.md) / sase-1t3.10.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t3.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.10.md) · **Assignee:** `sase-1t3.10.1.land`
**Created:** 2026-11-17 12:28:09 EST · **Closed:** 2026-11-18 15:29:04 EST
**Plan:** [202611/slim\_agent\_list\_rows.md](https://github.com/sase-org/sase--plans/blob/main/202611/slim_agent_list_rows.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/slim_agent_list_rows.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | [bead:sase-1ti][2] | Proposed by phase .1 note #2; independent older full-scanner omissions share compact projection files with the landing repair, so workers should reuse newer changes. |
| related | file:explicit:390183b0f5d7c729aaa2f505 | attached via sase artifact create --bead |
| related | file:explicit:b20e7bc07e4622a2fb08abb5 | attached via sase artifact create --bead |

_Plus 6 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/slim_agent_list_rows.md
[2]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1ti/README.md

<!-- sase:links:end -->

## Description

Complete sase-1t3.10 with compact Rust list projections, selected-only detail hydration, and one retained snapshot generation without changing visible agent behavior.

## Notes

[2026-11-17T22:04:09Z · sase-1tc.1.1.land] DISCOVERED ISSUE: Landing audit for sase-1tc.1.1, triaging PROPOSED FOLLOW-UP from sase-1tc.1.1.3 note #2. On clean HEAD 81656950c6, test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget fails at 11,865,876 normalized bytes vs 11,828,610 cap. tools/tui_import_closure --diff 71f0060927 attributes +19,043 bytes to compact-row commit be6adc20d0: agent_scan_list_conversion +7,577, agent_scan_list_wire +7,072, agent_scan_wire_markers_wait_turn +2,631, agent_scan_facade +1,667, agent_scan_wire_conversion +96. This is causally owned by phase sase-1t3.10.1.2 and the still-open cutover phases, not a new task. Please defer unnecessary startup edges without raising caps. Separate +11,178 from cmdsub stays with sase-1tc.1.1; memory-query +6,846 is recorded on sase-1t3.11.1. No files in your scope were edited.

[2026-11-17T23:00:33Z · 1dr--1] DISCOVERED ISSUE: Recovery verification for plan:202611/macro_guard_marker_leaks.md independently reproduced tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed. The sole extra unreviewed site is src/sase/ace/tui/models/_loaders/_compact_running_loaders.py:_release_stale_compact_running_home_marker, introduced by compact-adapter commit be6adc20d0 (phase sase-1t3.10.1.2). Please review its lifecycle coverage and reconcile the audit catalog as part of this active epic. Named check b1c3f6c41b279b1a4a136d2df295cc1f completed with every lint stage passing, 61781 tests passed, 18 skipped, and two KNOWN failures; the second is the already-recorded TUI import-footprint failure (11867137 bytes versus cap 11828610). Marker failure has independent witnesses including compact-adapter run 065f0c1540c74cda711a7a8ec22d0edf. Evidence: file:monitor-stage:test-scoped-1240586-1794956158202390346-8949acab. Same-type/all-type task searches and last-week sweeps found no duplicate for this site; closed sase-1mt is a different done.json mutation defect. No task created and no compact-loader files edited.

[2026-11-18T16:21:39Z · sase-1t3.10.1.land] LANDER FOLLOW-UP TRIAGE (2026-11-18): Reviewed every note on all four child phases. (1) sase-1t3.10.1.1 note #2: independently reproduced missing held_by/hold_expires_at/status_bucket in the full Rust scanner; these fields were already absent before core 8cedd45d. Filed sized medium bug sase-1ti after same-type/all-type/all-status searches, last-week sweep, and active-epic causal review. This is independent pre-existing full-scan parity work, not a reason to enlarge this landing. (2) sase-1t3.10.1.3 note #1: declined a new MemoryAuditRow task because cd0b9c5273 already privatized it as _MemoryAuditRow, with all callers in its defining file; verified source and commit. (3) sase-1t3.10.1.3 note #2: declined deferral to a future task because compact projection introduced the supervisor_identity loss; real binding returns full supervisor boot:9 but compact process_identity boot:1 and monitor={exit_code:null}. The Python workaround caches whole agent_meta.json dictionaries through _json_cache, violating this epics retained-compact contract. Include core-side precedence and removal of that workaround in the remaining-work tale. Existing sase-1qr fixed generic process_identity before this epic and is not a duplicate. No other PROPOSED FOLLOW-UP notes were present.

[2026-11-18T16:25:07Z · sase-1t3.10.1.land] LANDING AUDIT: At sase fbc1e34fbc reviewed core 8cedd45d and Python be6adc20d0/8fa9c1ad8b/fbc1e34fbc, all four child scopes and every note, inherited decisions, and the linked child/outer plans. Core pin 71c59dca contains 8cedd45d. Production cached/revalidated/fallback/full-history/live-plan/delta acquisition uses compact DTOs and constructors; core selection/order/completeness are reused; marker lifecycle audit coverage is present. Follow-up outcomes are in the preceding triage note. Completion is blocked by actual detail ownership gaps: 20 hydrated replacement objects with one logical identity retain 20 raw payloads (1.9MB) while owner size is 1; both copy_agent_graph and copy_agent_rows_relinked retain unmanaged full detail after the original is released (owner size 0); selected-detail workers mutate/register before post-await identity checks and do not verify replacement object/version; a delayed cache window-25 result overwrites the newer window-50 result (binding calls [25,50,50]); monitor supervisor identity is lost in the compact wire and recovered by caching full metadata JSON. Reproduction script: file:explicit:390183b0f5d7c729aaa2f505. Preparing medium tale sase_plan_slim_list_landing_repairs.md, whose final step closes this epic and parent phase sase-1t3.10 without waiting for its own commit. This turn removes four unused epic-symbol exemptions ahead of that tale because the close guard unions upstream rows; production bounded APIs remain. No source retention fix is claimed yet.

[2026-11-18T16:25:32Z · sase-1t3.10.1.land] POST-START INTEGRATION REVIEW: Reviewed sase commits from the first core-contract commit time (2026-11-17 13:49 EST), including 8a6451068e/f2fb7fb6b5 before be6adc20d0 and all later default-branch commits through fbc1e34fbc; local master had no missing origin/master commits at review. No later core agent_scan changes followed 8cedd45d. dd56fe2075 replaced the broad import-baseline bump with attributed growth and deferred unnecessary edges; preserve its current cap and verify the import test. cd0b9c5273 already resolved MemoryAuditRow. 81e124eca8 added bounded-cache census consumers after this epic started: the remaining tale integrates the separate full snapshot cache and detail owner into that census so telemetry cannot conceal them. New artifact-read/bead-query caches remain independently bounded; viewer, chop-recovery, and forced-name-reuse commits introduce no compact-row consumers to switch. Destructive name-wipe scanning needs full authoritative owner/link payloads and must keep its existing path. The repair tale will recheck drift at closeout.

[2026-11-18T16:26:57Z · sase-1t3.10.1.land] VERIFICATION CHECKPOINT: Integration cleanup passes 38 focused tests across compact list wires/ordinary rows/workflows, real Rust parity, selected-detail retention, and marker mutation/path audits (33.11s). This confirms the old compact-running marker audit finding is addressed. Standalone same-identity/copy/monitor reproduction results are file:explicit:b20e7bc07e4622a2fb08abb5. Required just check is ToolRun 6b3ba7450a20b7f13a341f55e64a1f40, still rebuilding the automatically refreshed local Rust extension; it has not passed yet. Repair tale validated with --explain, corrected title/goal metadata, then revalidated successfully with zero warnings. Epic and parent phase remain open until the tale implements the reproduced ownership fixes.

[2026-11-18T16:28:17Z · sase-1t3.10.1.land] ADDITIONAL CONTRACT EVIDENCE: project_output_facts in sase-core clones every meta_* value, including meta_commits that phase .1 explicitly listed as deferred. A real scan_agent_artifact_dir_list call with done.step_output.meta_details={_raw:100000 x characters} and meta_commits=[{diff:100000 y characters}] retains both full nested payloads in the compact result. Compact done construction can additionally backfill the full commit list through enrich_missing_commit_metadata. The remaining tale includes bounded typed list/action facts, selected-detail restoration for arbitrary metadata, and no commit-list backfill on compact construction. This is another gap in the original compact-payload invariant, not an unrelated feature request.

[2026-11-18T17:55:26Z · sase-1t3.10.1.land] LANDER FINAL VERIFICATION AND DRIFT: 38 focused compact wire/row/workflow/retention/marker tests passed. Required just check ToolRun 6b3ba7450a20b7f13a341f55e64a1f40 exited 1: every lint/validation stage including Symvision passed, then the expanded nonvisual suite reported 61918 passed, 18 skipped and four cancellation failures. All four reproduced serially (4 failed in 6.77s), evidence file:explicit:5a1946d926ef97e2b7ce4d60. They paired primary fbc1e34fbc with newly built linked core 98a22b79. Fresh upstream review through 43ef590bb6 found companion 4e5c1b9730 already updates all four exact assertions and pins that core revision; do not reverse the intended skipped/cancelled and crossing-launch settlement semantics. Via /sase_new_task, corroborated existing tasks sase-1tl and sase-1tm and recorded the causal diagnosis on active epic sase-1tc.3.1.6; no new tasks. Reviewed six post-audit upstream commits (chop recovery/contract, repository-integration split, finalizer visibility, TUI update wait notices, cmdsub docs): no additional compact consumers or changes to remaining repair boundaries. The four local epic-symbol exemptions are removed and git diff --check is clean; upstream-only exemptions disappear when this lander cleanup commits. Epic remains open for the documented retention/compact-contract/cache defects. A validated medium tale will implement only that remaining work and finish this epic plus parent phase sase-1t3.10 in its own coding turn.

[2026-11-18T20:29:04Z · sase-1t3.10.1.land--1] LANDING CLOSEOUT 2026-11-18: compact list and bounded retention scope is complete. Primary just check ToolRun 4bd12aac194f3924f3fc6b2cc899973d passed with exit 0, including scoped tests. Linked core ToolRun 3d6acab87f4dfae7c457a427680ac5aa passed with exit 0 after updating a stale fixture that expected arbitrary meta_keep to survive; its final triage verdict is pass. The earlier core run 58c91f6c9c3126f8776dd196a6fe8c01 exposed that assertion; the repaired fixtures preserve meta_patch and prove prompt/workflow metadata stays deferred. Core check retained a non-failing baseline-file lookup diagnostic. Separate Python process smoke used the real Tier-1 index: 605 compact rows among 641 rows, selected detail hydrated and released, 4.233 s, and detail owner size 0 after release. The index change

… and 1133 more characters

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.10.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.10.1.land.md) | [sase-1t3.10.1](sase-1t3.10.1.md) | 4 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fbfaf07`](https://github.com/sase-org/sase/commit/fbfaf07123b790738caf0bf203b3f3d3711aa374) | refactor(agent-scan): retire unused compact-list landing APIs | [sase-1t3.10.1](sase-1t3.10.1.md) | 2026-11-18 12:57:07 EST |
| sase-core | [`sase-core@9a87b5b`](https://github.com/sase-org/sase-core/commit/9a87b5bd86d2c1336fe18dbf413b49e5906e304d) | feat(agent-scan): preserve monitor identity in compact rows | [sase-1t3.10.1](sase-1t3.10.1.md) | 2026-11-18 15:54:55 EST |
| sase | [`af07b78`](https://github.com/sase-org/sase/commit/af07b78ac22bc55f394b6dc576e88fac5dd9573c) | feat(tui): bound compact agent list retention | [sase-1t3.10.1](sase-1t3.10.1.md) | 2026-11-18 15:56:49 EST |
| sase--plans | [`sase--plans@1a357e7`](https://github.com/sase-org/sase--plans/commit/1a357e734ad84c76948a0c72b4719cf9a8615c80) | docs(plan): mark slim agent list rows complete | [sase-1t3.10.1](sase-1t3.10.1.md) | 2026-11-18 15:58:16 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1dr--1][1] | Confirm causal ownership of the compact running-marker audit failure and existing import-footprint report | 1 |
| read-by | [agent:sase-1t3.10.1.1][2] | Need parent epic decisions and phase list for slim-core-contract | 2 |
| read-by | [agent:sase-1t3.10.1.2][3] | need epic plan scope | 1 |
| read-by | [agent:sase-1t3.10.1.3--1][4] | check parent epic status for re-key | 1 |
| read-by | [agent:sase-1t3.10.1.land][5] | Need the epic scope, children, and linked plan file | 1 |
| read-by | [agent:sase-1t3.10.1.land--1][5] | Review the landing phase requirements and its current notes before closing it | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1dr.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.10.1.1/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.10.1.2/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.10.1.3.md
[5]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.10.1.land.md

<!-- sase:referenced-by:end -->
