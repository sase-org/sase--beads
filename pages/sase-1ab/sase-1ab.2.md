# Bead: sase-1ab.2 — Python persistence and wire cutover

[Bead Pages](../README.md) / [sase-1ab](README.md) / sase-1ab.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ss](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ss.md) · **Assignee:** `sase-1ab.2` · **Size:** large
**Created:** 2026-09-26 00:15:07 EDT
**Plan:** [202609/sase\_turn\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_turn_rename.md)

## Description

wire-cutover: bump the core pin and switch sase to the new binding names. Rename the Python wire mirrors and every durable key and value (agent meta, plan-gate meta and files, gate bundles, proc rows, runner-slot records, dismissed procs): new data is written only with turn/named-proc spellings, and readers accept both.

## Dependencies

- **Depends on:** [sase-1ab.1](sase-1ab.1.md) ✓ · ⧖ 2026-09-26
- **Blocks:** [sase-1ab.3](sase-1ab.3.md) ◐ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ab.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.2.md) | [sase-1ab.2](sase-1ab.2.md) | 0 |
