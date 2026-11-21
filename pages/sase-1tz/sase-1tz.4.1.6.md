# Bead: sase-1tz.4.1.6 — Raise one wait\_checks notice per failed root blocker and freeze its +1s

[Bead Pages](../README.md) / [sase-1tz.4.1](sase-1tz.4.1.md) / sase-1tz.4.1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.4.md) · **Assignee:** `sase-1tz.4.1.6` · **Size:** medium
**Created:** 2026-11-20 14:00:23 EST · **Closed:** 2026-11-20 15:38:39 EST
**Plan:** [202611/hygiene\_gateway\_notifications\_retention.md](https://github.com/sase-org/sase--plans/blob/main/202611/hygiene_gateway_notifications_retention.md)

## Description

wait_blocker: terminally blocked waiters group under one notice per root blocker that names every direct and transitive waiter. The notice changes only when its waiter set changes and never +1s otherwise. Legacy per-waiter rows settle once.

## Notes

[2026-11-20T20:37:31Z · sase-1tz.4.1.6] MEASURE (before, read-only, 2026-11-20 ~15:20 EST, live notifications.jsonl): athena rows=430 undismissed=410 plus_ones=117652 legacy_per_waiter(wait_checks:terminal-blocked:*)=418 legacy_undismissed=409 legacy_plus_ones=115862 root(wait_checks:terminal-blocker:*)=0; 'can never self-resolve' rows=418 (409 undismissed). apollo rows=65 undismissed=59 plus_ones=9421 legacy=61 legacy_undismissed=59 legacy_plus_ones=8906 root=0; 'can never self-resolve' rows=61 (59 undismissed). Archive (all-time extra): athena 54 legacy rows/5526 +1s, apollo 22/2932. Expected after install: legacy_undismissed -> 0 on the first wait_checks tick (each settles once with wait_checks_auto_dismissed=true), root rows = number of live failed root blockers, root_plus_ones stays ~0 across ticks. Repeat on each host (athena locally; apollo via: ssh apollo '<cmd>'): python3 -I -c 'import json,os;r=[json.loads(l) for l in open(os.path.expanduser("~/.sase/notifications/notifications.jsonl")) if "wait_checks" in l];r=[x for x in r if x.get("sender")=="wait_checks"];k=lambda p:[x for x in r if (x.get("dedup_key") or "").startswith(p)];u=lambda xs:sum(not x.get("dismissed") for x in xs);P=lambda xs:sum(len(x.get("plus_ones") or [])+int(x.get("plus_ones_dropped") or 0) for x in xs);L=k("wait_checks:terminal-blocked:");R=k("wait_checks:terminal-blocker:");print("rows=%d undismissed=%d plus_ones=%d legacy=%d legacy_undismissed=%d legacy_plus_ones=%d root=%d root_undismissed=%d root_plus_ones=%d"%(len(r),u(r),P(r),len(L),u(L),P(L),len(R),u(R),P(R)))'

[2026-11-20T20:37:57Z · sase-1tz.4.1.6] CONTRACT for waiter_expire (sase-1tz.4.1.7): root notices are sender=wait_checks, dedup_key 'wait_checks:terminal-blocker:{blocker artifact_dir}' (ROOT_BLOCKER_DEDUP_PREFIX in src/sase/scripts/_chop_wait_checks_root_notice.py), action=None today. action_data (all strings): blocker_artifact_dir, blocker_outcome, blocker_dependency, blocker_name ('' when unknown), waiter_count, waiters = JSON list of {artifact_dir, name, project[, via=upstream waiter artifact_dir]} (direct waiters have no via), and wait_checks_auto_dismissed='true' only while the job settled the row (AUTO_DISMISSED_ACTION_DATA_KEY; reconcile_notification_rows reversible marker). The job settles the row itself once every waiter is gone, so the expire action may simply expire waiters and dismiss; the next tick reconciles. Adding an action/action_data keys must go through _build_root_blocker_notification so _same_content keeps unchanged passes write-free.

[2026-11-20T20:38:13Z · sase-1tz.4.1.6] PROPOSED FOLLOW-UP: Add a mark_unread state update to the sase-core notification store — wait_checks' root notice flips read->unread when a waiter joins via two reconcile writes (dismiss with the reversible marker, then resurface), because NotificationStateUpdateWire has no MarkUnread and reconcile keeps read from disk; a core primitive would make it one atomic write (src/sase/scripts/_chop_wait_checks_root_notice.py flip_rows).

[2026-11-20T20:38:19Z · sase-1tz.4.1.6] PROPOSED FOLLOW-UP: tests/completion/test_snapshot.py (test_checked_in_snapshot_has_no_drift, test_current_structural_view_matches_checked_in_snapshot) fail on clean master f6b4344d87 — 'sase CLI completion spec is out of sync with the argparse tree'; reproduced identically with this phase's changes stashed; sase tool run triage labels it KNOWN (witness 004ecc862e32316588e888ef0cc4dd20, no owner bead found). Regenerate the checked-in completion snapshot.

[2026-11-20T20:38:39Z · sase-1tz.4.1.6] wait_checks raises one notice per failed root blocker (dedup wait_checks:terminal-blocker:{root dir}) naming direct + transitive waiters with a count; waiter list in action_data. Transitive edges come from new WaitDependencyIndex.pending_blocking_members_for_name/hood (same latest-unresolved-entity selection as terminal_blocking_artifacts_*), walk is depth-bounded (32) with a visited set. Unchanged passes write nothing (file bytes+mtime verified), changed sets refresh in place via reconcile_notification_rows (no +1), unread only on join; all-gone settles with reversible wait_checks_auto_dismissed marker and resurfaces unread on return; user dismissals hold; fail-open waiters stay listed; legacy per-waiter rows settle once. Tests: new tests/test_axe_chop_wait_checks_root_blockers.py (13 cases incl. N->1 row, transitive, repeat no-write, join, leave, settle/resurface, user dismissal, legacy settle, cycles, depth bound, fail-open) + updated terminal_outcomes keys; mutation-checked transitive/cycle tests. sase tool run check: all lint gates pass; full suite 62495 passed, only 2 KNOWN tests/completion/test_snapshot.py failures that reproduce on clean base (PROPOSED FOLLOW-UP recorded). Docs: notification-types.md + directive-launch.md. Before-numbers + repeat command recorded as notes.

## Dependencies

- **Blocks:** [sase-1tz.4.1.7](sase-1tz.4.1.7.md) ✓ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.4.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.6/README.md) | [sase-1tz.4.1.6](sase-1tz.4.1.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bca49ea`](https://github.com/sase-org/sase/commit/bca49eadd11e70043e0fab05e140ee52a69fe35d) | feat(wait\_checks): raise one notice per failed root blocker and freeze its +1s | [sase-1tz.4.1.6](sase-1tz.4.1.6.md) | 2026-11-20 15:40:31 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.4.1.6][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1tz.4.1.7][2] | Need the root-blocker notice action_data contract from the prior phase | 1 |
| read-by | [agent:sase-1tz.4.1.land][3] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.6/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.7/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.land/README.md

<!-- sase:referenced-by:end -->
