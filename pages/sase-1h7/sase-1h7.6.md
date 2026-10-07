# Bead: sase-1h7.6 — Follow state in the agent model and shared view

[Bead Pages](../README.md) / [sase-1h7](README.md) / sase-1h7.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3v.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3v.linker.w0.md) · **Assignee:** `sase-1h7.6` · **Size:** medium
**Created:** 2026-10-06 18:17:41 EDT · **Closed:** 2026-10-07 17:01:58 EDT
**Plan:** [202610/wait\_for\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202610/wait_for_epic.md)

## Description

model: load `wait_for_epics_of` and `wait_epic_follows` into the TUI Agent model and render cache key. Make wait-satisfied and status-count logic follow-aware without I/O, and add one shared follow view model plus plain-text phrasing for every surface.

## Notes

[2026-10-07T21:01:30Z · sase-1h7.6] PROPOSED FOLLOW-UP: symvision _runs private-import errors in v2_snapshot_io.py and overview_card.py reproduce on clean base (KNOWN per tool-run triage) — needs owner

[2026-10-07T21:01:41Z · sase-1h7.6] PROPOSED FOLLOW-UP: SASE validation init repo --check wants sase/repos/beads/README.md refresh (+4/-4); reproduces without this phase diff, sidecar state drift

[2026-10-07T21:01:58Z · sase-1h7.6] Model phase done: Agent carries wait_for_epics_of/wait_epic_follows via wire+filesystem loaders (waiting.json wins); counts split FOLLOWING epics into a follows segment with authored beads preserved; satisfied parks on launching/blocked; render key covers follow state; shared view+phrasing in core. 19 new + 277 neighboring tests pass; ruff/mypy clean; symvision+validate failures reproduce on clean base (noted as follow-ups)

## Dependencies

- **Depends on:** [sase-1h7.5](sase-1h7.5.md) ✓ · ⧖ 2026-10-06
- **Blocks:** [sase-1h7.8](sase-1h7.8.md) ✓ · ⧖ 2026-10-06
- **Blocks:** [sase-1h7.9](sase-1h7.9.md) ✓ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h7.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h7.6/README.md) | [sase-1h7.6](sase-1h7.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6e2bc57`](https://github.com/sase-org/sase/commit/6e2bc577260805ecec2695b93697cd5bfe3f66ac) | feat(wait): add epic follow view for wait\_for\_epics\_of targets | [sase-1h7.6](sase-1h7.6.md) | 2026-10-07 17:04:08 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1h7.6][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h7.6/README.md

<!-- sase:referenced-by:end -->
