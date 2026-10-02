# Bead: sase-1ex.6 — Run each prompt text-area mount, unmount, and worker hook once

[Bead Pages](../README.md) / [sase-1ex](README.md) / sase-1ex.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vk](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vk.md) · **Assignee:** `sase-1ex.6` · **Size:** medium
**Created:** 2026-10-02 14:53:51 EDT
**Plan:** [202610/prompt\_space\_and\_project\_cycle\_latency.md](https://github.com/sase-org/sase--plans/blob/main/202610/prompt_space_and_project_cycle_latency.md)

## Description

mount-dedup: replace the mixins' super-chained, Textual-dispatched `on_mount`, `on_unmount`, and `on_worker_state_changed` handlers with cooperative hooks that are dispatched once. Body order and theme layering stay the same, and goldens stay unchanged.

## Dependencies

- **Depends on:** [sase-1ex.1](sase-1ex.1.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1ex.11](sase-1ex.11.md) ◐ · ⧖ 2026-10-02
- **Blocks:** [sase-1ex.7](sase-1ex.7.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ex.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ex.6/README.md) | [sase-1ex.6](sase-1ex.6.md) | 0 |
