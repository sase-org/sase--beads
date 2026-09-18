# Bead: sase-132.6 — Trim on\_mount to first paint back under 0.3 s

[Bead Pages](../README.md) / [sase-132](README.md) / sase-132.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0n7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0n7.md) · **Assignee:** `sase-132.6` · **Size:** small
**Created:** 2026-09-18 15:22:38 EDT
**Plan:** [202609/tui\_startup\_regression.md](https://github.com/sase-org/sase--plans/blob/main/202609/tui_startup_regression.md)

## Description

first-paint: profile the compose/on_mount/first-refresh path (on_mount_to_first_paint_seconds doubled from 0.21 s to 0.44 s median) and remove or defer the growth so first paint lands in about 0.25 s again.

## Dependencies

- **Depends on:** [sase-132.1](sase-132.1.md) ✓ · ⧖ 2026-09-18
- **Blocks:** [sase-132.7](sase-132.7.md) ◐ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-132.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-132.6/README.md) | [sase-132.6](sase-132.6.md) | 0 |
