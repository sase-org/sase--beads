# Bead: sase-17x.4 — Command-line proc tag and retention bucket

[Bead Pages](../README.md) / [sase-17x](README.md) / sase-17x.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qs](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qs.md) · **Assignee:** `sase-17x.4` · **Size:** small
**Created:** 2026-09-24 11:29:22 EDT
**Plan:** [202609/command\_line\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_panel.md)

## Description

proc-retention: in sase-core, give finished procs tagged `command-line` their own retention bucket of 50 so they never evict operational proc history. Export the tag and limit through the binding and move sase's sase-core revision pin.

## Dependencies

- **Blocks:** [sase-17x.5](sase-17x.5.md) ◐ · ⧖ 2026-09-24
- **Blocks:** [sase-17x.6](sase-17x.6.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.4/README.md) | [sase-17x.4](sase-17x.4.md) | 0 |
