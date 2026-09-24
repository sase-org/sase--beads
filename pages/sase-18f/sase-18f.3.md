# Bead: sase-18f.3 — Repair non-UI tests that fail on clean master

[Bead Pages](../README.md) / [sase-18f](README.md) / sase-18f.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0rh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0rh.md) · **Assignee:** `sase-18f.3` · **Size:** medium
**Created:** 2026-09-24 17:18:55 EDT
**Plan:** [202609/green\_just\_check.md](https://github.com/sase-org/sase--plans/blob/main/202609/green_just_check.md)

## Description

tests-core: fix the deterministic non-UI failures. These are the wait-check summary and scan-once tests (sase-186), the system-clock guard (sase-188 plus command-line block_render), the config-schema keymap, fakey help color, the agent-session rename fallout in kill-and-edit and launch approval, and the marker-mutation audit. Classify the load-sensitive tests by rerunning them.

## Dependencies

- **Depends on:** [sase-18f.1](sase-18f.1.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-18f.9](sase-18f.9.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18f.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.3/README.md) | [sase-18f.3](sase-18f.3.md) | 0 |
