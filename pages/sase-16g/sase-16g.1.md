# Bead: sase-16g.1 — Core restart, request, and config-layer semantics

[Bead Pages](../README.md) / [sase-16g](README.md) / sase-16g.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pe](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pe.md) · **Assignee:** `sase-16g.1` · **Size:** medium
**Created:** 2026-09-22 12:59:06 EDT
**Plan:** [202609/services\_p0\_supervision.md](https://github.com/sase-org/sase--plans/blob/main/202609/services_p0_supervision.md)

## Description

core: make crash-loop stickiness survive capped backoff, add a per-proc restart request with a generation to the service state store, surface the pending request in the status snapshot, and make an errored or unknown-kind config layer fatal instead of invisible.

## Dependencies

- **Blocks:** [sase-16g.2](sase-16g.2.md) ◐ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16g.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16g.1/README.md) | [sase-16g.1](sase-16g.1.md) | 0 |
