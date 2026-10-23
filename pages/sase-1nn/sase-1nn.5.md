# Bead: sase-1nn.5 — Make the visual screenshot check clean on UTC runners

[Bead Pages](../README.md) / [sase-1nn](README.md) / sase-1nn.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.137](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.137.md) · **Assignee:** `sase-1nn.5` · **Size:** medium
**Created:** 2026-10-23 11:30:06 EDT · **Closed:** 2026-10-23 16:38:54 EDT
**Plan:** [202610/v0\_18\_1\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_release.md)

## Description

visual-lane: inventory golden drift with a full TZ=UTC screenshot check, fix nondeterminism, regenerate only intended goldens, and prove the check clean.

## Notes

[2026-10-23T20:38:54Z · sase-1nn.5--7] Verified visual-lane: five targeted TZ=UTC checks passed; full TZ=UTC visual check was clean with created=0, updated=0, stale=0 and no failed/skipped captures; just fix passed; sase tool run check passed with SASE_TUI_PERF and SASE_TUI_GC_CENSUS unset. Inspected the golden update reports and confirmed no epic-symbol entries remain; publish_dispatch=yes and gate_rerun=yes are intact.

## Dependencies

- **Depends on:** [sase-1nn.4](sase-1nn.4.md) ✓ · ⧖ 2026-10-23
- **Blocks:** [sase-1nn.7](sase-1nn.7.md) ✓ · ⧖ 2026-10-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nn.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.5.md) | [sase-1nn.5](sase-1nn.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`62c5934`](https://github.com/sase-org/sase/commit/62c5934eb6ba1c30f32805cc30d52ae084d4de5c) | test(tui): stabilize visual snapshot lane | [sase-1nn.5](sase-1nn.5.md) | 2026-10-23 16:40:38 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.2a.cld][1] | E3 readiness: sase-1nn status | 1 |
| read-by | [agent:sase-1nn.5--7][2] | Inspect the assigned visual-lane phase bead, required dispatch flags, and remaining phase-local work before closure | 2 |
| read-by | [agent:sase-1nn.6][3] | Need visual-lane notes before deciding whether screenshot CLI failures are owned there | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2a.cld/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.5.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nn.6/README.md

<!-- sase:referenced-by:end -->
