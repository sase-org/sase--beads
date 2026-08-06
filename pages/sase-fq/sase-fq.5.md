# Bead: sase-fq.5 — Keep CI's prebuilt core wheel installed for every just recipe in a job

[Bead Pages](../README.md) / [sase-fq](README.md) / sase-fq.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tq](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tq/README.md) · **Assignee:** `sase-fq.5` · **Size:** medium
**Created:** 2026-08-05 21:06:00 EDT · **Closed:** 2026-08-05 21:37:38 EDT
**Plan:** [202608/ci\_master\_red\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202608/ci_master_red_recovery.md)

## Description

ci-wheel-pin: stop later just recipes from silently re-resolving sase-core-rs back to a published wheel, so source lanes really do test the sase-core commit that build-core built, and add CI-shape coverage that locks the behavior in.

## Notes

[2026-08-06T01:37:04Z · sase-fq.5] PROPOSED FOLLOW-UP: tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout is load-flaky — it failed once under the parallel `just test` lane (40s) and passed in 11s when re-run alone; unrelated to ci-wheel-pin.

[2026-08-06T01:37:38Z · sase-fq.5] setup-sase now exports SASE_CORE_WHEEL to $GITHUB_ENV so every later just recipe re-enters _setup with the wheel set and _core-overrides-arg emits the overrides file. Added 3 CI-shape tests in tests/test_github_actions_ci.py, incl. one that executes the action's install script against a stubbed just and asserts the GITHUB_ENV line; verified all 3 new tests fail without the action.yml change and pass with it (13 passed). just test: 25555 passed, 1 unrelated load-flake (bead lock contention) that passes standalone — noted as follow-up. just check lint fails only on the pre-existing progress_fingerprint symvision error owned by a sibling phase. Measured repeat local-wheel install at ~70ms, so no _setup skip logic needed. CI log confirmation must happen after this lands.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fq.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fq.5/README.md) | [sase-fq.5](sase-fq.5.md) | 0 |
