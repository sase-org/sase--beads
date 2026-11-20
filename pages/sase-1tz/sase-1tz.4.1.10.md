# Bead: sase-1tz.4.1.10 — Silence success toasts, dedup workspace-rescue, floor prune nudges, and skip no-op claim writes

[Bead Pages](../README.md) / [sase-1tz.4.1](sase-1tz.4.1.md) / sase-1tz.4.1.10

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.4.md) · **Assignee:** `sase-1tz.4.1.10` · **Size:** medium
**Created:** 2026-11-20 14:00:24 EST
**Plan:** [202611/hygiene\_gateway\_notifications\_retention.md](https://github.com/sase-org/sase--plans/blob/main/202611/hygiene_gateway_notifications_retention.md)

## Description

notify_quieting: file-hooks successes become one silent row per hook, and workspace-rescue gets a stable dedup key. Artifact-run prune nudges fire only above a size floor or under disk pressure. hold_workspace_claim writes no ledger row when nothing changed.

## Notes

[2026-11-20T21:28:57Z · sase-1tz.4.1.10] MEASURE notify_quieting BEFORE (read-only, 2026-11-20 ~14:10 EST). athena live notifications.jsonl: file-hooks 160 ok + 4 failed rows; workspace-rescue 144 rows, 0 with a dedup key; axe artifact_run_prune rows 3. athena archive: file-hooks 138 ok + 2 failed; workspace-rescue 53 (0 dedup); prune 45. apollo live: file-hooks 208 ok + 2 failed; workspace-rescue 114 (0 dedup); prune 0. apollo archive: file-hooks 78 ok + 5 failed; workspace-rescue 47; prune 24. Claim ledger "already pinned (no-op)" hold rows: athena 481 on 2026-11-19 (ledger window starts 09:54) + 42 on 2026-11-20 by 14:06, all caller_tag workspace-retention (523 of 533 hold rows); apollo 0 in its current ledger window. Rescue key choice measured on athena (197 rescue rows all-time): keying on workspace+cause gives 75 rows, workspace+label+cause 119, so the key is workspace dir + normalized reason (digits/hex ids collapse to N). AFTER (run on each host after install; expect file-hooks ok rows created after install = 1 per hook and silent, rescue rows carrying dedup keys, prune rows only above 1 GiB or under pressure, no-op ledger rows = 0): python3 -I -c 'import json,os,collections as C,glob,sys;since=sys.argv[1];h=os.path.expanduser("~/.sase");c=C.Counter();[c.update([(r["sender"],"silent" if r.get("silent") else "loud","dedup" if r.get("dedup_key") else "nodedup")]) for r in map(json.loads,open(h+"/notifications/notifications.jsonl")) if r.get("timestamp","")>=since and (r.get("sender") in ("file-hooks","workspace-rescue") or (r.get("dedup_key") or "").startswith("artifact_run_prune:"))];print(dict(c));n=C.Counter(str(r.get("timestamp"))[:6] for p in glob.glob(h+"/logs/workspace_claims.jsonl*") if not p.endswith(".lock") for r in map(json.loads,open(p)) if r.get("operation")=="hold" and r.get("error")=="already pinned (no-op)");print("noop holds/day",dict(sorted(n.items())))' <install-date e.g. 2026-11-21>

[2026-11-20T21:29:16Z · sase-1tz.4.1.10] PROPOSED FOLLOW-UP: possible flaky test tests/test_axe_chop_runner_script.py::test_run_configured_chop_once_records_unresolved_secret_as_check_error — failed once in the escalated full scoped lane of sase tool run e6d69b4f7946d152e32bc5c40017e361 (62,504 passed, 5 failed) but passes alone and with its whole module on the same tree; it exercises chop env-secret resolution, unrelated to this phase. No existing flake bead found.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.4.1.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.4.1.10.md) | [sase-1tz.4.1.10](sase-1tz.4.1.10.md) | 0 |
