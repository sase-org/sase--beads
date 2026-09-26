# Bead: sase-1aq.4 — Complete the live Apollo snapshot and dismissal proof

[Bead Pages](../README.md) / [sase-1aq](README.md) / sase-1aq.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.athena.0sw` · **Assignee:** `sase-1aq.4` · **Size:** medium
**Created:** 2026-09-26 11:53:29 EDT · **Closed:** 2026-09-26 12:38:43 EDT
**Plan:** [202609/finish\_blocking\_epics\_and\_memory.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_blocking_epics_and_memory.md)

## Description

dispatch_snapshot: prove owner-viewer fleet state, dismissal, history, and restart on live Apollo.

## Notes

[2026-09-26T16:38:13Z · sase-1aq.4] PROPOSED FOLLOW-UP: Apollo owner snapshot served frozen for 45+ min (missing 4 live rows incl. 45-min-old sase-1af.5.1) while summary freshness read aging/partial-false; only index-gc + gateway restart rebuilt it -r dispatch_snapshot: snapshot refresh/invalidation cadence and viewer staleness signal need owner

[2026-09-26T16:38:23Z · sase-1aq.4] PROPOSED FOLLOW-UP: Remote row for live RUNNING agent 1z carried status=FAILED while status_bucket=running/liveness=alive/owner_status=true agreed with owner RUNNING -r dispatch_snapshot: clarify status vs status_bucket semantics on live rows so viewers do not misread health

[2026-09-26T16:38:43Z · sase-1aq.4] dispatch_snapshot verified 2026-09-26 on released cohort (sase 0.17.1+1524 / core 0.34.73+40 both hosts, Apollo hello ok schema v6): owner-viewer appearance (controlled 1z visible remotely after gc+gateway-restart rebuild, counts matched owner 2 running/2 waiting), production dismissal (owner dismiss + restart => 1z gone both pages, no resurrection, others preserved), death reconciliation (kill 1z runner => remote DONE/done/dead new revision, no disconnect inference), history paging (100+68=168 total, 0 overlap, finished), snapshot change (stale cursor => resync_required/snapshot_mismatch, 0 rows), restart resilience (2 managed gateway restarts, enrollment/hello/versions intact). No repo files changed. Evidence note filed on sase-xe.16.11.7.14.6.7.5 (ready for normal close); 2 PROPOSED FOLLOW-UPs filed (snapshot staleness signal; status-vs-bucket semantics). Boundary: ACE-session recovery rides with sase-1aq.5/.7.6 which owns gateway-restart recovery with ACE.

## Dependencies

- **Depends on:** [sase-1aq.3](sase-1aq.3.md) ✓ · ⧖ 2026-09-26
- **Blocks:** [sase-1aq.5](sase-1aq.5.md) ◐ · ⧖ 2026-09-26
