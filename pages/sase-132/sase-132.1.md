# Bead: sase-132.1 — Controlled baselines and startup observability gaps

[Bead Pages](../README.md) / [sase-132](README.md) / sase-132.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0n7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0n7.md) · **Assignee:** `sase-132.1` · **Size:** medium
**Created:** 2026-09-18 15:22:33 EDT
**Plan:** [202609/tui\_startup\_regression.md](https://github.com/sase-org/sase--plans/blob/main/202609/tui_startup_regression.md)

## Description

baseline: capture controlled quiet-host and busy-host loader benches plus traced live startups at a recorded deployed SHA, and close the instrumentation gaps this diagnosis hit - sub-stage spans inside agents.load_from_disk, spans for the axe surface first load (none exist in live traces today), a pre-mount split of process_start_to_on_mount, and a startup-window marker on spans so startup contention is directly queryable.

## Dependencies

- **Blocks:** [sase-132.2](sase-132.2.md) ◐ · ⧖ 2026-09-18
- **Blocks:** [sase-132.3](sase-132.3.md) ◐ · ⧖ 2026-09-18
- **Blocks:** [sase-132.5](sase-132.5.md) ◐ · ⧖ 2026-09-18
- **Blocks:** [sase-132.6](sase-132.6.md) ◐ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-132.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-132.1/README.md) | [sase-132.1](sase-132.1.md) | 0 |
