# Bead: sase-1oh.4.1.1 — Add atomic Rust recovery of closes owned by a failed run

[Bead Pages](../README.md) / [sase-1oh.4.1](sase-1oh.4.1.md) / sase-1oh.4.1.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1oh.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1oh.4.md) · **Assignee:** `sase-1oh.4.1.1` · **Size:** medium
**Created:** 2026-10-26 14:34:47 EDT
**Plan:** [202610/failed\_stitch\_bead\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202610/failed_stitch_bead_recovery.md)

## Description

recovery-core: add close provenance, durable completion-failure facts, and an idempotent Rust mutation that conditionally reopens this run's standing done closes with their ancestors and a STITCH FAILED note. Expose tested bindings; implement the failure-fact classification in the Rust stranded-work reducer.

## Dependencies

- **Blocks:** [sase-1oh.4.1.2](sase-1oh.4.1.2.md) ◐ · ⧖ 2026-10-26
- **Blocks:** [sase-1oh.4.1.3](sase-1oh.4.1.3.md) ◐ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1oh.4.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1oh.4.1.1/README.md) | [sase-1oh.4.1.1](sase-1oh.4.1.1.md) | 0 |
