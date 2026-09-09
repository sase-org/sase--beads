# Bead: sase-z2.3 — Detect and repair missing archived plans

[Bead Pages](../README.md) / [sase-z2](README.md) / sase-z2.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0i2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0i2.md) · **Assignee:** `sase-z2.3` · **Size:** medium
**Created:** 2026-09-09 18:25:00 EDT · **Closed:** 2026-09-09 19:39:24 EDT
**Plan:** [202609/durable\_plan\_archive\_publication.md](https://github.com/sase-org/sase--plans/blob/main/202609/durable_plan_archive_publication.md)

## Description

plan-archive-doctor: add a doctor-style check that cross-references plan beads, sidecar links/ indexes, and the canonical plans directory against the plans sidecar, reporting approved plans whose archived copy is missing, with a confirmed repair mode that re-archives recoverable plans (restoring bead_id frontmatter) and pushes.

## Notes

[2026-09-09T23:39:24Z · sase-z2.3] Implemented plan-archive doctor detection and --fix-plan-archive repair; verified targeted plan-archive/doctor pytest tests, completion snapshot tests, just _lint-symvision, and just check.

## Dependencies

- **Blocks:** [sase-z2.4](sase-z2.4.md) ◐ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-z2.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-z2.3/README.md) | [sase-z2.3](sase-z2.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b8ac9f3`](https://github.com/sase-org/sase/commit/b8ac9f39290d48a3710277541c438a0cd154d107) | feat(beads): add plan archive doctor repair | [sase-z2.3](sase-z2.3.md) | 2026-09-09 19:40:47 EDT |
