# Bead: sase-1tz.4.1.10 — Silence success toasts, dedup workspace-rescue, floor prune nudges, and skip no-op claim writes

[Bead Pages](../README.md) / [sase-1tz.4.1](sase-1tz.4.1.md) / sase-1tz.4.1.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.4.md) · **Assignee:** `sase-1tz.4.1.10` · **Size:** medium
**Created:** 2026-11-20 14:00:24 EST · **Closed:** 2026-11-20 19:23:23 EST
**Plan:** [202611/hygiene\_gateway\_notifications\_retention.md](https://github.com/sase-org/sase--plans/blob/main/202611/hygiene_gateway_notifications_retention.md)

## Description

notify_quieting: file-hooks successes become one silent row per hook, and workspace-rescue gets a stable dedup key. Artifact-run prune nudges fire only above a size floor or under disk pressure. hold_workspace_claim writes no ledger row when nothing changed.

## Notes

[2026-11-20T21:28:57Z · sase-1tz.4.1.10] MEASURE notify_quieting BEFORE (read-only, 2026-11-20 ~14:10 EST). athena live notifications.jsonl: file-hooks 160 ok + 4 failed rows; workspace-rescue 144 rows, 0 with a dedup key; axe artifact_run_prune rows 3. athena archive: file-hooks 138 ok + 2 failed; workspace-rescue 53 (0 dedup); prune 45. apollo live: file-hooks 208 ok + 2 failed; workspace-rescue 114 (0 dedup); prune 0. apollo archive: file-hooks 78 ok + 5 failed; workspace-rescue 47; prune 24. Claim ledger "already pinned (no-op)" hold rows: athena 481 on 2026-11-19 (ledger window starts 09:54) + 42 on 2026-11-20 by 14:06, all caller_tag workspace-retention (523 of 533 hold rows); apollo 0 in its current ledger window. Rescue key choice measured on athena (197 rescue rows all-time): keying on workspace+cause gives 75 rows, workspace+label+cause 119, so the key is workspace dir + normalized reason (digits/hex ids collapse to N). AFTER (run on each host after install; expect file-hooks ok rows created after install = 1 per hook and silent, rescue rows carrying dedup keys, prune rows only above 1 GiB or under pressure, no-op ledger rows = 0): python3 -I -c 'import json,os,collections as C,glob,sys;since=sys.argv[1];h=os.path.expanduser("~/.sase");c=C.Counter();[c.update([(r["sender"],"silent" if r.get("silent") else "loud","dedup" if r.get("dedup_key") else "nodedup")]) for r in map(json.loads,open(h+"/notifications/notifications.jsonl")) if r.get("timestamp","")>=since and (r.get("sender") in ("file-hooks","workspace-rescue") or (r.get("dedup_key") or "").startswith("artifact_run_prune:"))];print(dict(c));n=C.Counter(str(r.get("timestamp"))[:6] for p in glob.glob(h+"/logs/workspace_claims.jsonl*") if not p.endswith(".lock") for r in map(json.loads,open(p)) if r.get("operation")=="hold" and r.get("error")=="already pinned (no-op)");print("noop holds/day",dict(sorted(n.items())))' <install-date e.g. 2026-11-21>

[2026-11-20T21:29:16Z · sase-1tz.4.1.10] PROPOSED FOLLOW-UP: possible flaky test tests/test_axe_chop_runner_script.py::test_run_configured_chop_once_records_unresolved_secret_as_check_error — failed once in the escalated full scoped lane of sase tool run e6d69b4f7946d152e32bc5c40017e361 (62,504 passed, 5 failed) but passes alone and with its whole module on the same tree; it exercises chop env-secret resolution, unrelated to this phase. No existing flake bead found.

[2026-11-21T00:23:23Z · sase-1tz.4.1.10--2] Closed by explicit `sase stitch create -B close` after create_commit landed 335170e1cb ("feat(notifications): quiet file-hook successes, dedup rescues, floor prune nudges"). The commit author requested bead completion after verifying the bead scope. Reopen with `sase bead open sase-1tz.4.1.10` if more work remains.

[2026-11-21T00:28:15Z · sase-1tz.4.1.10--2] PROPOSED FOLLOW-UP: ACE-run retention selects live continuation ancestry for pruning since 92dc6274e5 — tests/core/test_continuation_retention.py::test_plan_protects_live_continuation_ancestry_from_audit_probe fails deterministically on origin/master 92dc6274e5 (perf(housekeeping): speed up artifact retention scans; no bead trailer; rewrote agent_artifact_run_retention.py and agent_artifact_run_protection.py) and passes on its parent 6b444fcdef (pristine worktree repro, 2026-11-20). Failing assertion at line 90: `assert old not in selected` — the protected ancestor run dir lands in the prune selection, so retention can trash runs that live continuations still replay. just check triage labels it KNOWN (witness 004ecc862e32316588e888ef0cc4dd20) with no owner. Suggested: task(ci), high priority; restore continuation-ancestry protection in the sped-up scan.

[2026-11-21T00:28:22Z · sase-1tz.4.1.10--2] PROPOSED FOLLOW-UP: review the reap_settled_bundles artifact-directory site added by 1115db9e66 (sase-1tz.4.1.9) — tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed fails deterministically on origin/master: extra unreviewed site 'src/sase/scripts/_bead_task_triage_gates.py:reap_settled_bundles'. Passes at f6b4344d87, fails at 6b444fcdef and 92dc6274e5. Triage: KNOWN, no owner. Same class as closed sase-1p5 / sase-n1; fix is to review the site and register it in the audit (or route it through an already-reviewed helper). Suggested: task(ci), small.

[2026-11-21T00:28:27Z · sase-1tz.4.1.10--2] PROPOSED FOLLOW-UP: the after-rebase import gate (tools/check_rebase_imports, sase-1pm.5.1 / cddea47cc6) never certifies in a real workspace — _python_paths_not_matching_tree (tools/_check_rebase_imports.py:363) unions in `git ls-files -o -i --exclude-standard`, so every gitignored .py under .venv/ and .venv-format/ counts as dirty (8 shown +3519 more here). The gate raises CheckerError, stitch classifies it as an infrastructure error, and publication proceeds unchecked ('allowing publication'). Seen during sase stitch create --resume for 335170e1cb; evidence under the 20261120174114 run's commit_hooks/*after_rebase*.json. Fix: scope the ignored-file query to first-party import roots (src/, tools/) or exclude virtualenv dirs. Not caused by this epic; suggested standalone task(bug), small.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.4.1.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.4.1.10.md) | [sase-1tz.4.1.10](sase-1tz.4.1.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`335170e`](https://github.com/sase-org/sase/commit/335170e1cb0b5b2d597fd43994f30eff784ac126) | feat(notifications): quiet file-hook successes, dedup rescues, floor prune nudges | [sase-1tz.4.1.10](sase-1tz.4.1.10.md) | 2026-11-20 18:51:15 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.4.1.land][1] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.land/README.md

<!-- sase:referenced-by:end -->
