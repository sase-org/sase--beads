# Bead: sase-132.2 — Make the visible surface win the startup window

[Bead Pages](../README.md) / [sase-132](README.md) / sase-132.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0n7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0n7.md) · **Assignee:** `sase-132.2` · **Size:** large
**Created:** 2026-09-18 15:22:34 EDT
**Plan:** [202609/tui\_startup\_regression.md](https://github.com/sase-org/sase--plans/blob/main/202609/tui_startup_regression.md)

## Description

startup-sequence: stop launching every post-mount background load concurrently with the visible tab's first load; sequence or gate non-visible-surface work (relations index builds, prompt catalog warm, detail/prompt panel first renders, monitor reconcile, bead warmups, dismissed-index sync, proc-shell prune, update checks) behind visible-ready with a bounded fallback delay, and deduplicate work that runs twice in the window today.

## Dependencies

- **Depends on:** [sase-132.1](sase-132.1.md) ✓ · ⧖ 2026-09-18
- **Blocks:** [sase-132.7](sase-132.7.md) ◐ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-132.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-132.2.md) | [sase-132.2](sase-132.2.md) | 0 |
