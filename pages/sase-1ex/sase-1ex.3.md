# Bead: sase-1ex.3 — Serve \`\<space\>\` and the other MRU-head entry points from the snapshot

[Bead Pages](../README.md) / [sase-1ex](README.md) / sase-1ex.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vk](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vk.md) · **Assignee:** `sase-1ex.3` · **Size:** medium
**Created:** 2026-10-02 14:53:47 EDT
**Plan:** [202610/prompt\_space\_and\_project\_cycle\_latency.md](https://github.com/sase-org/sase--plans/blob/main/202610/prompt_space_and_project_cycle_latency.md)

## Description

space-prefill: resolve the `<space>` prefill from the snapshot without I/O. A cold or launch-pending snapshot opens a blank bar at once and applies a late prefill only to an untouched session. Move `,.` and the editor entry point to the snapshot, and remove every MRU write from key paths.

## Dependencies

- **Blocks:** [sase-1ex.10](sase-1ex.10.md) ◐ · ⧖ 2026-10-02
- **Blocks:** [sase-1ex.11](sase-1ex.11.md) ◐ · ⧖ 2026-10-02
- **Depends on:** [sase-1ex.2](sase-1ex.2.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ex.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ex.3/README.md) | [sase-1ex.3](sase-1ex.3.md) | 0 |
