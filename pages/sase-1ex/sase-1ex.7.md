# Bead: sase-1ex.7 — One highlight build and no pump-side Jinja inspect per cycle edit

[Bead Pages](../README.md) / [sase-1ex](README.md) / sase-1ex.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vk](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vk.md) · **Assignee:** `sase-1ex.7` · **Size:** medium
**Created:** 2026-10-02 14:53:52 EDT
**Plan:** [202610/prompt\_space\_and\_project\_cycle\_latency.md](https://github.com/sase-org/sase--plans/blob/main/202610/prompt_space_and_project_cycle_latency.md)

## Description

cycle-edit-coalesce: batch highlight-map builds so a cycle edit pays for one. Make the queued Changed/SelectionChanged context refreshes no-ops when nothing changed, skip the needless arg-hint refresh, and move the Jinja diagnostics inspect into a pump-free task.

## Dependencies

- **Blocks:** [sase-1ex.11](sase-1ex.11.md) ◐ · ⧖ 2026-10-02
- **Depends on:** [sase-1ex.2](sase-1ex.2.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1ex.6](sase-1ex.6.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ex.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ex.7/README.md) | [sase-1ex.7](sase-1ex.7.md) | 0 |
