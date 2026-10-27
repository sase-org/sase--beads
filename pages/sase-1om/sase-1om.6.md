# Bead: sase-1om.6 — Feed the TUI from the authoritative report

[Bead Pages](../README.md) / [sase-1om](README.md) / sase-1om.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5e.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5e.linker.w0.md) · **Assignee:** `sase-1om.6` · **Size:** medium
**Created:** 2026-10-26 20:19:45 EDT
**Plan:** [202610/machine\_capacity\_transparency.md](https://github.com/sase-org/sase--plans/blob/main/202610/machine_capacity_transparency.md)

## Description

tui-report-feed: compute the machine report off the event loop on token change plus a 10 s poll, drive the chip values and row queue context from it, keep the roster projection only as a pre-first-report estimate and drift witness, and log capacity_gauge/capacity_drift telemetry.

## Dependencies

- **Depends on:** [sase-1om.1](sase-1om.1.md) ◐ · ⧖ 2026-10-26
- **Depends on:** [sase-1om.3](sase-1om.3.md) ◐ · ⧖ 2026-10-26
- **Blocks:** [sase-1om.7](sase-1om.7.md) ◐ · ⧖ 2026-10-26
- **Blocks:** [sase-1om.8](sase-1om.8.md) ◐ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1om.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1om.6/README.md) | [sase-1om.6](sase-1om.6.md) | 0 |
