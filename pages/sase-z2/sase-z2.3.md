# Bead: sase-z2.3 — Detect and repair missing archived plans

[Bead Pages](../README.md) / [sase-z2](README.md) / sase-z2.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0i2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0i2.md) · **Assignee:** `sase-z2.3` · **Size:** medium
**Created:** 2026-09-09 18:25:00 EDT
**Plan:** [202609/durable\_plan\_archive\_publication.md](https://github.com/sase-org/sase--plans/blob/main/202609/durable_plan_archive_publication.md)

## Description

plan-archive-doctor: add a doctor-style check that cross-references plan beads, sidecar links/ indexes, and the canonical plans directory against the plans sidecar, reporting approved plans whose archived copy is missing, with a confirmed repair mode that re-archives recoverable plans (restoring bead_id frontmatter) and pushes.

## Dependencies

- **Blocks:** [sase-z2.4](sase-z2.4.md) ◐ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-z2.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-z2.3/README.md) | [sase-z2.3](sase-z2.3.md) | 0 |
