# Bead: sase-1ex.5 — Pure catalog getters, non-blocking watcher growth, and a wakeable watcher stop

[Bead Pages](../README.md) / [sase-1ex](README.md) / sase-1ex.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vk](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vk.md) · **Assignee:** `sase-1ex.5` · **Size:** medium
**Created:** 2026-10-02 14:53:49 EDT
**Plan:** [202610/prompt\_space\_and\_project\_cycle\_latency.md](https://github.com/sase-org/sase--plans/blob/main/202610/prompt_space_and_project_cycle_latency.md)

## Description

watcher-growth: stop catalog getters from restarting the prompt-source watcher. Grow watches off the pump with `ensure_watches` and reconcile once afterward. Add a self-pipe so `ArtifactWatcher.stop()` never waits out the 0.5 s `select`.

## Dependencies

- **Depends on:** [sase-1ex.1](sase-1ex.1.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1ex.11](sase-1ex.11.md) ◐ · ⧖ 2026-10-02
- **Blocks:** [sase-1ex.8](sase-1ex.8.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ex.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ex.5/README.md) | [sase-1ex.5](sase-1ex.5.md) | 0 |
