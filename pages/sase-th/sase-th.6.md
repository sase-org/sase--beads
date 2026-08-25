# Bead: sase-th.6 — Fix the two remaining CI-only test races

[Bead Pages](../README.md) / [sase-th](README.md) / sase-th.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0d8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0d8.md) · **Assignee:** `sase-th.6` · **Size:** medium
**Created:** 2026-08-25 07:32:03 EDT · **Closed:** 2026-08-25 07:53:07 EDT
**Plan:** [202608/repair\_red\_master\_ci.md](https://github.com/sase-org/sase--plans/blob/main/202608/repair_red_master_ci.md)

## Description

ci-races: diagnose and fix the provider-drain relaunch e2e and the plugins-pane lazy-fetch node, both of which pass serially and fail only under the CI lane.

## Notes

[2026-08-25T11:53:07Z · sase-th.6] Updated plugins lazy latest test to wait for the applied entry state; provider-drain e2e passes in the current tree. Verified the two target nodes serially and with SASE_PYTEST_WORKERS=4 pytest -n 4. just check reached unrelated symvision failures assigned to earlier epic phase; epic-symbols clean.

## Dependencies

- **Blocks:** [sase-th.7](sase-th.7.md) ◐ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-th.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-th.6/README.md) | [sase-th.6](sase-th.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`978fc7f`](https://github.com/sase-org/sase/commit/978fc7fd6a07a368a23f4ce6b7888d96ce94e912) | test(ace): deflake plugin latest wait | [sase-th.6](sase-th.6.md) | 2026-08-25 07:54:33 EDT |
