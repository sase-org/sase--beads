# Bead: sase-16t.7 — The reveal toast, lens chip, and user docs

[Bead Pages](../README.md) / [sase-16t](README.md) / sase-16t.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pq.md) · **Assignee:** `sase-16t.7` · **Size:** small
**Created:** 2026-09-23 08:23:37 EDT · **Closed:** 2026-09-23 12:18:40 EDT
**Plan:** [202609/artifact\_link\_jumps.md](https://github.com/sase-org/sase--plans/blob/main/202609/artifact_link_jumps.md)

## Description

toast: add a pure, escaped toast formatter showing the new query, what hid the target, the scope change, and the real restore/back keys, plus unified failure copy, a context label on the lens chip, and rewritten reveal-ladder docs.

## Notes

[2026-09-23T16:17:35Z · sase-16t.7] PROPOSED FOLLOW-UP: just check symvision flags ExpandedLaunchSegments in src/sase/agent/launch_cwd_segments.py (committed 08:09, pre-existing, untouched by toast phase)

[2026-09-23T16:18:40Z · sase-16t.7] Toast formatter wired with 8s info toast (live keys, accent, escaped markup); unified 4-case failure copy; chip shows context label; Link Jumps docs rewritten; 11 new toast tests + 91 link-follow/shell/rail tests green; ruff/mypy clean; 2 chip PNG goldens regenerated and inspected; live toast verified via pilot notification dump and canonical-pipeline PNG render. just check red only on pre-existing foreign symvision flag ExpandedLaunchSegments (noted as follow-up).

## Dependencies

- **Depends on:** [sase-16t.4](sase-16t.4.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-16t.8](sase-16t.8.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16t.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16t.7/README.md) | [sase-16t.7](sase-16t.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e25372a`](https://github.com/sase-org/sase/commit/e25372a64a856b692329c9ad57f935a945f58ad2) | feat(ace): reveal toast, lens chip label, and Link Jumps docs | [sase-16t.7](sase-16t.7.md) | 2026-09-23 12:21:01 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16t.7][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16t.7/README.md

<!-- sase:referenced-by:end -->
