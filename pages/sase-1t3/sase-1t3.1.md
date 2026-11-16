# Bead: sase-1t3.1 — Stop the hijack-decision storm

[Bead Pages](../README.md) / [sase-1t3](README.md) / sase-1t3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.62.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.62.linker.w0.md) · **Assignee:** `sase-1t3.1` · **Size:** medium
**Created:** 2026-11-16 07:57:54 EST · **Closed:** 2026-11-16 09:50:38 EST
**Plan:** [202611/tui\_storm\_trust\_heap\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202611/tui_storm_trust_heap_recovery.md)

## Description

storm-hotfix: gate passive footer scheduling with the cheap check. Key the decision cache on stable row identity plus a fingerprint instead of the roster generation. Run single-flight, latest-wins computes on one dedicated worker, and resolve sessions, clans, and running rows from the in-memory roster so the TUI never scans the archive.

## Notes

[2026-11-16T14:50:07Z · sase-1t3.1] Verified: storm test 50 footer refreshes with pid+generation bumps, slow fake 0.05s, max_in_flight=1 started<=2; asyncio.to_thread and default-executor patched to fail. Cache hit after generation bump; late result still refreshes footer; teardown raises RuntimeError on submit. just check passed (tool run 56f74bf41c2b8ec09c677ea75fd6598e). Live RSS/thread count on a running TUI was not measured in this unit-only phase; heartbeat ~4GB and one sase-hijack-decision thread belong to later soak/census phases.

[2026-11-16T14:50:38Z · sase-1t3.1] Storm-hotfix landed: fingerprint cache, dedicated sase-hijack-decision worker (max_workers=1, latest-wins), cheap-gated single schedule site, row-local StopDeps snapshot with no archive fallback. Storm test max_in_flight=1 started<=2; just check green (56f74bf41c2b8ec09c677ea75fd6598e). Live TUI RSS/thread census left to later soak/census phases.

## Dependencies

- **Blocks:** [sase-1t3.13](sase-1t3.13.md) ◐ · ⧖ 2026-11-16
- **Blocks:** [sase-1t3.14](sase-1t3.14.md) ◐ · ⧖ 2026-11-16
- **Blocks:** [sase-1t3.8](sase-1t3.8.md) ◐ · ⧖ 2026-11-16
- **Blocks:** [sase-1t3.9](sase-1t3.9.md) ◐ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.1/README.md) | [sase-1t3.1](sase-1t3.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`75ed2a1`](https://github.com/sase-org/sase/commit/75ed2a12395f17be73302b31081a40f85ee1b50b) | fix(tui): stop the hijack-decision compute storm | [sase-1t3.1](sase-1t3.1.md) | 2026-11-16 09:53:32 EST |
