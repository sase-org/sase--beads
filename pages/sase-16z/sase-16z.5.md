# Bead: sase-16z.5 — Plugin polling floors, CLI fingerprints, and limit events that only mark due

[Bead Pages](../README.md) / [sase-16z](README.md) / sase-16z.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0q3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0q3.md) · **Assignee:** `sase-16z.5` · **Size:** medium
**Created:** 2026-09-23 11:06:14 EDT
**Plan:** [202609/usage\_window\_collection\_service\_tree.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_window_collection_service_tree.md)

## Description

adaptive-admission: move the core pin, let plugins declare `min_probe_interval_seconds` (claude 300, muse 180, agy/grok/codex 120), compute CLI fingerprints, and pass floors, fingerprints, and `adaptive=True` through admission, attempts, and floor-aware reads. Limit events only mark providers due and no longer force explicit probes.

## Dependencies

- **Depends on:** [sase-16z.2](sase-16z.2.md) ◐ · ⧖ 2026-09-23
- **Depends on:** [sase-16z.4](sase-16z.4.md) ◐ · ⧖ 2026-09-23
- **Blocks:** [sase-16z.6](sase-16z.6.md) ◐ · ⧖ 2026-09-23
- **Blocks:** [sase-16z.8](sase-16z.8.md) ◐ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16z.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16z.5/README.md) | [sase-16z.5](sase-16z.5.md) | 0 |
