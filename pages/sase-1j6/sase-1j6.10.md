# Bead: sase-1j6.10 — Finish update-skew agent auto-restart so it is safe and actually relaunches

[Bead Pages](../README.md) / [sase-1j6](README.md) / sase-1j6.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1j6.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1j6.land.md) · **Assignee:** `sase-1j6.10.land`
**Created:** 2026-10-10 08:09:05 EDT · **Closed:** 2026-10-10 15:19:46 EDT
**Plan:** [202610/finish\_update\_skew\_auto\_restart.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_update_skew_auto_restart.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/finish_update_skew_auto_restart.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 3 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/finish_update_skew_auto_restart.md

<!-- sase:links:end -->

## Description

Complete epic sase-1j6: the update-skew healer really relaunches pre-provider skew deaths once under the same name, touches nothing but skew-shaped failures, never spams or resurrects rows, records honest timestamps and provenance, keeps the episode report live, and leaves just check free of epic-caused failures.

## Notes

[2026-10-10T13:25:09Z · sase-1io.7.6.land] DISCOVERED ISSUE: v0.18.0 cannot publish while master imports auto-restart bindings that are not in the published sase-core-rs. PR 299 release-core-floor-smoke (job 114186958378, run 38043045593, 2026-10-10) failed check_sase_core_rs_bindings against floor 0.37.2, missing advance_auto_restart_ledger, agent_auto_restart_wire_schema_version, auto_restart_lineage_root, auto_restart_recovery_is_in_flight, claim_auto_restart_ledger, classify_agent_failure, and derive_auto_restart_episode. PyPI sase-core-rs is still 0.37.2. This is sase-1j6.10's core wire, not epic sase-1io.7.6. That epic will not edit the healer or cut a core release. Its ship waits until this epic has closed and a published core contains the bindings master imports. Full CI 38029274494 and Master Gate 38053026930 also failed auto-restart tests (including test_collect_journal_updates_bundle_window and test_default_config_matches_public_schema on spare_process_patterns). No duplicate task filed.

[2026-10-10T17:44:26Z · sase-1j6.10.land] LAND TRIAGE (sase-1j6.10.land, 2026-10-10) of every child PROPOSED FOLLOW-UP, checked on master e5e58ac3d5. DECLINED as resolved: (a) flag-lint rule 7 leftovers (10.1 #1, 10.3 #1, 10.4 #1 agents_unified_query; 10.5 #1 sase-1jc.7 flags; 10.7 #4 sase-1jc.8 flags): tools/check_feature_flags now exits 0. (b) unused ArtifactIndexProjection (10.1 #3, 10.6 #1, 10.7 #5): it is now private _ArtifactIndexProjection. (c) 10.1 #2 config-schema and timezone-guard failures: epic-caused and fixed by 1728f2bcd0; both tests pass. ROUTED: 10.7 #3 session_root_tab path-passing audit -> +1 sase-1by. 10.7 #6 test_node_finder_snapshot.py re-export ImportError (caused by sase-1jc's b46ecb0a94 rename) -> DISCOVERED ISSUE note on active epic sase-1jc. 10.7 #7 TUI import budget -> +1 sase-1ic for the 5 non-epic modules; the epic's own 4 modules (auto_restart, .constants, .ux, runner_lifecycle_phase) are remaining epic work. 10.7 #8 bob highlights --parent -> +1 sase-1jj. Epic note #1 (sase-1io.7.6.land, release floor): the bindings are in sase-core 31544120 and the pin; publishing them needs the open sase-core release-plz PR #325 (v0.38.0) merged by a human. No task filed: sase-1io.7.6 owns the ship wait.

[2026-10-10T17:46:49Z · sase-1j6.10.land] LAND VERIFICATION (sase-1j6.10.land, 2026-10-10, master e5e58ac3d5): NOT landable yet. Confirmed from source and CI: core-fixes is in sase-core 31544120 and the pin; probe-quiescence, the runner-ux lifecycle/config/test fixes, and healer-relaunch re-classify/provenance/env-scrub/ordering are met. Integration review of non-epic commits since the epic began (3513d91b1f, 68466146bf, 166289ac43, 18f53d3e57, 3ca1d2d153, b144f622cf) found nothing to update: RESTARTING buckets as Running through the new Rust status wrapper, and the Telegram rules don't touch auto-restart. Remaining epic-caused work: (1) CI: test_collect_journal_updates_bundle_window is TZ-dependent and fails under UTC; the episode_polish and episode_notify tests leak launched-*/failed-bead-* temp dirs (Master Gate 38067967749 test(3)/test(8)). (2) Deferrals never expire, because reclaim resets claimed_at. (3) A dead launching claim adopts the failed row as its replacement. (4) Orphaned deferred/stale ledger records keep the job actionable forever. (5) Retakes drop silenced, derive_episode, and the injected hooks. (6) The skip-rule, deferred_expired, execute_failed, launch_aborted, and wipe_reaches_others paths ignore quiet_declines or never surface silenced rows. (7) The files union is dropped because Python never sends refresh_files. (8) refresh_episode_rows' prefix match rewrites storm rows. (9) Fallback copy: 'sase update a sase update', 'Restarted 0 agents', 'unknown' key; the storm copy is off-spec. (10) The evidence v hint registers a directory, so the pager errors. (11) The epic's 4 modules stay in the TUI import closure (3519 vs cap 3513). (12) The firewall test misses managed_tmp_roots. (13) Literal glyphs remain, and tests have gaps. Planned as one medium tale that ends with this epic's closeout and the parent sase-1j6 landing. Declined reviewer findings: (a) scan-failure fallback to the history walk: a degraded path that still filters through is_healer_candidate. (b) Replacement branch skips the candidate pre-check: the spec makes any replacement second failure already_restarted. (c) Storm-paused declines are quiet even for silenced rows: per spec, the one storm escalation covers the episode. (d) finalize_loop records finalizing for non-handoff phases: correct for a death during finalization. (e) Unit tests in test_agent_auto_restart_episode_notify.py call refresh_episode_report/escalate_healer directly: they unit-test those functions, and the no-hand-call rule targets the end-to-end replay.

[2026-10-10T19:19:46Z · sase-1j6.10.land--1] TALE LAND_UPDATE_SKEW_AUTO_RESTART (2026-10-10): all plan sections 1-6 implemented and verified. Fixes: (1) TZ-independent journal-window test + temp-dir leaks routed via pytest tmp paths (scratch TMPDIR holds only pytest-of-bryan). (2) Healer: deferral expiry from lineage first claim; dead launching claims never adopt the failed row (ledger_key match + failed-dir reject); ledger-only orphans resolve row_gone/launch_aborted with next tick idle; retakes thread silenced+hooks via persisted extras; unified quiet_declines policy across skip-rule/deferred_expired/execute_failed/launch_aborted/wipe_reaches_others with already_restarted+storm loud; candidate pre-check exception-safe; doorbell project resolution matches scan; resurface stamp keyed by full path; at=timestamp_for on settle; dead branch removed; mtime-gated ledger cache for idle ticks PLUS writer-side invalidation (this turn: tmpfs freezes dir mtime on rewrites, so claim/store now clear the cache; regression test_cached_ledger_listing_sees_record_rewrites). (3) Notifications: refresh_files wire+reconcile path; episode refresh no longer clobbers storm rows; honest sase update NNN copy helper, no unknown keys/titles; exact storm copy; settlement-inside-healer refreshes report+rows with ledger-first Now cell; single _FAILED_REPLACEMENT_OUTCOMES definition; settlement test drives the tick. (4) TUI: epic 4 modules out of the import closure (count 3515; remaining +5 notification_gates.*+running_field._occupant owned by sase-1ic); evidence v hint registers files not dirs; firewall test drops PYTEST_VERSION and passes local_macros; UPDATE_RECOVERY_GLYPH everywhere; completion-test comment + lifecycle docstring nits. (5) Coverage: recent 429 row, probe module-name asserts, provenance from_rev/to_rev+culprit, incident replay via launched path with full row counts. (6) docs/agent_auto_restart.md updated, false claims removed. Tests: 153 passed TZ=UTC (all auto-restart suites + core + marker mutation audit), 67 passed TZ=America/New_York, new cache test fails on pre-fix code, ruff+mypy+fmt clean. Check: sase tool run 013f3490adb16a59ac06addbb055b788 (monitor ntdepwavd550 just check) red ONLY on items owned elsewhere, named here: sase-1by session_root_tab path audit (file renamed by base commit eff003d6a9); sase-1jc node-finder re-export + contract manifest; sase-1jj bob highlights dry run; sase-1ic import-budget remainder; flakes sase-1gh/sase-1jk/sase-1jl; sase-102 flag rule 7 (sase-1jc.9 closed the bead 18:22:47Z, its registry removal unmerged on this base); symvision __getattr__ in query_profile/profiles/__init__.py (sase-1jm.2.1.4 commit 18f53d3e57, identical error on pristine tree). TUI import count 3515 as predicted.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1j6.10.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1j6.10.land.md) | [sase-1j6.10](sase-1j6.10.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`20ddc1b`](https://github.com/sase-org/sase/commit/20ddc1b154de7a9bc40283f1c505d690d5c67410) | feat(auto-restart): fix update-skew auto-restart defects and land sase-1j6.10/sase-1j6 | [sase-1j6.10](sase-1j6.10.md) | 2026-10-10 15:40:23 EDT |
| sase--plans | [`sase--plans@4bee985`](https://github.com/sase-org/sase--plans/commit/4bee9857b5e72d66f02e02fbe3cbbab420f4db1f) | docs(plans): mark update-skew auto-restart plans done | [sase-1j6.10](sase-1j6.10.md) | 2026-10-10 15:44:50 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1j6.10.2][1] | Need parent epic decisions, sibling phases, and design context for core-fixes | 1 |
| read-by | [agent:sase-1j6.10.6][2] | parent epic scope | 1 |
| read-by | [agent:sase-1j6.10.land--1][3] | Plan closeout: need status, children, notes and plan path for epic sase-1j6.10 | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.10.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.10.6/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1j6.10.land.md

<!-- sase:referenced-by:end -->
