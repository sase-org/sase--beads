# Bead: sase-1mk.5 — Fix the usage-probe, git-maintenance and stderr-burst Full CI flakes

[Bead Pages](../README.md) / [sase-1mk](README.md) / sase-1mk.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.11b](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.11b.md) · **Assignee:** `sase-1mk.5` · **Size:** medium
**Created:** 2026-10-18 09:58:30 EDT · **Closed:** 2026-10-18 11:09:04 EDT
**Plan:** [202610/ship\_v0\_18\_0\_owned\_blockers.md](https://github.com/sase-org/sase--plans/blob/main/202610/ship_v0_18_0_owned_blockers.md)

## Description

runtime: root-cause sase-1k9, sase-1j4 and sase-1ht outside the TUI.

## Notes

[2026-10-18T15:08:22Z · sase-1mk.5] PROPOSED FOLLOW-UP: tests/tool/test_observe.py::test_executor_records_samples_and_show_lists_them still flakes under xdist load — saw 2 samples where >=3 were asserted in 1 of ~10 -n 8 runs on a tree whose changes do not touch it; already tracked by sase-19u, which is not in the v0.18.0 phase plan, so it is a candidate to fold into a later phase or the land agent triage.

[2026-10-18T15:08:27Z · sase-1mk.5] PROPOSED FOLLOW-UP: tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_agent_session_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap failed once in the escalated full just check ("agent land--1 did not finish", 92s, thread_alive=True) and passes solo in 67s; triaged FLAKY with no owning bead (ToolRun 140f8d705d35e76dfe342005729ca1a3). It is a load-sensitive 60-90s e2e, not a Full CI failure seen so far.

[2026-10-18T15:09:04Z · sase-1mk.5] Root-caused and fixed sase-1k9, sase-1j4 and sase-1ht in tests only; no production change. 1k9: probe test now runs in-process with a 1.0s mint wait and 60s deadline, so worker/fake-CLI start-up cannot consume the budget (reproduced by delaying worker start 1.4s; passes with a 1.4s fake-CLI start delay). 1j4: git commit forks 'git maintenance run --auto --detach' (verified via GIT_TRACE2_EVENT); tests/conftest.py session gitconfig now sets maintenance.auto=false and gc.auto=0, with a trace-based regression test in tests/sdd/test_git_identity_fixture.py that fails without the fix; observe has no copy path of its own. 1ht: the old test let the reader race the child's two writes (reproduced as 'assert 1200 < 1200' with a 0.3s gap); the test now starts the reader after the child confirms both pipes are written and asserts stderr is read within _JSONL_RECORD_BUDGET records, passing with the same 0.3s gap. Verification: sase tool run check escalated to the full suite (root conftest changed): 56425 passed, 1 failed (tests/fakey/test_monitor_capacity_e2e.py delayed_child_bootstrap, triaged FLAKY, passes solo in 67s, unrelated); touched files stable over 9 runs at -n 8. Two PROPOSED FOLLOW-UPs recorded (sase-19u sample-count flake; monitor capacity e2e). epic-symbols: none.

## Dependencies

- **Blocks:** [sase-1mk.8](sase-1mk.8.md) ◐ · ⧖ 2026-10-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1mk.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1mk.5/README.md) | [sase-1mk.5](sase-1mk.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f1c20a9`](https://github.com/sase-org/sase/commit/f1c20a9f6b729aebbf47246294fe4185b4392ea2) | fix(tests): remove timing races from the usage-probe, git-maintenance and stderr-burst flakes | [sase-1mk.5](sase-1mk.5.md) | 2026-10-18 11:10:24 EDT |
