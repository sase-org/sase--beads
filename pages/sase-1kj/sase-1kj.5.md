# Bead: sase-1kj.5 — Stop the Patch relation-index treadmill

[Bead Pages](../README.md) / [sase-1kj](README.md) / sase-1kj.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.102](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.102.md) · **Assignee:** `sase-1kj.5` · **Size:** medium
**Created:** 2026-10-13 11:47:19 EDT
**Plan:** [202610/apollo\_tui\_startup.md](https://github.com/sase-org/sase--plans/blob/main/202610/apollo_tui_startup.md)

## Description

patch-relation-index: memoize the Patch relation index, build its edges only when the Patches pane is visible (keeping a cheap targets-only index for link-follow), take the startup build off the event loop, and debounce visible reloads adaptively.

## Dependencies

- **Blocks:** [sase-1kj.6](sase-1kj.6.md) ◐ · ⧖ 2026-10-13
- **Blocks:** [sase-1kj.7](sase-1kj.7.md) ◐ · ⧖ 2026-10-13
- **Blocks:** [sase-1kj.8](sase-1kj.8.md) ◐ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kj.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kj.5/README.md) | [sase-1kj.5](sase-1kj.5.md) | 0 |
