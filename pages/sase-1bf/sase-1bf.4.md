# Bead: sase-1bf.4 — Truthful disk attribution under pressure

[Bead Pages](../README.md) / [sase-1bf](README.md) / sase-1bf.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.1d` · **Assignee:** `sase-1bf.4` · **Size:** medium
**Created:** 2026-09-27 14:23:37 EDT · **Closed:** 2026-09-27 19:20:09 EDT
**Plan:** [202609/bounded\_agent\_scratch.md](https://github.com/sase-org/sase--plans/blob/main/202609/bounded_agent_scratch.md)

## Description

disk-attribution: `sase disk list` and the disk_pressure job cover every registered root and every workspace checkout before the stray walk, report unattributed bytes, and workspace compaction stops over-reporting hardlinked bytes.

## Notes

[2026-09-27T23:13:50Z · sase-1bf.4--1] PROPOSED FOLLOW-UP: symvision flags private import _segment_section_identity in src/sase/ace/tui/widgets/prompt_panel/_section_navigation.py; reproduces identically on clean base tree (exit 1 both), outside disk-attribution scope

[2026-09-27T23:20:09Z · sase-1bf.4--1] Closed by explicit `sase stitch create -B close` after create_commit landed 5db68f77f ("feat(disk): truthful disk attribution under pressure (sase-1bf.4)"). The commit author requested bead completion after verifying the bead scope. Reopen with `sase bead open sase-1bf.4` if more work remains.

## Dependencies

- **Depends on:** [sase-1bf.1](sase-1bf.1.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bf.6](sase-1bf.6.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1bf.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1bf.4.md) | [sase-1bf.4](sase-1bf.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5db68f7`](https://github.com/sase-org/sase/commit/5db68f77f2e46d989934643dd8dad318cbc13fa2) | feat(disk): truthful disk attribution under pressure (sase-1bf.4) | [sase-1bf.4](sase-1bf.4.md) | 2026-09-27 19:16:02 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bf.4--1][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1bf.4.md

<!-- sase:referenced-by:end -->
