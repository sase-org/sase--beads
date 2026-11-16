# Bead: sase-1t3.1 — Stop the hijack-decision storm

[Bead Pages](../README.md) / [sase-1t3](README.md) / sase-1t3.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.62.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.62.linker.w0.md) · **Assignee:** `sase-1t3.1` · **Size:** medium
**Created:** 2026-11-16 07:57:54 EST
**Plan:** [202611/tui\_storm\_trust\_heap\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202611/tui_storm_trust_heap_recovery.md)

## Description

storm-hotfix: gate passive footer scheduling with the cheap check. Key the decision cache on stable row identity plus a fingerprint instead of the roster generation. Run single-flight, latest-wins computes on one dedicated worker, and resolve sessions, clans, and running rows from the in-memory roster so the TUI never scans the archive.

## Dependencies

- **Blocks:** [sase-1t3.13](sase-1t3.13.md) ◐ · ⧖ 2026-11-16
- **Blocks:** [sase-1t3.14](sase-1t3.14.md) ◐ · ⧖ 2026-11-16
- **Blocks:** [sase-1t3.8](sase-1t3.8.md) ◐ · ⧖ 2026-11-16
- **Blocks:** [sase-1t3.9](sase-1t3.9.md) ◐ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.1/README.md) | [sase-1t3.1](sase-1t3.1.md) | 0 |
