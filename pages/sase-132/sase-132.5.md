# Bead: sase-132.5 — Attribute and fix the doubled axe surface startup cost

[Bead Pages](../README.md) / [sase-132](README.md) / sase-132.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0n7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0n7.md) · **Assignee:** `sase-132.5` · **Size:** medium
**Created:** 2026-09-18 15:22:37 EDT
**Plan:** [202609/tui\_startup\_regression.md](https://github.com/sase-org/sase--plans/blob/main/202609/tui_startup_regression.md)

## Description

axe-ready: using the axe spans added in baseline, attribute why axe_ready_seconds doubled (2.0 s to 3.5 s median, step on 2026-08-27/28) and restore it to about 2 s, keeping the axe first load off the visible surface's critical path.

## Dependencies

- **Depends on:** [sase-132.1](sase-132.1.md) ✓ · ⧖ 2026-09-18
- **Blocks:** [sase-132.7](sase-132.7.md) ◐ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-132.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-132.5/README.md) | [sase-132.5](sase-132.5.md) | 0 |
