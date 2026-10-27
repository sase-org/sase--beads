# Bead: sase-1ou.2.1.2 — Adopt the core policy and prove the affected ToolRun flows

[Bead Pages](../README.md) / [sase-1ou.2.1](sase-1ou.2.1.md) / sase-1ou.2.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ou.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ou.2.md) · **Assignee:** `sase-1ou.2.1.2` · **Size:** medium
**Created:** 2026-10-27 10:41:27 EDT · **Closed:** 2026-10-27 17:36:25 EDT
**Plan:** [202610/toolrun\_sqlite\_contention.md](https://github.com/sase-org/sase--plans/blob/main/202610/toolrun_sqlite_contention.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:1083872161ac8666fd9b1bda | attached via sase artifact create --bead |
| related | file:explicit:5188d4e4e5c2a4d5dc6c79a1 | attached via sase artifact create --bead |
| related | file:explicit:6b50e3f8b87298d7ac6fc874 | attached via sase artifact create --bead |
| related | file:explicit:6fc26af0d95272457a17d879 | attached via sase artifact create --bead |
| related | file:explicit:a07183c91cc51db252271078 | attached via sase artifact create --bead |
| related | file:explicit:b0d1fd4be5d7f8c6c632927d | attached via sase artifact create --bead |
| related | file:explicit:b13e06f116130351ef4438d2 | attached via sase artifact create --bead |
| related | file:explicit:c0f4bd59f97240f4bbc90b82 | attached via sase artifact create --bead |
| related | file:explicit:c8e2e1dd2954f633e244ccb6 | attached via sase artifact create --bead |
| related | file:explicit:dcdb074200fedcafa5a9f497 | attached via sase artifact create --bead |
| related | file:explicit:e81105351838d35a34702195 | attached via sase artifact create --bead |

<!-- sase:links:end -->

## Description

caller-integration: consume the landed core policy in Python, preserve explicit latency deadlines, ratchet the core pin, repeat the same isolated and loaded stress runs, and retire only proven fixed baseline nodes.

## Notes

[2026-10-27T19:18:21Z · sase-1ou.2.1.2--1] MONITOR CONTINUATION (planned verification, not unfinished single-coder scope): caller integration implemented; all29 store adapters and receipts default to core0, ownership1s and detach5s/busy masking removed; stage2s retained because legitimate600ms writer overlap exceeds core250ms, test holder moved to subprocess. Pin ratcheted to6d11122e with old-pin ancestry verified. 100 focused tests pass; just fix and targeted ruff clean. Natural before each of10nodes:10/10 serial+20/20 loaded pass; all8 workers granted, old extension verified. Decisive controlled last-close400ms scheduling injection: old10/10 show failures at251ms, fixed10/10 pass <2ms; strace proves old last-close checkpoint takes exclusive main-file lock after WAL writer unlock, fixed omits it. No duplicate runs/events/quarantine. Evidence and reusable harnesses file:explicit:a07183c91cc51db252271078. Handing after stress, complete files, and controlled per-node attribution to monitor; then selective baseline retirement, selection_health, guarded check, evidence/closure remain. No baseline entries retired yet; no ancestor/task closed.

[2026-10-27T19:41:24Z · sase-1ou.2.1.2--2] PROPOSED FOLLOW-UP: Retain six ToolRun baseline nodes without per-node lock attribution — audited bundle file:explicit:b13e06f116130351ef4438d2 records all ten nodes at before 10/10 serial and 20/20 loaded pass, after all 10/10 serial and nine 20/20 loaded pass. Controlled last-close400ms failed only both detach watchdog nodes and settlement notification (each old3/3 fail, fixed3/3 pass); those three are retired. Demand, nested executor, inline escalation, known continuation and both wrapper group-kill entries remain active. The original lifecycle node passed controlled3/3 on both cores, so do not claim its natural failure was reproduced. sase-19t handoff complete file passes21/21 including its node, but the original report has no exception text; duplicate status remains unproven. Do not close sase-18t or sase-19t from this phase.

[2026-10-27T19:41:50Z · sase-1ou.2.1.2--2] PROPOSED FOLLOW-UP: Wrapper group-kill exit-order flake remains — after/loaded-11 in file:explicit:b13e06f116130351ef4438d2 failed tests/tool/test_wrapper_fidelity.py::test_owner_child_shares_wrapper_group_and_group_kill_leaves_no_survivors at line231 assert not _alive(child_pid), after successful process-group assertions and wrapper.wait following killpg(SIGKILL). No SQLite exception. Rate1/20 loaded,0/10 serial; subsequent complete file passed8/8 and controlled fixed passes3/3 on the same unchanged integrated tree. Likely process exit-order assertion race (waiting for wrapper does not wait for its child), not proven permanent survival. Keep baseline active; outer lander should triage separately from18t. Existing closed sase-19c grouped historical database-locked failures and does not establish this signature.

[2026-10-27T19:45:15Z · sase-1ou.2.1.2--2] Verification found an in-scope residual core deadline defect: controlled-after.json in file:explicit:b13e06f116130351ef4438d2 has explicit25ms begin waits up to49.951ms. Code confirms enable_wal_mode starts its timer only after initial PRAGMA journal_mode has already spent a SQLite wait. This is a reset, not scheduling tolerance. Local core change moves timer before that probe and adds wal_mode_probe_consumes_conversion_budget (250ms allowance,425ms upper bound with175ms scheduling margin rejects two250ms waits). Preparing red/green core regression, full core check and rebuilt application verification before closure. Core now has a repository commit obligation; host must commit it first and advance primary pin to its actual SHA. No manual commits or invented SHA.

[2026-10-27T20:23:04Z · sase-1ou.2.1.2--2] PROPOSED FOLLOW-UP: Existing broad-check failures reproduced exactly on clean base — primary ToolRun fbab9f2df86cb680af2e7df5bb7142e2 exit1 after42m54s, all lint/validation green; 58227passed,17skipped,3failed in1013.50s with11workers (normal check internally broadened, no check-full). Failures: tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget (3541 modules vs3539 cap, not elapsed time); tests/completion/test_snapshot.py::{test_checked_in_snapshot_has_no_drift,test_current_structural_view_matches_checked_in_snapshot} (CLI spec drift, parent plan cites sase-1om ownership). Current focused rerun and clean d16b79f3 tree with old extension d03a52d... each3failed/2passed; all3 failure messages byte-identical. Restored primary integration byte-for-byte in finally. Logs/XML/build provenance saved as check-rerun.*, check-clean-base.*, initial-check.* and will be in budget-evidence-bundle. No ToolRun SQLite failure in broad run. Selection-health41exceedances likewise identical using HEAD baseline; none of retired3 exceed.

[2026-10-27T21:35:37Z · sase-1ou.2.1.2--3] FINAL EVIDENCE: file:explicit:b0d1fd4be5d7f8c6c632927d is the published/audited landing report; raw final bundle file:explicit:c0f4bd59f97240f4bbc90b82. Core regression fails before at 501.049ms and passes corrected. Final explicit25ms show/begin maxima25.121/25.403ms; all60 bounded probes preserve expected counts/integrity/no quarantine. Each of10 nodes final10/10 serial+20/20 loaded and3/3 controlled passes, with190 correct controller/worker build records; complete14files272/272pass. Preserve earlier after loaded owner-group-kill19/20 and original before zero failures. Retire only3 attributed nodes; six stay active. Final core check b2631e20ccc7a88c5b307a70b5c3f5bd PASS; primary check1c557cb47b1f4832fb4c616a46b209c3 PASS, scoped1276/5414files with4workers. Earlier broad check three clean-base-identical failures remain evidenced, not claimed repaired. Current primary/core diffs match tested bundle; installed source stamp matches core6d11122e+correction digestc3bc74bc473223ca1bd22afcdde37ccaf99322e877eb9606a8ecedfc1e781453, extensiond39e8fe63e50ff4c5ae0b16e42fa20cf03c32ab098ee12687b4e07f638748914. Declare both repos: host commitscorefirst and follows configured revision_pin to actualSHA before primary commit. Epic-symbol audit has no entries. Ancestors,18t,19t remain untouched.

[2026-10-27T21:36:06Z · sase-1ou.2.1.2--3] PROPOSED FOLLOW-UP: Selection-health has 41 preexisting baseline exceedances — tools/selection_health --fail-on-new-flake exits 1 with exactly the same 41 node IDs using current and HEAD baselines. None of the three retired ToolRun nodes exceeds the baseline. Their fixed-at entries retire eight historical failures (82 total retired versus 74 on HEAD). Audited logs and comparisons are in file:explicit:c0f4bd59f97240f4bbc90b82 and the final report file:explicit:b0d1fd4be5d7f8c6c632927d. The land agent should triage these existing exceedances separately; the final guarded checks in both changed repositories pass.

[2026-10-27T21:36:25Z · sase-1ou.2.1.2--3] Verified default delegation and explicit deadline preservation, including the WAL probe budget regression. Final core and primary guarded checks pass; 272/272 affected-file tests pass; each of ten target nodes passes 10/10 serial, 20/20 loaded, and 3/3 controlled final repetitions. Earlier failures and clean-base witnesses are retained. Only three causally proven baseline entries retired; six remain active. No epic-symbol entries remain. Audited final evidence: file:explicit:b0d1fd4be5d7f8c6c632927d; raw final bundle: file:explicit:c0f4bd59f97240f4bbc90b82. Both repositories are ready for host commits, with core committed first and the primary revision pin following its actual SHA. Ancestors and task beads are untouched.

## Dependencies

- **Depends on:** [sase-1ou.2.1.1](sase-1ou.2.1.1.md) ✓ · ⧖ 2026-10-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ou.2.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ou.2.1.2.md) | [sase-1ou.2.1.2](sase-1ou.2.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@3f8baa7`](https://github.com/sase-org/sase-core/commit/3f8baa79844d9c856d211ad23149985afccccc70) | fix(tool-run): count the WAL probe against the busy budget | [sase-1ou.2.1.2](sase-1ou.2.1.2.md) | 2026-10-27 17:37:25 EDT |
