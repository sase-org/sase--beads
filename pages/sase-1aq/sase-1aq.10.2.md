# Bead: sase-1aq.10.2 — Complete the unified live dispatch and exact-operation matrix

[Bead Pages](../README.md) / [sase-1aq.10](sase-1aq.10.md) / sase-1aq.10.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.23](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.23.md) · **Assignee:** `sase-1aq.10.2` · **Size:** medium
**Created:** 2026-09-26 17:34:41 EDT · **Closed:** 2026-09-26 18:17:20 EDT
**Plan:** [202609/finish\_1aq\_live\_closeout.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_1aq_live_closeout.md)

## Description

unified_proof: finish the original unified live proof and the remaining fault cases on a matching released cohort.

## Notes

[2026-09-26T22:15:45Z · sase-1aq.10.2] unified_proof live evidence 2026-09-26T22:05-22:15Z: repaired service-host gateway bridge doubling (src/sase/integrations/mobile_gateway.py: service launch passed full "sase mobile agent-bridge" while Rust invoke() appends mobile/agent-bridge/<op> itself; every fleet launch died in argparse exit 2 with bare receipt "launch_failed: agent_bridge:launch-text"; regression since e92e6c91c service-host move; fixed to bare sase exe per runbook contract, test updated, 34 passed +1 pre-existing env error identical on clean base). Fix mirrored to primary checkout, gateway restarted via service host (proc 3174750->3422963, then host restart; hello ok schema v6, enrollment intact, live rows preserved). dispatch-a464978fdf02d2e8a650a5242ec5fcce: accepted 22:05:51Z, success 22:05:56Z, receipt settled with logical locator, owner RUNNING pid 3426769, DONE completed with nonempty reply + artifacts. Same-key retry of 7664 refused ExpiredOrTombstonedKey with no duplicate execution. Source preflight proven (home-dir dispatch refused without git evidence; repo dispatch accepted). Cohort Apollo sase 0.17.1+1549/core 0.34.73+46, Athena sase 0.17.1+1540/core 0.34.73+46, gateway 0.34.73.

[2026-09-26T22:16:11Z · sase-1aq.10.2] PROPOSED FOLLOW-UP: Athena exact-name remote stop/retry cannot address fleet-dispatched rows - catalog_sync query returns 0 rows for dispatch-a464978f, dispatch-5330c1fc and broad "dispatch" while "bob-cli-26.4.land" returns 1; stop by full id failed twice live plus retry after 150s ("no remote agent matching"); blocks .7.6 remote exact-stop acceptance; suspect settled-receipt (project sase) vs landed-agent (project home) mismatch drops rows from served catalog -r unified_proof remote-stop gap for sase-1aq.10.3

[2026-09-26T22:16:25Z · sase-1aq.10.2] PROPOSED FOLLOW-UP: viewer-side matrix leftovers for sase-1aq.10.3 - unfollowed-remote attention, stale-gate refusal, composable project/machine queries, target-picker focus, healthy-beside-hung navigation, .16.11.3 genuine old-locator rejection, .16.11.5/.16.10 e2e, .7.13 explicit-%id and picker incidents; codex agents do not literally sleep (a464/533 finished in ~60s via monitor-continuation, requested verbatim marker lines never printed), so exact-output proofs need sleep-free prompts -r unified_proof leftovers for sase-1aq.10.3

[2026-09-26T22:17:20Z · sase-1aq.10.2] verified: bridge-doubling root cause fixed (34 focused tests pass, 1 pre-existing env error also on clean base); live dispatch-a464978f accepted->success with settled receipt, owner RUNNING/DONE, nonempty output+artifacts; same-key retry refused without duplicate; gateway restart recovery via service host; remote-stop-by-name gap + viewer leftovers recorded as PROPOSED FOLLOW-UPs for sase-1aq.10.3; no epic-symbols

[2026-09-26T22:57:16Z · sase-1aq.10.2--1] PROPOSED FOLLOW-UP: just check fails identically on clean base tree (monitor tq5qfn3tyek8: 82 failed +10 errors scoped, 93 NEW triage; sampled test_procs_service::test_submit_records_a_named_proc and test_parser_proc::test_proc_run_and_list_parse_named_named_proc fail with stash applied too; symvision lint item is KNOWN witness c35f1c106893aef0f4a906db3769f6b1f6b1) - pre-existing proc-surface breakage unrelated to mobile-gateway bridge-doubling fix; focused tests/test_mobile_gateway.py 35 passed

## Dependencies

- **Depends on:** [sase-1aq.10.1](sase-1aq.10.1.md) ✓ · ⧖ 2026-09-26
- **Blocks:** [sase-1aq.10.3](sase-1aq.10.3.md) ◐ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1aq.10.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1aq.10.2.md) | [sase-1aq.10.2](sase-1aq.10.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`29f8240`](https://github.com/sase-org/sase/commit/29f8240df594e321befb65d0881bbbdd7feff6ee) | fix(mobile-gateway): pass bare sase exe for bridge commands (sase-1aq.10.2) | [sase-1aq.10.2](sase-1aq.10.2.md) | 2026-09-26 18:58:58 EDT |
