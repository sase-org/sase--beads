# Bead: sase-1t2.6 — Transactional stop hardening and target-level dedup

[Bead Pages](../README.md) / [sase-1t2](README.md) / sase-1t2.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1ct](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ct.md) · **Assignee:** `sase-1t2.6` · **Size:** medium
**Created:** 2026-11-15 20:00:10 EST · **Closed:** 2026-11-16 00:46:29 EST
**Plan:** [202611/agent\_hijack\_dependability.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack_dependability.md)

## Description

stop_txn: target-level dedup that returns the active operation, verified intent persistence before any signal, pin restore on pre-signal abort, stop_blocked custody plus bounded retry on partial stops, pidfd signalling on Linux, stale-sweep reconciliation of abandoned requested/stopping records, and session promotion so a sessionless stop can still Continue.

## Notes

[2026-11-16T05:45:56Z · sase-1t2.6--1] --list

[2026-11-16T05:46:29Z · sase-1t2.6--1] stop_txn verified: full just check passed all lint gates with 9789 passed and only the marker path-passing audit failing on the new _promote_sessionless_predecessor context (triage FLAKY, actually owned by this phase); added the reviewed PathPassingReview entry, reran 26 hijack+marker audit tests and 30 facts/ledger/custody/preparation tests green plus ruff/mypy clean. No epic-symbol entries remain. Glossary strand left untouched for the land phase.

## Dependencies

- **Blocks:** [sase-1t2.12](sase-1t2.12.md) ◐ · ⧖ 2026-11-15
- **Depends on:** [sase-1t2.3](sase-1t2.3.md) ✓ · ⧖ 2026-11-15
- **Depends on:** [sase-1t2.4](sase-1t2.4.md) ✓ · ⧖ 2026-11-15
- **Blocks:** [sase-1t2.7](sase-1t2.7.md) ◐ · ⧖ 2026-11-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t2.6.md) | [sase-1t2.6](sase-1t2.6.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`deddacb`](https://github.com/sase-org/sase/commit/deddacb1e510d0d40fa12e05da8629cc8c15373d) | feat(agent-hijack): transactional stop hardening and target-level dedup | [sase-1t2.6](sase-1t2.6.md) | 2026-11-16 00:28:30 EST |
| sase | [`dcae086`](https://github.com/sase-org/sase/commit/dcae0865684a74cf837c8189b5a481f6229b9ab5) | test(agent-hijack): review \_promote\_sessionless\_predecessor marker path passing | [sase-1t2.6](sase-1t2.6.md) | 2026-11-16 00:49:14 EST |
