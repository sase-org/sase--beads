# Bead: sase-ij.4 — Ratchet the window on the pending release branch in report-only mode

[Bead Pages](../README.md) / [sase-ij](README.md) / sase-ij.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wq](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wq/README.md) · **Assignee:** `sase-ij.4` · **Size:** medium
**Created:** 2026-08-09 15:19:11 EDT
**Plan:** [202608/core\_window\_ratchet.md](https://github.com/sase-org/sase--plans/blob/main/202608/core_window_ratchet.md)

## Description

release-ratchet: extend publish.yml's sync-lockfile job into a sync-release-metadata reconciler that runs the ratchet tool ahead of the lock refresh, landing it in report-only mode so a real release can be observed before it writes anything.

## Dependencies

- **Depends on:** [sase-ij.2](sase-ij.2.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-ij.5](sase-ij.5.md) ◐ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ij.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.4/README.md) | [sase-ij.4](sase-ij.4.md) | 0 |
