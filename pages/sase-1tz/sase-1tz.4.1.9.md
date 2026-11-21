# Bead: sase-1tz.4.1.9 — Settle orphaned triage gates and reap settled gate bundles

[Bead Pages](../README.md) / [sase-1tz.4.1](sase-1tz.4.1.md) / sase-1tz.4.1.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.4.md) · **Assignee:** `sase-1tz.4.1.9` · **Size:** medium
**Created:** 2026-11-20 14:00:24 EST · **Closed:** 2026-11-20 16:33:43 EST
**Plan:** [202611/hygiene\_gateway\_notifications\_retention.md](https://github.com/sase-org/sase--plans/blob/main/202611/hygiene_gateway_notifications_retention.md)

## Description

gate_reconcile: a pending automation-owned gate whose notification was dismissed, or whose bead is resolved, is cancelled. A dismissal is not undone by the next pass. Settled task-triage and snooze bundles older than a horizon are reaped. Other gate kinds are only counted.

## Notes

[2026-11-20T21:03:34Z · sase-1tz.4.1.9] MEASURE (before, read-only, 2026-11-20 ~16:30 EST). Bundle census: athena task_triage pending=433 settled=4686 settled_old30d=3627; bead_snooze pending=15 settled=33 old30d=24; flag_triage missing (0 bundles). apollo task_triage pending=433 settled=2061 old30d=1128; bead_snooze pending=15 settled=14 old30d=7; flag_triage missing. Pending gates with dismissed notifications: athena task_triage 0/433, bead_snooze 0/15; apollo 0/433 and 0/15. So the orphan queue is currently empty; the reaper backlog is ~3650 athena + ~1135 apollo settled triage/snooze bundles older than 30d. sase-core agent_stats/gate_bundles.rs only scans plan/epic_plan/question, so reaping triage bundles changes no stats aggregates.

[2026-11-20T21:03:49Z · sase-1tz.4.1.9] AFTER-INSTALL COMMAND (run on athena, and on apollo as: ssh apollo "python3 -" < script.py). Counts settled triage/snooze/flag bundles older than the horizon and pending dismissed gates: python3 - <<PY
from pathlib import Path
import json, time
root=Path.home()/".sase/interaction_requests"
notif=Path.home()/".sase/notifications/notifications.jsonl"
dismissed=set()
try:
  for line in notif.open():
    try: r=json.loads(line)
    except: continue
    if r.get("dismissed"): dismissed.add(r.get("id"))
except FileNotFoundError: pass
now=time.time(); cutoff=now-30*86400.0
for kind in ("task_triage","bead_snooze","flag_triage"):
  d=root/kind
  if not d.is_dir(): print(f"{kind}: missing"); continue
  pending=dism=settled=old=0
  for b in d.iterdir():
    if not b.is_dir(): continue
    if (b/"response.json").is_file() or (b/"cancellation.json").is_file():
      settled+=1
      m=max([(b/f).stat().st_mtime for f in ("response.json","cancellation.json") if (b/f).is_file()])
      if m < cutoff: old+=1
    elif (b/"request.json").is_file():
      pending+=1
      try: nid=json.loads((b/"request.json").read_text()).get("notification_id")
      except: nid=None
      if nid in dismissed: dism+=1
  print(f"{kind}: pending={pending} dismissed_pending={dism} settled={settled} old30d={old}")
PY

[2026-11-20T21:03:59Z · sase-1tz.4.1.9] MECHANISM: orphan reconciliation runs inside _reconcile for automation-owned kinds (task_triage, bead_snooze, flag_triage). A pending gate whose notification row is dismissed is cancelled with reason notification_dismissed and recorded in lane state dismissed[bead]=kind; the pass does not recreate it and a dismissal never undismisses the row. The suppression lifts when the gate kind changes (recreate as new kind) or the bead leaves gateable entirely (state entry cleared when bead not in gateable set, plus on resolved-bead cancel). Resolved/gone beads cancel with existing reasons. NotificationIndex now loads include_dismissed=True and exposes is_dismissed (missing row = not dismissed, so archival never cancels a live gate). Settled-bundle retention deletes task_triage/bead_snooze/flag_triage bundles with response/cancellation mtime older than bead.task_triage.settled_bundle_retention_days (default 30) under the per-bundle creation lock, root-confined without symlink follow, cap bead.task_triage.settled_bundle_reap_cap (default 100) per pass with capped flag. Other kinds are counted in other_dismissed_pending and never cancelled/reaped.

[2026-11-20T21:04:05Z · sase-1tz.4.1.9] DECISIONS: quiet_triage_rule=remove already landed by sase-1tz.4.1.8 in chezmoi 058b195b (rule removed from sase.yml, telegram rule untouched); this phase changes nothing there. index_backups=report belongs to clutter_reapers phase; this phase adds no backup deletion and reports nothing automatically (report-only branch deferred to sase-1tz.4.1.13).

[2026-11-20T21:32:59Z · sase-1tz.4.1.9] VERIFICATION: targeted triage lane green (86 tests: gate_lifecycle, gate_reconcile x7, one_row, presentation, projects, snooze, liveness, launches, plus_ones, gate_kwargs), adoption+schema green (27 tests), ruff+mypy+symvision green, just fix clean. sase tool run check (runs 75c48250, 469a3ce0) passed all lint gates incl. symvision after fix and docs build; the diff-scoped lane escalated to FULL_SUITE via src-data-asset rule (default_config.yml + footprint catalog) and could not finish in-turn under host load ~47 within the 10m provider ceiling. No check failure observed; full-suite completion left to the land agent on the combined tree.

[2026-11-20T21:33:43Z · sase-1tz.4.1.9] gate_reconcile landed: dismissed pending triage/snooze/flag gates cancel with notification_dismissed and stay suppressed until kind change or re-entry; resolved beads cancel with existing reasons; settled bundles older than 30d reaped under creation lock with cap 100, other kinds only counted. Verified: 86 triage + 27 adoption/schema tests green, ruff/mypy/symvision green, just fix clean; full check lint green, scoped lane escalated to full suite and left to land agent under host load.

## Dependencies

- **Depends on:** [sase-1tz.4.1.8](sase-1tz.4.1.8.md) ✓ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.4.1.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.9/README.md) | [sase-1tz.4.1.9](sase-1tz.4.1.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1115db9`](https://github.com/sase-org/sase/commit/1115db9e66d4ebc82114d74a7fc524eab0900b42) | feat(bead-triage): reconcile notification gates with sticky dismissal and settled-bundle reaping | [sase-1tz.4.1.9](sase-1tz.4.1.9.md) | 2026-11-20 16:40:14 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.4.1.9][1] | Need notes and full detail to implement | 4 |
| read-by | [agent:sase-1tz.4.1.land][2] | Need the child scope and notes | 1 |
| read-by | [agent:sase-1uj.land][3] | Confirm audit-site ownership before routing catalog phase follow-up | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.9/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.land/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1uj.land/README.md

<!-- sase:referenced-by:end -->
