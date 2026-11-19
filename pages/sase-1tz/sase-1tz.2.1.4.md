# Bead: sase-1tz.2.1.4 — Give drain cleanup a budget it can finish and sweep stranded publisher scratch

[Bead Pages](../README.md) / [sase-1tz.2.1](sase-1tz.2.1.md) / sase-1tz.2.1.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.md) · **Assignee:** `sase-1tz.2.1.4` · **Size:** medium
**Created:** 2026-11-19 11:13:26 EST
**Plan:** [202611/noise\_publication\_digests\_tui\_stalls.md](https://github.com/sase-org/sase--plans/blob/main/202611/noise_publication_digests_tui_stalls.md)

## Description

pub_cleanup: the drain reserves a cleanup window inside its timeout and records a verifiable cleanup result. Stale .sase-v2-stage/.sase-v2-backup scratch is swept under the publisher lock. Workspace retention stops treating agents-sync scratch in the machine-wide agents sidecar as a run's stranded work.

## Notes

[2026-11-19T16:46:39Z · sase-1tz.2.1.4] MEASUREMENT 2026-11-19 (read-only; no live repair). Cleanup cap raised 1.0s → 15.0s from athena ledger (payload_clean+cleanup n=1058, p50≈1.60s, p95≈2.10s, max≈11.76s). Live `cleanup_result` is absent on both hosts until this lands.

Athena: 2 stranded dirs under `~/.sase/projects/gh_sase-org__sase/repos/agents/` — `.sase-v2-backup-kyrs0ld1` and `.sase-v2-stage-6nhjyn0l` (both 2026-11-03 10:56). `sase notify list -a -j -l 10000 -q 'agents prompt archive'` = 27 (plan cited 28). Drain ledger 529 rows: no_requests=261 published=267 timeout=1. payload_clean n=529 p50=1.608 p95=2.221 max=10.000; cleanup n=529 p50=1.598 p95=2.024 max=11.762.

Apollo: 0 `.sase-v2-*` dirs. Same notify query = 3. Drain ledger 148 rows: no_requests=71 published=71 timeout=6. payload_clean n=148 p50=1.590 p95=4.555 max=18.443; cleanup n=148 p50=1.564 p95=2.923 max=38.686. The 38s cleanup and 15s “budget exhausted” rows are alarm-fired timeout/no_requests under the old 1s cap; one published payload_clean=18.4s sits inside the 120s work window, not the exception reserve. 15s therefore covers athena max with headroom; apollo exception overruns take the deferred next-pass path.

After-install (maxdepth 3 misses sidecar-root scratch at depth 4):
`find ~/.sase/projects -name '.sase-v2-*'; sase notify list -a -j -l 10000 -q 'agents prompt archive' | python3 -c 'import json,sys;print(len(json.load(sys.stdin)))'`
One-time live sweep of the Nov 3 pair is proposed via `/sase_gate`, not applied here.

## Dependencies

- **Blocks:** [sase-1tz.2.1.5](sase-1tz.2.1.5.md) ◐ · ⧖ 2026-11-19
- **Blocks:** [sase-1tz.2.1.6](sase-1tz.2.1.6.md) ◐ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.2.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.4/README.md) | [sase-1tz.2.1.4](sase-1tz.2.1.4.md) | 0 |
