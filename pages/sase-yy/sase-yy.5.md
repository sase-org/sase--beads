# Bead: sase-yy.5 — Readers, projections, and maintenance consume reduced events

[Bead Pages](../README.md) / [sase-yy](README.md) / sase-yy.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.09d.f1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.09d.f1.md) · **Assignee:** `sase-yy.5` · **Size:** large
**Created:** 2026-09-09 11:48:18 EDT · **Closed:** 2026-09-09 16:57:27 EDT
**Plan:** [202609/artifact\_link\_events\_v2.md](https://github.com/sase-org/sase--plans/blob/main/202609/artifact_link_events_v2.md)

## Description

event-readers: aggregate rebuilds, link list/doctor, managed Markdown blocks, and rename handling read reduced events overlaid with pending outbox operations, with alias events replacing event-path rewrites.

## Notes

[2026-09-09T20:57:27Z · sase-yy.5--1] Implemented artifact-link event-reader phase: store reads now reduce durable and pending event truth, health reports event/outbox/publication issues, rename repair queues alias events, managed Markdown link conflicts resolve semantically, and the sase-core-rs floor is ratcheted.

## Dependencies

- **Depends on:** [sase-yy.2](sase-yy.2.md) ✓ · ⧖ 2026-09-09
- **Depends on:** [sase-yy.3](sase-yy.3.md) ✓ · ⧖ 2026-09-09
- **Blocks:** [sase-yy.6](sase-yy.6.md) ✓ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-yy.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-yy.5.md) | [sase-yy.5](sase-yy.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ba73bc3`](https://github.com/sase-org/sase/commit/ba73bc30e4c0438e8861dfbe3e95a3754d121252) | feat(artifact-links): consume reduced event truth | [sase-yy.5](sase-yy.5.md) | 2026-09-10 09:59:41 EDT |
