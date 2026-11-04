# Bead: sase-1r8.5 — Park protection-withheld requests instead of retrying them every pass

[Bead Pages](../README.md) / [sase-1r8](README.md) / sase-1r8.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.184](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.184.md) · **Assignee:** `sase-1r8.5` · **Size:** medium
**Created:** 2026-11-04 13:54:37 EST
**Plan:** [202611/agent\_publication\_errors.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_publication_errors.md)

## Description

parking: add parked fields to the outbox (schema 8), park withheld and prompt-protection rows at settlement, keep parked rows out of selection and the self-ring until the Rust recheck predicate says they are due, stop counting parks as job errors (except per park_notice), and surface parked counts in the heartbeat, chop summary, and doctor.

## Dependencies

- **Depends on:** [sase-1r8.2](sase-1r8.2.md) ✓ · ⧖ 2026-11-04
- **Depends on:** [sase-1r8.4](sase-1r8.4.md) ◐ · ⧖ 2026-11-04
- **Blocks:** [sase-1r8.6](sase-1r8.6.md) ◐ · ⧖ 2026-11-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1r8.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1r8.5/README.md) | [sase-1r8.5](sase-1r8.5.md) | 0 |
