# Bead: sase-1no.4 — Agents detail callouts, toast, and query field

[Bead Pages](../README.md) / [sase-1no](README.md) / sase-1no.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.13e](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.13e.md) · **Assignee:** `sase-1no.4` · **Size:** small
**Created:** 2026-10-23 14:22:49 EDT · **Closed:** 2026-10-23 20:05:50 EDT
**Plan:** [202610/stranded\_epic\_work.md](https://github.com/sase-org/sase--plans/blob/main/202610/stranded_epic_work.md)

## Description

agents-detail: add the AGENT TURN header callout, the [beads] wait-lane and WAVES markers, a transition toast that never fires at startup, and the `stranded` live-query field, with docs and PNG goldens.

## Notes

[2026-10-23T23:46:42Z · sase-1no.4--2] PROPOSED FOLLOW-UP: Track the clean-base TUI import-budget overage with sase-1ic and the stranded_work_reduce package-floor release follow-up with sase-1no.3; the current package index cannot resolve 0.42.3.

[2026-10-24T00:05:50Z · sase-1no.4--2] Implemented the agents-detail stranded callouts, wait lanes, toast, and live query field with docs and tests; inspected both new PNGs. Targeted visual checks passed in UTC and America/New_York; just fmt passed. sase tool run check found no new failures (57,257 passed); one KNOWN clean-base import-budget overage remains tracked by sase-1ic, and the package-floor follow-up is tracked by sase-1no.3. Phase epic-symbols are empty.

## Dependencies

- **Depends on:** [sase-1no.3](sase-1no.3.md) ✓ · ⧖ 2026-10-23
- **Blocks:** [sase-1no.6](sase-1no.6.md) ✓ · ⧖ 2026-10-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1no.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1no.4.md) | [sase-1no.4](sase-1no.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a7996c3`](https://github.com/sase-org/sase/commit/a7996c3b77d155a9b3449d97b5e79b46b0ddd7f3) | feat(ace): show stranded work in agent details | [sase-1no.4](sase-1no.4.md) | 2026-10-23 20:06:53 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1no.4--2][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1no.4.md

<!-- sase:referenced-by:end -->
