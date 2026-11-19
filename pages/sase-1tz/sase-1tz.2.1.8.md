# Bead: sase-1tz.2.1.8 — Rotate tui\_stalls.jsonl, tolerate torn lines, and write fault headers only on faults

[Bead Pages](../README.md) / [sase-1tz.2.1](sase-1tz.2.1.md) / sase-1tz.2.1.8

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.md) · **Assignee:** `sase-1tz.2.1.8` · **Size:** medium
**Created:** 2026-11-19 11:13:27 EST
**Plan:** [202611/noise\_publication\_digests\_tui\_stalls.md](https://github.com/sase-org/sase--plans/blob/main/202611/noise_publication_digests_tui_stalls.md)

## Description

stall_telemetry: tui_stalls.jsonl size-rotates through the shared bounded-append helper and drops its non-atomic in-place prune. Every reader tolerates torn lines, and long stalls get bounded stack re-samples. tui_faults.log gets a header only when a fault actually happens.

## Dependencies

- **Blocks:** [sase-1tz.2.1.13](sase-1tz.2.1.13.md) ◐ · ⧖ 2026-11-19
- **Blocks:** [sase-1tz.2.1.9](sase-1tz.2.1.9.md) ◐ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.2.1.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.8/README.md) | [sase-1tz.2.1.8](sase-1tz.2.1.8.md) | 0 |
