# Bead: sase-xe.16.11.7.16.5.4 — Adopt the fixes and complete live acceptance

[Bead Pages](../README.md) / [sase-xe.16.11.7.16.5](sase-xe.16.11.7.16.5.md) / sase-xe.16.11.7.16.5.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-xe.16.11.7.16.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-xe.16.11.7.16.land.md) · **Assignee:** `sase-xe.16.11.7.16.5.4` · **Size:** medium
**Created:** 2026-09-15 08:35:21 EDT · **Closed:** 2026-09-15 15:40:33 EDT
**Plan:** [202609/fleet\_ghost\_rows\_remaining.md](https://github.com/sase-org/sase--plans/blob/main/202609/fleet_ghost_rows_remaining.md)

## Description

release-live-acceptance: release and adopt the Rust changes, redeploy both machines, capture clean live evidence, and complete the reopened acceptance beads.

## Notes

[2026-09-15T19:39:10Z · sase-xe.16.11.7.16.5.4] PROPOSED FOLLOW-UP: Investigate flaky sudo acceptance full-suite failure — just check full-suite lane failed once at tests/test_sudo_acceptance.py::test_sudo_local_flow_never_persists_canary_credentials; immediate isolated rerun passed.

[2026-09-15T19:40:33Z · sase-xe.16.11.7.16.5.4] Verified: fixed fleet TUI fallback so missing owner labels use logical agent id instead of exact attempt id; focused projection/display tests passed locally and Athena regression passed; live Athena TUI machine:apollo captures for by-machine and by-project views showed Apollo rows with no lane/attempt-0/y--plan and no local here chip on remote rows; raw fleet projection active/terminal-inclusive checks reported zero forbidden display labels. just check completed all lint/setup gates and governed full suite failed once on unrelated sudo acceptance flake; immediate isolated rerun passed.

## Dependencies

- **Depends on:** [sase-xe.16.11.7.16.5.1](sase-xe.16.11.7.16.5.1.md) ✓ · ⧖ 2026-09-15
- **Depends on:** [sase-xe.16.11.7.16.5.2](sase-xe.16.11.7.16.5.2.md) ✓ · ⧖ 2026-09-15
- **Depends on:** [sase-xe.16.11.7.16.5.3](sase-xe.16.11.7.16.5.3.md) ✓ · ⧖ 2026-09-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-xe.16.11.7.16.5.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-xe.16.11.7.16.5.4/README.md) | [sase-xe.16.11.7.16.5.4](sase-xe.16.11.7.16.5.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5ca8a60`](https://github.com/sase-org/sase/commit/5ca8a60d2d732e2c2087019b34e93025312ac181) | fix(tui): hide fleet exact attempt fallback | [sase-xe.16.11.7.16.5.4](sase-xe.16.11.7.16.5.4.md) | 2026-09-15 15:42:57 EDT |
