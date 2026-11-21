# Bead: sase-1tz.4.1 — Gateway checkpoint fix, notification hygiene, and retention sweep (items 11-13)

[Bead Pages](../README.md) / [sase-1tz.4](sase-1tz.4.md) / sase-1tz.4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.4.md) · **Assignee:** `sase-1tz.4.1.land`
**Created:** 2026-11-20 14:00:21 EST · **Closed:** 2026-11-21 07:38:20 EST
**Plan:** [202611/hygiene\_gateway\_notifications\_retention.md](https://github.com/sase-org/sase--plans/blob/main/202611/hygiene_gateway_notifications_retention.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/hygiene_gateway_notifications_retention.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 6 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/hygiene_gateway_notifications_retention.md

<!-- sase:links:end -->

## Description

A busy SQLite WAL checkpoint reports busy instead of erroring, read paths checkpoint passively, and the gateway serves a cached fleet snapshot at once while one rebuild runs in the background. remote-attention keeps one row per request, wait_checks raises one notice per failed root blocker with a one-key expire action, and task-bead triage keeps one notification per bead. Settled triage gate bundles are reaped. Notification payloads over 8 KB move to sidecar files, and broken file references are pruned. file-hooks successes are silent, workspace-rescue dedups, prune nudges have a size floor, agent_state_refresh logs each unchanged verdict once, and no-op claim-ledger rows stop. Tool-run logs, tui.log, proc log locks, registry temp files, and index backups follow stated horizons.

## Notes

[2026-11-20T22:57:26Z · sase-1uj.land] DISCOVERED ISSUE: Proposed by sase-1uj.1 note #2, reproduced by sase-1uj.land on clean 7e590921e3: tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed has one extra site, src/sase/scripts/_bead_task_triage_gates.py:reap_settled_bundles. git blame identifies phase sase-1tz.4.1.9 commit 1115db9e66. Review the operation and register its existing coverage in the audit fixture as part of your landing; no unrelated task created. Also recorded on parent sase-1tz.

[2026-11-21T12:37:58Z · sase-1tz.4.1.land] FOLLOW-UP TRIAGE (land agent): every PROPOSED FOLLOW-UP from the child phases and what happened to it.
- New task sase-1ul (bug, medium), from .3 #2: remote-attention dismissals are lost once compaction archives the row.
- New task sase-1ur (small), from .3 #3: delete the legacy per-revision migration after the post-install census. It needs live state the epic could not observe.
- New task sase-1uo (flake), from .3 #5: test_volume_smoke_12500. The KNOWN pager test in the same note already has a witness.
- New task sase-1uq (medium), from .6 #3: a sase-core MarkUnread state update.
- New task sase-1um (bug, medium), from .8 #6: the triage fingerprint omits created_by, closed_at, and task_type_fields.
- New task sase-1up (flake), from .10 #2: test_run_configured_chop_once_records_unresolved_secret_as_check_error.
- New task sase-1un (bug, small), from .10 #6: the after-rebase import gate counts .venv files as dirty.
- +1 on sase-1uk, from .10 #4: continuation-ancestry retention, a 92dc6274e5 regression. It still fails on 39b594a30c.
- +1 on sase-1ug, from .5 #5: the sase-telegram tag-catalog fixture errors.
Declined:
- Completion-snapshot drift (.2 #2, .3 #4, .4 #1, .6 #4, .7 #3, .8 #5, .11 #2, .12 #3): resolved. 335170e1cb resynced cli_spec.json, and tests/completion/test_snapshot.py passes on 39b594a30c.
- reap_settled_bundles audit site (epic note #1, .5 #2, .10 #5): resolved. 3ea7133de2 registered it in tests/test_agent_artifact_directory_operation_audit.py with an exemption matching the code (owned settled bundles, under the creation lock, symlink-safe), and the test passes.
- Stale disk-inventory wire (.13 #3): resolved. The pin 6524f378 is sase-core origin/master and contains wire 2, and tests/core/test_disk_footprint_inventory.py passes.
- Durable Athena gateway log (.2 #1): athena's gateway runs but has written 0 bytes since 2026-09-20 because no fleet traffic reaches it (apollo is the rendezvous host), so there is nothing to measure there.

[2026-11-21T12:38:20Z · sase-1tz.4.1.land] LANDED. Verified all 13 phases closed and every child note addressed against the plan, the DECISIONS, and the code at sase 39b594a30c (origin/master).
Commits:
- sase: 2b18880ef1, 0386c59150, bca49eadd1, 18e4f35a54, f960f758ca, 1115db9e66, eb5401709d, 8f5ed08088, 3025de0572, 6b444fcdef, 335170e1cb, 88d36297cc, 39b594a30c.
- sase-core: 553387d3 (wal_busy), a3b95da5 (gateway_swr), 2c33360a (attention_key), 6524f378 (blob_store). All are in the pin 6524f378 = sase-core origin/master.
- sase-telegram: bffd4f6, on origin/master.
- chezmoi: 058b195b on origin/master removes only quiet-task-beads (quiet_triage_rule=remove). athena's quiet-task-beads-telegram stays.
DECISIONS: index_backups=report is a report-only agent_index_backups row and nothing auto-deletes. The one-time athena 212 MiB delete ran through gate custom-a71ace61.
Code spot checks:
- busy -1 reads as checkpoint_busy, the gateway hook runs PASSIVE after waiters wake, and busy checkpoints log at info.
- Stale-while-revalidate with a 5-minute bound and bounded permit waits.
- Stable remote-attention key with resurface on a new revision.
- Opt-in sidecars, externalized over 8 KiB, with readers resolving them.
- Root-blocker notices, plus the ExpireWaiters action on Enter with no auto-expiry.
- One-row triage adoption, kind-scoped fingerprint, request_id_conflict branch kept.
- Sticky dismissal-cancel, and reaping of settled bundles older than 30 days, capped at 100 per pass.
- Silent file-hook success rows, rescue dedup keys, run_prune_notify_min_bytes floor of 1 GiB, no-op holds skipped.
- Verdict memo.
- Hourly state_retention chop, tui.log age rotation, lock and registry-tmp sweeps.
- New config keys appear in default_config.yml, the schema, and the docs.
Tests: 286 focused epic tests pass on 39b594a30c, and the audit test passes. Phase .5's `sase tool run check` e09f2dea passed all stages, exit 0, on the combined tree (cd7c9f85c4 plus the 39b594a30c changes).
Integration: reviewed the 10 non-epic commits since the epic started:
- 1536c40a0b and cd7c9f85c4 refresh docs consistently with the epic's notification-storage and housekeeping behavior.
- 3ea7133de2 splits the triage chop and registers reap_settled_bundles in the audit; the triage and gate_reconcile tests pass.
- 0dc8cc1cc6, 770561bf9b, and 6fb94163ae are behavior-preserving test and module splits.
- 92dc6274e5 regressed continuation-ancestry retention. That is not caused by the epic and is tracked by sase-1uk, which got a +1.
- 815afd1406 and 7e590921e3 are unrelated.
- Phase .5 (07:22 today) re-audited every action_data and note reader on top of all of them.
No integration edits were needed.
Bookkeeping filled at landing:
- wal_busy before-measurement and after-install command added to sase-1tz.4.1.1. The phase had none.
- Missing wal_busy, gateway_swr, and gate_reconcile summaries added to sase-1tz.4.
- log_horizons and clutter_reapers overlap note added to sase-zw.8.
- The relationship notes on sase-1s5 (#2) and sase-1s5.3 (#8) were already present.
Accepted deviation: the maintenance TRUNCATE path still discards its checkpoint result rather than logging it. sase_core has no logging dependency, and busy is now an Ok outcome, so the F11 failure mode is gone.
No --epic-symbol entries. Follow-up triage is in epic note #2.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.4.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.land/README.md) | [sase-1tz.4.1](sase-1tz.4.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@905527e`](https://github.com/sase-org/sase--plans/commit/905527e9b5547071c1561588eae850ddba38124f) | chore(plans): mark hygiene\_gateway\_notifications\_retention done | [sase-1tz.4.1](sase-1tz.4.1.md) | 2026-11-21 07:40:09 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.4.1.12][1] | Need parent epic scope and sibling phases | 1 |
| read-by | [agent:sase-1tz.4.1.5][2] | Check the parent epic note for this known artifact-directory audit follow-up | 1 |
| read-by | [agent:sase-1tz.4.1.6][3] | See epic phase statuses and notes for coordination | 1 |
| read-by | [agent:sase-1tz.4.1.7][4] | Need parent epic scope, DECISIONS, and remaining phases | 1 |
| read-by | [agent:sase-1uj.land][5] | Need owner of reap_settled_bundles audit-site failure proposed by sase-1uj.1 | 1 |
| read-by | [agent:toobig-ae.agent_artifact_run_retention.0][6] | Check whether the continuation ancestry retention failure belongs on the retention sweep or false-red backlog epic | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.12/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.5/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.6/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.7/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1uj.land/README.md
[6]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-ae.agent_artifact_run_retention.0/README.md

<!-- sase:referenced-by:end -->
