# Bead: sase-1v7.1 — The roster\_loading axis and the generated on-demand pointer

[Bead Pages](../README.md) / [sase-1v7](README.md) / sase-1v7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1g7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1g7.md) · **Assignee:** `sase-1v7.1` · **Size:** medium
**Created:** 2026-11-25 15:44:40 EST · **Closed:** 2026-11-25 16:52:36 EST
**Plan:** [202611/on\_demand\_web\_rosters.md](https://github.com/sase-org/sase--plans/blob/main/202611/on_demand_web_rosters.md)

## Description

roster-axis: parse and validate `roster_loading: always | on_demand` and `roster_read_when:` on web descriptors, reserve the `roster` web slug, and render on-demand webs into AGENTS.md and instruction bundles with a generated pointer in place of the managed roster. The on-disk descriptor keeps its full roster. Also remove on-demand webs from the compaction ladder, update the Memory Webs intro and SASE Memory template text, add a Roster column to `sase memory web list`, and update the reference docs.

## Notes

[2026-11-25T21:52:36Z · sase-1v7.1] Roster-loading axis lands: parse/validate roster_loading always|on_demand and roster_read_when, reserve the roster web slug, project on-demand webs with a generated pointer while the on-disk descriptor keeps its full roster, skip on-demand webs on the compaction ladder, add the web-list Roster column, and update Memory Webs intro, SASE Memory template, and reference docs. No live web flipped on-demand. sase bead epic-symbols sase-1v7.1 was empty. sase tool run check 705cbafec3f7e3d9c822d59c660ac4a2 succeeded.

## Dependencies

- **Blocks:** [sase-1v7.2](sase-1v7.2.md) ✓ · ⧖ 2026-11-25
- **Blocks:** [sase-1v7.3](sase-1v7.3.md) ◐ · ⧖ 2026-11-25
- **Blocks:** [sase-1v7.4](sase-1v7.4.md) ✓ · ⧖ 2026-11-25
- **Blocks:** [sase-1v7.5](sase-1v7.5.md) ✓ · ⧖ 2026-11-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1v7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1v7.1/README.md) | [sase-1v7.1](sase-1v7.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e489558`](https://github.com/sase-org/sase/commit/e489558571a747220f7912156f1ebed7fb95e7b5) | feat(memory): add on-demand web roster loading axis | [sase-1v7.1](sase-1v7.1.md) | 2026-11-25 16:54:19 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1v7.1][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1v7.1/README.md

<!-- sase:referenced-by:end -->
