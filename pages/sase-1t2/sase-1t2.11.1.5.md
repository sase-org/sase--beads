# Bead: sase-1t2.11.1.5 — Present monitor recovery in the TUI

[Bead Pages](../README.md) / [sase-1t2.11.1](sase-1t2.11.1.md) / sase-1t2.11.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t2.11](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t2.11.md) · **Assignee:** `sase-1t2.11.1.5` · **Size:** medium
**Created:** 2026-11-16 15:27:13 EST · **Closed:** 2026-11-16 21:51:57 EST
**Plan:** [202611/monitor\_hijack\_adapter.md](https://github.com/sase-org/sase--plans/blob/main/202611/monitor_hijack_adapter.md)

## Description

surfaces: render Continue, Escalate, Re-run command, View, Shell, and Dismiss from the shared preview, hide unsupported monitor actions, preserve worker-based decision caching, and verify targeted visual snapshots.

## Notes

[2026-11-17T02:51:57Z · sase-1t2.11.1.5] Monitor recovery TUI done and verified: panel renders Continue/Escalate/Re-run/View/Shell/Dismiss from shared preview with backend reasons, Restart/Edit/Instruct hidden and refused; rerun routes via durable persist-recover; collapsed-session Enter opens occupant recovery; decision-cache/pump-free preview paths preserved; 28 focused tests pass (6 fail pre-fix); 2 new monitor goldens inspected and stable incl. TZ=UTC; joined just check run e1593b99e3aae797b82c5051c2cf8953 STATE=succeeded EXIT=0; epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1t2.11.1.3](sase-1t2.11.1.3.md) ✓ · ⧖ 2026-11-16
- **Blocks:** [sase-1t2.11.1.6](sase-1t2.11.1.6.md) ✓ · ⧖ 2026-11-16
- **Blocks:** [sase-1t2.11.1.7](sase-1t2.11.1.7.md) ◐ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.11.1.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t2.11.1.5.md) | [sase-1t2.11.1.5](sase-1t2.11.1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c52a24a`](https://github.com/sase-org/sase/commit/c52a24ade967836e4abac3ec93f7b0a40df07888) | feat(ace-tui): present monitor recovery in hijack panel | [sase-1t2.11.1.5](sase-1t2.11.1.5.md) | 2026-11-16 21:59:24 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1t2.11.1.5--1][1] | Verify bead status after monitored check completion | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t2.11.1.5.md

<!-- sase:referenced-by:end -->
