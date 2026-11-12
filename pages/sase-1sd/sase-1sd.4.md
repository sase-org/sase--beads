# Bead: sase-1sd.4 — Stop continuation capture from nesting fork ancestry past the 256 KiB cap (sase-1o1)

[Bead Pages](../README.md) / [sase-1sd](README.md) / sase-1sd.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1bp](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1bp.md) · **Assignee:** `sase-1sd.4` · **Size:** large
**Created:** 2026-11-12 05:26:16 EST
**Plan:** [202611/next\_seven\_salvage\_and\_unstrand.md](https://github.com/sase-org/sase--plans/blob/main/202611/next_seven_salvage_and_unstrand.md)

## Description

continuation-capture: persist_agent_delta records the #fork-expanded step prompt as authored_local_request and replay renders it as the parent user block, so every session member re-nests its whole ancestry; a live athena land session is at 708,391 bytes against the 262,144-byte validator cap, and an over-cap turn fails capture and settles the next monitor follow-up not-launchable. Capture only the local pre-fork request, make replay walk the parent chain, keep fork-replay output byte-stable, and add a repair or explicit error for in-flight over-cap sessions. Needs sase-core and sase changes.

## Dependencies

- **Depends on:** [sase-1sd.3](sase-1sd.3.md) ◐ · ⧖ 2026-11-12
- **Blocks:** [sase-1sd.5](sase-1sd.5.md) ◐ · ⧖ 2026-11-12
