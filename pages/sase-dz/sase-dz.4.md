# Bead: sase-dz.4 — Skip the prompt-archive check when its context is unavailable

[Bead Pages](../README.md) / [sase-dz](README.md) / sase-dz.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rm](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rm/README.md) · **Assignee:** `sase-dz.4` · **Size:** medium
**Created:** 2026-08-02 10:46:01 UTC · **Closed:** 2026-08-02 11:17:08 UTC
**Plan:** [202608/ci\_green\_restoration.md](https://github.com/sase-org/sase--plans/blob/main/202608/ci_green_restoration.md)

## Description

validate-skip: teach the prompt-archive validation an explicit unavailable-context outcome and have `sase validate` report it as skipped rather than failed, so a clean host without a project registry or agents-sidecar clone can still run the aggregate validation.

## Notes

[2026-08-02T11:16:41Z · sase-dz.4] PROPOSED FOLLOW-UP: Harden shared-load timeout tests against parallel-suite contention — test_concurrent_bead_mutations_wait_past_the_old_lock_timeout failed in both full runs with 11 and 20 workers (36-38s) but passed alone in 3.6s; the first run also timed out two completed fakey-retry visual threads that passed alone in 4-5s.

[2026-08-02T11:17:08Z · sase-dz.4] Verified unavailable project/no-project/missing-sidecar contexts return explicit exit 69 and sase validate renders them as a visible non-failing skip; resolvable invalid archives still fail. Focused handler suites: 15 passed. Final just check passed formatting, ruff, mypy, pyscripts, changelog, Symvision, toobig, SASE validation, and committed-plan validation; its parallel test stage had 25,362 passed and 7 skipped with one unrelated load-sensitive contention timeout that passes alone and is recorded as a proposed follow-up.

[2026-08-02T11:18:32Z · sase-dz.4] Verified explicit exit 69 for unavailable prompt-archive context, aggregate skip reporting, invalid-archive failure behavior, 15 focused tests, and all static/validation stages; full parallel suite reached 25,362 passed and 7 skipped with one documented load-sensitive timeout that passes alone.

## Dependencies

- **Blocks:** [sase-dz.6](sase-dz.6.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-dz.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-dz.4/README.md) | [sase-dz.4](sase-dz.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`404fac3`](https://github.com/sase-org/sase/commit/404fac3b5dfcd4bd069a6f94a1a1f37f1435cffc) | fix(validation): skip unavailable prompt archive context | [sase-dz.4](sase-dz.4.md) | 2026-08-02 11:19:38 |
