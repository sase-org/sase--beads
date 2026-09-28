# Bead: sase-1bu.2 — On-disk ledger, hot projection, doctor scan, and bindings

[Bead Pages](../README.md) / [sase-1bu](README.md) / sase-1bu.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tb.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tb.w0.md) · **Assignee:** `sase-1bu.2` · **Size:** medium
**Created:** 2026-09-27 19:03:19 EDT
**Plan:** [202609/goal\_ledger.md](https://github.com/sase-org/sase--plans/blob/main/202609/goal_ledger.md)

## Description

ledger-io: add ledger file I/O in sase-core: STORE.json fence, marker-superset write ordering, append, O(unsettled) hot read, stat-signature projection, history scan, doctor scan and repair, and an I/O probe. Expose them as PyO3 bindings with a thin Python facade and move the core pin.

## Dependencies

- **Depends on:** [sase-1bu.1](sase-1bu.1.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bu.3](sase-1bu.3.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bu.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bu.2/README.md) | [sase-1bu.2](sase-1bu.2.md) | 0 |
