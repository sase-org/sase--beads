# Bead: sase-15p.2 — Hardened agy usage collector and provider hooks

[Bead Pages](../README.md) / [sase-15p](README.md) / sase-15p.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0os](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0os.md) · **Assignee:** `sase-15p.2` · **Size:** medium
**Created:** 2026-09-21 15:31:53 EDT
**Plan:** [202609/agy\_usage\_windows.md](https://github.com/sase-org/sase--plans/blob/main/202609/agy_usage_windows.md)

## Description

agy-collector: add collect_agy_usage (version floor, own process group, stderr auth-prompt kill, deadline margins, no auto-update, private log file), wire AgyProvider usage hooks, raise the sase-core-rs floor and ratchet the core revision, add a scripted fake-agy test fixture, and document the collector.

## Dependencies

- **Depends on:** [sase-15p.1](sase-15p.1.md) ✓ · ⧖ 2026-09-21
- **Blocks:** [sase-15p.3](sase-15p.3.md) ◐ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-15p.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-15p.2/README.md) | [sase-15p.2](sase-15p.2.md) | 0 |
