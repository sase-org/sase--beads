# Bead: sase-1nf.8 — Parked endpoints leave the retry loop and the sweep converges

[Bead Pages](../README.md) / [sase-1nf](README.md) / sase-1nf.8

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.12i](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.12i.md) · **Assignee:** `sase-1nf.8` · **Size:** medium
**Created:** 2026-10-20 13:36:15 EDT
**Plan:** [202610/athena\_apollo\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/athena_apollo_audit_fixes.md)

## Description

links-converge: move parked operations into a replayable parked ledger, make outbox appends idempotent, sweep per document, report projection failures and parked counts in the artifact_link_backfill job status, and expose parked counts in doctor.

## Dependencies

- **Depends on:** [sase-1nf.7](sase-1nf.7.md) ✓ · ⧖ 2026-10-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.8/README.md) | [sase-1nf.8](sase-1nf.8.md) | 0 |
