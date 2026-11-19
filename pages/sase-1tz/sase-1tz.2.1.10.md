# Bead: sase-1tz.2.1.10 — Find and fix the top cyclic-garbage producers and heap retainers

[Bead Pages](../README.md) / [sase-1tz.2.1](sase-1tz.2.1.md) / sase-1tz.2.1.10

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.md) · **Assignee:** `sase-1tz.2.1.10` · **Size:** medium
**Created:** 2026-11-19 11:13:28 EST
**Plan:** [202611/noise\_publication\_digests\_tui\_stalls.md](https://github.com/sase-org/sase--plans/blob/main/202611/noise_publication_digests_tui_stalls.md)

## Description

heap_retainers: census the object types freed by idle full collections (up to 7M objects each) and the types retained across them. Fix up to the top three measured producers or retainers, and record allocated blocks, RSS, and collected counts before and after.

## Dependencies

- **Blocks:** [sase-1tz.2.1.13](sase-1tz.2.1.13.md) ◐ · ⧖ 2026-11-19
- **Depends on:** [sase-1tz.2.1.9](sase-1tz.2.1.9.md) ✓ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.2.1.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.10/README.md) | [sase-1tz.2.1.10](sase-1tz.2.1.10.md) | 0 |
