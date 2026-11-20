# Bead: sase-1tz.4.1.3 — Key remote-attention rows by stable request identity

[Bead Pages](../README.md) / [sase-1tz.4.1](sase-1tz.4.1.md) / sase-1tz.4.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.4.md) · **Assignee:** `sase-1tz.4.1.3` · **Size:** medium
**Created:** 2026-11-20 14:00:22 EST · **Closed:** 2026-11-20 15:34:09 EST
**Plan:** [202611/hygiene\_gateway\_notifications\_retention.md](https://github.com/sase-org/sase--plans/blob/main/202611/hygiene_gateway_notifications_retention.md)

## Description

attention_key: remote-attention rows key on (origin, request_id). A new revision updates and resurfaces the one row. An identical re-emission writes nothing. A local dismissal still sticks for its revision. Legacy per-revision rows migrate once.

## Notes

[2026-11-20T20:25:34Z · sase-1tz.4.1.3] MEASURE attention_key BEFORE (read-only, 2026-11-20, pre-install): athena live notifications.jsonl remote-attention rows=96 (undismissed=21; 75 auto-dismissed with marker, 0 user-dismissed), archive rows=1553; all-time raw=1649 rows over 1566 (origin,request_id) requests; 66 requests hold 148 rows across revisions (histogram: 1500 requests x1 revision, 50 x2, 16 x3); stable-key rows=0. One same-revision duplicate: id 23bf34b3-82d3-5d60-a9bf-f4e207c9172f appears twice in the archive (archived, recreated, re-dismissed). apollo: 0 remote-attention rows live or archived. AFTER-INSTALL (run on athena and via `ssh apollo`): N=~/.sase/notifications; for f in notifications.jsonl notifications-archive.jsonl; do printf "%s rows=%s undismissed=%s stable_key_rows=%s dup_request_groups=%s\n" "$f" "$(jq -c 'select(.sender=="remote-attention")' $N/$f | wc -l)" "$(jq -c 'select(.sender=="remote-attention" and (.dismissed|not))' $N/$f | wc -l)" "$(jq -r 'select(.sender=="remote-attention") | .dedup_key // ""' $N/$f | awk -F: 'NF==3' | wc -l)" "$(jq -r 'select(.sender=="remote-attention") | [.id, .action_data.remote_attention_origin_installation_id, .action_data.remote_attention_request_id] | @tsv' $N/$f | sort -u | cut -f2,3 | sort | uniq -d | wc -l)"; done. Expect: after the first TUI refresh post-install, live undismissed rows all have 3-field stable dedup keys, no live request gains a second row, and later revisions bump no row count.

[2026-11-20T20:26:03Z · sase-1tz.4.1.3] PROPOSED FOLLOW-UP: Remote-attention dismissals are lost once compaction archives the row — compaction archives a dismissed row 3 days after its last activity, and the reconciler never consults notifications-archive.jsonl, so a request still pending at the same revision is recreated as a fresh unread row. Athena evidence: id 23bf34b3-82d3-5d60-a9bf-f4e207c9172f sits in the archive twice for one revision (archived, recreated, dismissed again). This predates attention_key and limits sase-168.1's "dismissal sticks for its revision" to rows still in the live store. A fix belongs in sase-core: keep dismissed rows owned by an inventory reconciler live while their request is pending, or keep a dismissal tombstone.

[2026-11-20T20:26:10Z · sase-1tz.4.1.3] PROPOSED FOLLOW-UP: Delete the remote-attention legacy migration code once no host holds an undismissed per-revision row — the supersede fold in reconcile_remote_attention_inbox plus _legacy_rows_by_identity and _inherit_legacy_browsing_state in src/sase/dispatch/attention_inbox.py. The first refresh after install dismisses every per-revision row for a pending request, and compaction archives those rows 3 days later. Gate the deletion on the after-install jq census showing 0 live rows whose dedup_key has 4 fields.

[2026-11-20T20:26:18Z · sase-1tz.4.1.3] PROPOSED FOLLOW-UP: tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift and ::test_current_structural_view_matches_checked_in_snapshot fail identically on the clean base f6b4344d87 (git stash, isolated rerun) with "sase CLI completion spec is out of sync with the argparse tree" — run `just sync-completion-spec` or find the parser drift. Unrelated to attention_key, and no open bead tracks it.

[2026-11-20T20:26:25Z · sase-1tz.4.1.3] PROPOSED FOLLOW-UP: Possible load flake — tests/sdd/test_artifact_link_store_projected.py::test_volume_smoke_12500_projected_rows_rebuild_inside_budget failed in `sase tool run check` a982bc6eb2ad2cf702a0e411644fdf2d (which escalated to the full suite while a sase-core check ran in parallel at load1 ~25) and passed alone in 0.25s. Triage labeled it NEW, and no flake bead tracks it. The same run also failed KNOWN tests/ace/tui/actions/test_view_files_pager_contract.py::test_ace_built_document_follows_a_linked_capture_source (witness 004ecc862e32).

[2026-11-20T20:27:36Z · sase-1tz.4.1.3] VERIFIED: sase-core `sase tool run check` f66aa8bbcc74 passed (fmt, features, clippy, all tests), including 7 new parity tests in notification_store_parity/reconcile_resurface.rs and a binding round-trip in sase_core_py. In sase, with a sase_core_rs built from the linked checkout: tests/test_dispatch_attention_inbox.py passes 21/21. Those tests cover an identical re-emission (no reconcile call, store bytes and generation unchanged), a new revision updating and resurfacing the one row, a dismissal sticking for its revision, and the legacy migration (user dismissal carries over, an undismissed legacy row folds with the marker, an older-revision dismissal does not hide a new revision, an auto-dismissal does not carry). The wire test passes too. In sase `sase tool run check` a982bc6eb2ad every lint, docs, and validation stage passed. Of the 62,488 tests in the escalated full lane, 4 unrelated tests failed: 2 completion-snapshot tests that fail identically on the clean base, 1 volume smoke that passes alone, and 1 KNOWN pager contract test. The host revision_pin follow moves sase-core-revision.txt to the sase-core commit; the pin was 0939137425 = sase-core origin/master, so it is not moving backwards.

[2026-11-20T20:34:09Z · sase-1tz.4.1.3] Closed by explicit `sase stitch create -B close` after create_commit landed 0386c59150 ("feat(notifications): key remote-attention rows by stable request identity"). The commit author requested bead completion after verifying the bead scope. Reopen with `sase bead open sase-1tz.4.1.3` if more work remains.

## Dependencies

- **Blocks:** [sase-1tz.4.1.4](sase-1tz.4.1.4.md) ◐ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.4.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.3/README.md) | [sase-1tz.4.1.3](sase-1tz.4.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@2c33360`](https://github.com/sase-org/sase-core/commit/2c33360ad602932ccd63e6941b4751b979efe133) | feat(notifications): resurface reconciled rows when a named revision key changes | [sase-1tz.4.1.3](sase-1tz.4.1.3.md) | 2026-11-20 15:28:38 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.4.1.3][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.3/README.md

<!-- sase:referenced-by:end -->
