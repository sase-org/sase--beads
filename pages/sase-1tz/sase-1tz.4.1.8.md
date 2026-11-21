# Bead: sase-1tz.4.1.8 — Keep one task-triage notification per bead across presentation changes

[Bead Pages](../README.md) / [sase-1tz.4.1](sase-1tz.4.1.md) / sase-1tz.4.1.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.4.md) · **Assignee:** `sase-1tz.4.1.8` · **Size:** medium
**Created:** 2026-11-20 14:00:23 EST · **Closed:** 2026-11-20 15:23:54 EST
**Plan:** [202611/hygiene\_gateway\_notifications\_retention.md](https://github.com/sase-org/sase--plans/blob/main/202611/hygiene_gateway_notifications_retention.md)

## Description

triage_volume: measure which fingerprint inputs churn triage gates. Stop canceling and recreating a pending gate for presentation drift the gate does not render. Recreated gates reuse one notification row per bead. Remove or keep the quiet-task-beads rule per the decision.

## Notes

[2026-11-20T20:22:03Z · sase-1tz.4.1.8] MEASURE (before, read-only, 2026-11-20 ~15:30 EST). Triage-gate notification rows (TaskTriage+BeadSnooze+FlagTriage, live+archive, window 2026-10-21..2026-11-20): athena rows=1118 over 31 days = 36.1/day, 476 bead-kinds, 2.35 rows per bead-kind, max 27; apollo rows=978 = 31.5/day, 404 bead-kinds, 2.42 rows per bead-kind, max 27. Gate churn census (diff of consecutive task_triage request.json payload + task.md sections): athena 5110 bundles / 1334 beads, 2142 task_triage_presentation_changed recreations; apollo 2485 bundles / 929 beads, 1519 recreations. Top churn sources (athena; apollo is the same shape): +1 evidence 1535 (72%; changes the +N badge, the +1 Evidence section and plus_one_count), bead notes 467, description 197, refs 173, typed-body sections 169, option/contract changes 72, close history 18. All 112 recreations (apollo: 70) with no visible diff fall in 4 one-hour bursts (2026-08-18 x2, 08-21, 09-29), i.e. renderer/contract version bumps, not bead edits. So nearly all churn is from inputs the gate really renders; the fix is one row per bead, not a smaller hash. FlagTriage hashed +1 evidence and close history it never renders (0 flag_triage bundles on either host so far).

[2026-11-20T20:22:13Z · sase-1tz.4.1.8] AFTER-INSTALL COMMAND (run on athena, and on apollo as: ssh apollo "python3 -I - ~/.sase/notifications <SINCE>" < script.py). Pick SINCE = install date; rows per bead-kind should fall toward 1 per ready episode and rows/day should drop well below 36: python3 -I - ~/.sase/notifications <SINCE> <<'PY'
import json,sys,collections as C
from pathlib import Path
b,since=Path(sys.argv[1]).expanduser(),sys.argv[2];seen=set();day=C.Counter();bead=C.Counter()
for n in ("notifications-archive.jsonl","notifications.jsonl"):
  p=b/n
  if not p.is_file(): continue
  for l in p.open():
    try:r=json.loads(l)
    except ValueError:continue
    if r.get("action") not in {"TaskTriage","BeadSnooze","FlagTriage"} or r["id"] in seen or r.get("timestamp","")[:10]<since:continue
    seen.add(r["id"]);day[r["timestamp"][:10]]+=1;bead[r["action_data"].get("request_id","").rsplit("-g",1)[0]]+=1
t=sum(day.values());print(f"rows={t} days={len(day)} rows/day={t/max(len(day),1):.1f} bead_kinds={len(bead)} rows/bead_kind={t/max(len(bead),1):.2f} max/bead_kind={max(bead.values(),default=0)}")
PY

[2026-11-20T20:22:32Z · sase-1tz.4.1.8] MECHANISM: notification_gates had no safe in-place presentation update (bundles are write-once and hash-verified), so a re-presentation recreates the gate but keeps one row. create_gate(notification_id=...) lets a successor adopt an existing row: reconcile_notification_rows refreshes only content fields (notes, files, action_data, chip) and keeps read, dismissed, timestamp and +1s; a born-snoozed gate re-applies its wake time; a failed creation restores the predecessor content. cancel_gate(settle_notification=False) retires the superseded bundle without dismissing the shared row. bead_task_triage creates the successor first (adopting the pending gate row), then retires the predecessor; if creation fails it keeps tracking the old gate; the request_id_conflict branch from b6f6c63e3e is kept and retires a conflicting gate that holds the carried row without settling it; the untracked sweep leaves a row that now presents another gate. A new unread row appears only on a kind change or when the bead re-enters ready. presentation_fingerprint is now kind-scoped: inputs a kind does not render are pinned empty (FlagTriage: +1 evidence, close history; non-snooze kinds: snooze), so every existing TaskTriage/BeadSnooze stored fingerprint is byte-identical (checked against the pre-change code) and install causes no mass re-presentation.

[2026-11-20T20:22:40Z · sase-1tz.4.1.8] CHEZMOI (quiet_triage_rule = remove): deleted only the quiet-task-beads rule (and its now-empty notification_rules key) from the chezmoi source home/dot_config/sase/sase.yml. athena quiet-task-beads-telegram in sase_athena.yml is untouched. Validated without applying: YAML parses and both sase.yml and sase_athena.yml pass src/sase/config/sase.schema.json with 0 errors. It takes effect only when the human runs chezmoi apply after installing this change; Beads-tab toasts and sounds return then.

[2026-11-20T20:22:46Z · sase-1tz.4.1.8] PROPOSED FOLLOW-UP: Regenerate the stale completion snapshot — tests/completion/test_snapshot.py (2 tests) fails on clean HEAD (reproduced from a git-archive export of HEAD): only the description_digest of sase artifact link list drifted, after eca97ab5a7 changed src/sase/artifact_cli/ without just sync-completion-spec. No open bead tracks it.

[2026-11-20T20:22:52Z · sase-1tz.4.1.8] PROPOSED FOLLOW-UP: Close the triage fingerprint under-coverage — the TaskTriage preview renders created_by (Filed by), closed_at (post-close +1 markers) and the full task_type_fields body, but presentation_fingerprint hashes only the truncated task_type_display facts and neither created_by nor closed_at, so an edit there leaves a pending gate stale. Adding them changes every stored fingerprint, so pair it with a one-time adopt-in-place refresh (now cheap: no new rows) or a fingerprint-scheme migration.

[2026-11-20T20:23:54Z · sase-1tz.4.1.8] Measured churn read-only on athena and apollo (before-numbers and after-install command in notes); +1 evidence drives 72% of recreations, so a pending gate's re-presentation now creates the successor adopting the old notification row in place (create_gate(notification_id=...)) and retires the predecessor without settling it (cancel_gate(settle_notification=False)); fingerprint is kind-scoped with TaskTriage/BeadSnooze hashes byte-identical to before; request_id_conflict recovery kept; quiet-task-beads removed from chezmoi source and schema-validated (applies on chezmoi apply). Verified: new tests (one row across N +1s, dismissal survives, kind change and ready re-entry raise new rows, conflict recovery, retire failure, failed successor, non-rendered edits cause no cancellation, service adoption/restore) plus 3766 related gate/triage tests pass; ruff, mypy, symvision clean; sase tool run check passed every lint gate and 62501 tests, its only remaining failure being the completion-snapshot drift that reproduces on clean HEAD (PROPOSED FOLLOW-UP noted).

## Dependencies

- **Blocks:** [sase-1tz.4.1.9](sase-1tz.4.1.9.md) ✓ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.4.1.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.8/README.md) | [sase-1tz.4.1.8](sase-1tz.4.1.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2b18880`](https://github.com/sase-org/sase/commit/2b18880ef1c0d12bd75e37b90542f5447a73867b) | feat(triage): keep one task-triage notification row per bead across re-presentations | [sase-1tz.4.1.8](sase-1tz.4.1.8.md) | 2026-11-20 15:25:48 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.4.1.8][1] | Check for earlier notes on this phase | 2 |
| read-by | [agent:sase-1tz.4.1.9][2] | Need predecessor notes for measurement pattern | 1 |
| read-by | [agent:sase-1tz.4.1.land][3] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.8/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.9/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.land/README.md

<!-- sase:referenced-by:end -->
