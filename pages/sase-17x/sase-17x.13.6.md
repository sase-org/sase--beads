# Bead: sase-17x.13.6 — Proc, project, marked, path and cd completion sources

[Bead Pages](../README.md) / [sase-17x.13](sase-17x.13.md) / sase-17x.13.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17x.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17x.land.md) · **Assignee:** `sase-17x.13.6` · **Size:** medium
**Created:** 2026-09-24 20:28:47 EDT · **Closed:** 2026-09-25 00:47:22 EDT
**Plan:** [202609/command\_line\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_landing_fixes.md)

## Description

entity-sources: feed proc and project slots from real app state with provider fallback. Read Agents-tab marks. Add off-thread path/dir and `cd` completion. Rank the selected agent's plan first.

## Notes

[2026-09-25T04:47:10Z · sase-17x.13.6--2] PROPOSED FOLLOW-UP: `sase tool run check` remains blocked on a clean-base mypy error in tools/smoke_sase_core_rs_tool_runs:75 (unannotated `fingerprint`); the phase touched no tools/ files, while mypy reports success for all 4967 source files.

[2026-09-25T04:47:22Z · sase-17x.13.6--2] Implemented proc/project/marked/path/cd completion sources and selected-agent-plan ranking. Focused command-line completion tests passed earlier in this phase; whole-repository `sase tool run check` now passes mypy over 4967 source files but is blocked only by the documented clean-base extensionless smoke-tool annotation failure. Verified `sase bead epic-symbols sase-17x.13.6`: no entries remain.

## Dependencies

- **Depends on:** [sase-17x.13.5](sase-17x.13.5.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17x.13.9](sase-17x.13.9.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.13.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17x.13.6.md) | [sase-17x.13.6](sase-17x.13.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fad9b5d`](https://github.com/sase-org/sase/commit/fad9b5d03db1b2812dcd10576d1eeefe4aec3de4) | feat(command-line): add dynamic completion sources | [sase-17x.13.6](sase-17x.13.6.md) | 2026-09-25 00:48:31 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17x.13.6--2][1] | Confirm assigned phase scope and its current closure evidence | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17x.13.6.md

<!-- sase:referenced-by:end -->
