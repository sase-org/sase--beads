# Bead: sase-8v.6 — Linked SASE\_AGENT and automatic commit publication

[Bead Pages](../README.md) / [sase-8v](README.md) / sase-8v.6

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-8v.6` · **Size:** medium
**Created:** 2026-07-23 16:59:15 UTC
**Plan:** [202607/global\_agent\_hoods.md](https://github.com/sase-org/sase--plans/blob/main/202607/global_agent_hoods.md)

## Description

Stop producing SASE_MACHINE, render the full global SASE_AGENT as an agent/family link, and add an idempotent post-commit targeted publish with a durable retry outbox.

## Notes

COMMIT: 9564e01e8

## Dependencies

- **Blocks:** [sase-8v.10](sase-8v.10.md) ✓
- **Depends on:** [sase-8v.4](sase-8v.4.md) ✓
- **Blocks:** [sase-8v.8](sase-8v.8.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-8v.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-8v.6/README.md) | [sase-8v.6](sase-8v.6.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`9aab8a7`](https://github.com/sase-org/sase/commit/9aab8a713d27977956c68eb80b4affa9ac41a00b) | feat!: publish linked agent hoods after commits (sase-8v.6) | [sase-8v.6](sase-8v.6.md) | 2026-07-24 18:56:52 |
