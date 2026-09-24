# Bead: sase-18f.1 — Restore every lint gate except toobig on master

[Bead Pages](../README.md) / [sase-18f](README.md) / sase-18f.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0rh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0rh.md) · **Assignee:** `sase-18f.1` · **Size:** medium
**Created:** 2026-09-24 17:18:51 EDT
**Plan:** [202609/green\_just\_check.md](https://github.com/sase-org/sase--plans/blob/main/202609/green_just_check.md)

## Description

lint-green: re-derive master's lint failures stage by stage, including symvision's masked categories. Fix the mypy errors in the agent-detail mixins, launch-prompt inputs, and command-line input/screen. Replace the fixed sleep in the command-line completion test. Resolve the ~41 unused public symbols using the symvision decision hierarchy.

## Dependencies

- **Blocks:** [sase-18f.2](sase-18f.2.md) ◐ · ⧖ 2026-09-24
- **Blocks:** [sase-18f.3](sase-18f.3.md) ◐ · ⧖ 2026-09-24
- **Blocks:** [sase-18f.4](sase-18f.4.md) ◐ · ⧖ 2026-09-24
- **Blocks:** [sase-18f.9](sase-18f.9.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18f.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.1/README.md) | [sase-18f.1](sase-18f.1.md) | 0 |
