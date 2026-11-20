# Bead: sase-1tz.3.1.5 — Treat a prebuilt Rust artifact cache miss as a miss, not a failure

[Bead Pages](../README.md) / [sase-1tz.3.1](sase-1tz.3.1.md) / sase-1tz.3.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.3.md) · **Assignee:** `sase-1tz.3.1.5` · **Size:** small
**Created:** 2026-11-20 09:19:06 EST · **Closed:** 2026-11-20 09:32:49 EST
**Plan:** [202611/defects\_wire\_swap\_telegram\_bundles\_triage.md](https://github.com/sase-org/sase--plans/blob/main/202611/defects_wire_swap_telegram_bundles_triage.md)

## Description

prebuild_miss: prebuild consume exits 0 and records hit:false with its reason on a cache miss. Dev-update reconcile records the step as a miss, then builds from source. The prebuild producer's writer probe also recognizes install.dev and install.pypi swaps.

## Notes

[2026-11-20T14:32:15Z · sase-1tz.3.1.5] MEASURE: apollo 2026-11-20 read-only ~/.sase/logs/dev_update.jsonl: 46 records, 45 attempted rust_prebuild steps, 22 hits, 23 misses all reason=commit-mismatch, 23 nonzero consume returncodes (audit was 18 of 37). After install, rerun: ssh apollo python3 -c "from pathlib import Path; import json; p=Path.home()/\" .sase/logs/dev_update.jsonl\".replace(\" \", \"\"); rows=[json.loads(l) for l in p.read_text().splitlines() if l.strip()]; att=[r for r in rows if ((r.get(\"result\") or {}).get(\"rust_prebuild\") or {}).get(\"attempted\")]; print(\"records\",len(rows),\"attempted\",len(att));
hits=misses=nonzero=0; reasons={};
for r in att:
 pre=r[\"result\"][\"rust_prebuild\"];
 hits += 1 if pre.get(\"hit\") else 0;
 misses += 0 if pre.get(\"hit\") else 1;
 reasons[pre.get(\"reason\") or \"?\"] = reasons.get(pre.get(\"reason\") or \"?\",0) + (0 if pre.get(\"hit\") else 1);
 nonzero += sum(1 for c in r.get(\"commands\") or [] if \"prebuilt\" in (c.get(\"label\") or \"\").lower() and c.get(\"returncode\") not in (0,None));
print(\"hits\",hits,\"misses\",misses,\"nonzero_prebuild_commands\",nonzero,\"miss_reasons\",reasons);
print(\"last10\");
[print(r.get(\"timestamp\"), pre:=r[\"result\"][\"rust_prebuild\"], \"rc\", next((c.get(\"returncode\") for c in r.get(\"commands\") or [] if \"prebuilt\" in (c.get(\"label\") or \"\").lower()), None), \"counts\", (r.get(\"result\") or {}).get(\"counts\")) for r in att[-10:]]
"  New records after install should keep commit-mismatch misses but show consume rc=0, rust_prebuild.status=miss, and counts.miss rather than a failed/warned step.

[2026-11-20T14:32:34Z · sase-1tz.3.1.5] AFTER-INSTALL (apollo, read-only): python3 -c "
from pathlib import Path
import json
p = Path.home() / \".sase/logs/dev_update.jsonl\"
rows = [json.loads(l) for l in p.read_text().splitlines() if l.strip()]
att = [r for r in rows if ((r.get(\"result\") or {}).get(\"rust_prebuild\") or {}).get(\"attempted\")]
print(\"records\", len(rows), \"attempted\", len(att))
hits = misses = nonzero = 0
reasons = {}
for r in att:
    pre = r[\"result\"][\"rust_prebuild\"]
    if pre.get(\"hit\"):
        hits += 1
    else:
        misses += 1
        reasons[pre.get(\"reason\") or \"?\"] = reasons.get(pre.get(\"reason\") or \"?\", 0) + 1
    for c in r.get(\"commands\") or []:
        if \"prebuilt\" in (c.get(\"label\") or \"\").lower() and c.get(\"returncode\") not in (0, None):
            nonzero += 1
print(\"hits\", hits, \"misses\", misses, \"nonzero_prebuild_commands\", nonzero, \"miss_reasons\", reasons)
for r in att[-10:]:
    pre = r[\"result\"][\"rust_prebuild\"]
    rc = next((c.get(\"returncode\") for c in r.get(\"commands\") or [] if \"prebuilt\" in (c.get(\"label\") or \"\").lower()), None)
    print(r.get(\"timestamp\"), \"hit\", pre.get(\"hit\"), \"reason\", pre.get(\"reason\"), \"status\", pre.get(\"status\"), \"rc\", rc, \"counts\", (r.get(\"result\") or {}).get(\"counts\"))
"
Expect post-install misses to keep reason=commit-mismatch with consume rc=0, status=miss, and counts.miss incremented; nonzero_prebuild_commands should stay at the pre-install 23 unless new errors appear.

[2026-11-20T14:32:49Z · sase-1tz.3.1.5] consume exits 0 on cache miss with hit:false and the miss reason; copy-failure and health-check-failed stay nonzero. Reconcile records timeline status miss and journal counts.miss, then still builds from source. Writer probe treats install.dev and install.pypi as writers. Focused tests: test_prebuild, test_execute_reconcile, test_progress, test_journal, test_update_command_dev, update_progress (133 passed). Apollo baseline 23/45 commit-mismatch misses with nonzero consume rc recorded on this bead and sase-1tz.3.

[2026-11-20T15:38:41Z · sase-1tz.3.1.5--1] PROPOSED FOLLOW-UP: test_snapshot_includes_live_config_token_refresh_threads failed in escalated just check — already tracked by ready flake task sase-t6 (+1 this turn); dummy hold.wait(30s) can expire during a slow xdist snapshot walk. Applied a test-only hold-until-release robustness fix on this tree so verification can land; sase-t6 still owns residual parallel-lane flake work. FLAKY auto-refresh tick node also failed (untouched).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.3.1.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.3.1.5.md) | [sase-1tz.3.1.5](sase-1tz.3.1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f9b8800`](https://github.com/sase-org/sase/commit/f9b88003413260bc1c85ecb39ea1d794a6d17db5) | fix(dev-update): treat a prebuilt Rust cache miss as a miss | [sase-1tz.3.1.5](sase-1tz.3.1.5.md) | 2026-11-20 11:00:46 EST |
