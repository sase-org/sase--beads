# Bead: sase-17p.6 — Prove the hand-off contract end to end and remove the beta flag

[Bead Pages](../README.md) / [sase-17p](README.md) / sase-17p.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qj](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qj.md) · **Assignee:** `sase-17p.6` · **Size:** medium
**Created:** 2026-09-24 08:40:25 EDT · **Closed:** 2026-09-24 15:27:35 EDT
**Plan:** [202609/tool\_e2\_durable\_handoff.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e2_durable_handoff.md)

## Description

acceptance-and-adoption: extend the ToolRun smoke harness with the hand-off fault matrix, update docs, the sase_monitor skill source, and the named memory, and remove the tool_handoff flag.

## Notes

[2026-09-24T19:13:23Z · sase-17p.6] Adoption baseline 2026-09-24: local ledger sase tool runs -a counts — total 640, owner_kind {none: 591, monitor: 49}, launch_mode {foreground: 640, handoff: 0}, state {failed: 491, succeeded: 110, signaled: 14, lost: 24, running: 1}. Zero handoff runs is expected pre-removal (flag was off); monitor-owned rows are E1.5 wraps, not reservations.

[2026-09-24T19:13:45Z · sase-17p.6] PROPOSED FOLLOW-UP: add a decisions strand for fail-closed sase tool run -H narrowing record-before-admit (explicit hand-offs only), and mark record-before-admit superseded-in-part

[2026-09-24T19:13:57Z · sase-17p.6] PROPOSED FOLLOW-UP: deploy regenerated sase_monitor skill (SKILL.md source changed here) via sase skill init --force from the landed tree after this epic lands

[2026-09-24T19:27:35Z · sase-17p.6] Verified: DoD-14 hermetic 7/7 pass, DoD-15 5/5 pass with --live (stop races exactly targeted, viewers detach 130 with run continuing, worker SIGKILL settles typed owner_lost with no replay, delivery exactly once proc-owned / zero monitor-owned, monitor hand-off id-first); tool_handoff flag removed and sase-17w closed; docs+skill source+memory updated with memory init re-run. just check red only on pre-existing master failures (mypy in 4 untouched files, symvision other-epic symbols, harness dod-1/dod-2 fail identically on clean HEAD).

## Dependencies

- **Depends on:** [sase-17p.5](sase-17p.5.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17p.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17p.6/README.md) | [sase-17p.6](sase-17p.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c91690e`](https://github.com/sase-org/sase/commit/c91690efcbae1179773f70a2823e77fabac4b203) | feat(tool): prove hand-off contract end to end and remove tool\_handoff flag (sase-17p.6) | [sase-17p.6](sase-17p.6.md) | 2026-09-24 15:29:12 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.2i.mus][1] | Research E3/E4: need remaining E2 exit criteria | 1 |
| read-by | [agent:sase-17p.6][2] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-17p.land][3] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2i.mus/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17p.6/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17p.land/README.md

<!-- sase:referenced-by:end -->
