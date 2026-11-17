# Bead: sase-1t2.11.1.6 — Exercise a real monitor hijack and recovery

[Bead Pages](../README.md) / [sase-1t2.11.1](sase-1t2.11.1.md) / sase-1t2.11.1.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t2.11](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t2.11.md) · **Assignee:** `sase-1t2.11.1.6` · **Size:** medium
**Created:** 2026-11-16 15:27:13 EST
**Plan:** [202611/monitor\_hijack\_adapter.md](https://github.com/sase-org/sase--plans/blob/main/202611/monitor_hijack_adapter.md)

## Description

canary: extend the real fakey launch/loader/TUI-operation canary with a running sleep monitor, same-workspace recovery and command rerun; flip the screenshot-shaped fixture and verify CLI/TUI parity.

## Notes

[2026-11-17T07:15:12Z · sase-1t2.11.1.6--1] PROPOSED FOLLOW-UP: test_session_hijack_chooses_running_member_one flakes in full-file runs (WorkspaceClaimError workspace #3 already claimed at child spawn) but passes solo; seen in 2 consecutive full-file runs of tests/fakey/test_agent_hijack_canary.py, passes in isolation; claim path untouched by this phase (ledger-only Rust change + monitor canary file).

## Dependencies

- **Depends on:** [sase-1t2.11.1.4](sase-1t2.11.1.4.md) ✓ · ⧖ 2026-11-16
- **Depends on:** [sase-1t2.11.1.5](sase-1t2.11.1.5.md) ✓ · ⧖ 2026-11-16
- **Blocks:** [sase-1t2.11.1.7](sase-1t2.11.1.7.md) ◐ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.11.1.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t2.11.1.6.md) | [sase-1t2.11.1.6](sase-1t2.11.1.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@35904eb`](https://github.com/sase-org/sase-core/commit/35904ebd0713ea1db7046be1386f9e05c434a52a) | fix(agent-hijack): allow held monitor rerun resolution in ledger | [sase-1t2.11.1.6](sase-1t2.11.1.6.md) | 2026-11-17 02:27:11 EST |
