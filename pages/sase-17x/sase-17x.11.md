# Bead: sase-17x.11 — Run policies, confirmation-aware blocks, and built-ins

[Bead Pages](../README.md) / [sase-17x](README.md) / sase-17x.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qs](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0qs.md) · **Assignee:** `sase-17x.11` · **Size:** medium
**Created:** 2026-09-24 11:29:31 EDT · **Closed:** 2026-09-24 16:21:28 EDT
**Plan:** [202609/command\_line\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_panel.md)

## Description

run-policies: run foreground-policy commands in the real terminal through `app.suspend()` and refuse deny-policy commands with an alternative. Add confirmation-aware declined blocks with an explicit `R` rerun-with-`-y`, plus the `cd`, `clear`, `help` and `history` built-ins.

## Notes

[2026-09-24T20:17:47Z · sase-17x.11] PROPOSED FOLLOW-UP: wire cd dir/+project completion into the completion popup (a complete_cd helper was dropped as dead code per symvision)

[2026-09-24T20:21:28Z · sase-17x.11] run-policies done: foreground suspend+run with ↗ blocks, deny ⊘ blocks (no history), declined+ R rerun-with--y flow, cd/clear/help/history › built-ins; 24 new tests green, neighbors green (83), ruff/fmt clean, no new mypy/symvision flags; PNG goldens need fix-tui-screenshots in a capable env

## Dependencies

- **Blocks:** [sase-17x.12](sase-17x.12.md) ✓ · ⧖ 2026-09-24
- **Depends on:** [sase-17x.8](sase-17x.8.md) ✓ · ⧖ 2026-09-24
- **Depends on:** [sase-17x.9](sase-17x.9.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.11/README.md) | [sase-17x.11](sase-17x.11.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ee9eda4`](https://github.com/sase-org/sase/commit/ee9eda4ab340bf9f6aaac08a773ca39dd912f93f) | feat(ace): command-line run policies, confirmation-aware blocks, and built-ins (sase-17x.11) | [sase-17x.11](sase-17x.11.md) | 2026-09-24 16:22:54 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17x.11][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.11/README.md

<!-- sase:referenced-by:end -->
