# Bead: sase-1v7.4 — sase's decisions web adopts the on-demand roster

[Bead Pages](../README.md) / [sase-1v7](README.md) / sase-1v7.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1g7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1g7.md) · **Assignee:** `sase-1v7.4` · **Size:** small
**Created:** 2026-11-25 15:44:41 EST · **Closed:** 2026-11-25 18:09:46 EST
**Plan:** [202611/on\_demand\_web\_rosters.md](https://github.com/sase-org/sase--plans/blob/main/202611/on_demand_web_rosters.md)

## Description

adopt-sase: flip `sase/memory/decisions.md` to on-demand with its read triggers. Add the `rosters-load-on-demand` record, mark `webs-render-in-their-own-section` superseded in part, and correct the memory-web glossary strand, each as its memory decision allows. Run `sase memory init` and `just fix`, verify the bundle shrank, and deploy the updated skills from the landed tree.

## Notes

[2026-11-25T23:09:46Z · sase-1v7.4] Implemented the on-demand decisions roster and read triggers, added decisions:rosters-load-on-demand, marked webs-render-in-their-own-section superseded in part, corrected glossary:memory-web, regenerated memory, and deployed landed skills. just fix passed; AGENTS.md shrank from 21,076 to 13,868 bytes. sase tool run check reached SASE validation but init memory --check is blocked until the new managed strand is committed by host finalization; no epic symbols remained.

## Dependencies

- **Depends on:** [sase-1v7.1](sase-1v7.1.md) ✓ · ⧖ 2026-11-25
- **Depends on:** [sase-1v7.2](sase-1v7.2.md) ✓ · ⧖ 2026-11-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1v7.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1v7.4/README.md) | [sase-1v7.4](sase-1v7.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`47cec6e`](https://github.com/sase-org/sase/commit/47cec6ea49154aee6d56ac766385e6c8f2b4238e) | feat(memory): load decisions roster on demand | [sase-1v7.4](sase-1v7.4.md) | 2026-11-25 18:11:44 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1v7.4][1] | Confirm the phase close and recorded verification note | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1v7.4/README.md

<!-- sase:referenced-by:end -->
