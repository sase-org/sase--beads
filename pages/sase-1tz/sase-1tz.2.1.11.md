# Bead: sase-1tz.2.1.11 — Move sampled synchronous filesystem work off the TUI main thread

[Bead Pages](../README.md) / [sase-1tz.2.1](sase-1tz.2.1.md) / sase-1tz.2.1.11

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.md) · **Assignee:** `sase-1tz.2.1.11` · **Size:** medium
**Created:** 2026-11-19 11:13:28 EST
**Plan:** [202611/noise\_publication\_digests\_tui\_stalls.md](https://github.com/sase-org/sase--plans/blob/main/202611/noise_publication_digests_tui_stalls.md)

## Description

ui_io_offload: move the launchable-MRU tick's stat and config-token peek, the hijack roster's per-row realpath, and project-record listing behind pump-free workers or freshness-token caches. This is the separate fix for apollo's low-GC blocking-I/O stalls.

## Dependencies

- **Blocks:** [sase-1tz.2.1.13](sase-1tz.2.1.13.md) ◐ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.2.1.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.11/README.md) | [sase-1tz.2.1.11](sase-1tz.2.1.11.md) | 0 |
