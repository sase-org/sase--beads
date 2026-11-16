# Bead: sase-1t2.6 — Transactional stop hardening and target-level dedup

[Bead Pages](../README.md) / [sase-1t2](README.md) / sase-1t2.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1ct](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ct.md) · **Assignee:** `sase-1t2.6` · **Size:** medium
**Created:** 2026-11-15 20:00:10 EST
**Plan:** [202611/agent\_hijack\_dependability.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack_dependability.md)

## Description

stop_txn: target-level dedup that returns the active operation, verified intent persistence before any signal, pin restore on pre-signal abort, stop_blocked custody plus bounded retry on partial stops, pidfd signalling on Linux, stale-sweep reconciliation of abandoned requested/stopping records, and session promotion so a sessionless stop can still Continue.

## Dependencies

- **Blocks:** [sase-1t2.12](sase-1t2.12.md) ◐ · ⧖ 2026-11-15
- **Depends on:** [sase-1t2.3](sase-1t2.3.md) ✓ · ⧖ 2026-11-15
- **Depends on:** [sase-1t2.4](sase-1t2.4.md) ◐ · ⧖ 2026-11-15
- **Blocks:** [sase-1t2.7](sase-1t2.7.md) ◐ · ⧖ 2026-11-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.6/README.md) | [sase-1t2.6](sase-1t2.6.md) | 0 |
