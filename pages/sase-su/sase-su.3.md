# Bead: sase-su.3 — Automatic drain on a usage-limit disable

[Bead Pages](../README.md) / [sase-su](README.md) / sase-su.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ce](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ce.md) · **Assignee:** `sase-su.3` · **Size:** medium
**Created:** 2026-08-24 10:29:14 EDT
**Plan:** [202608/provider\_drain.md](https://github.com/sase-org/sase--plans/blob/main/202608/provider_drain.md)

## Description

auto: gate the feature behind a beta flag, submit a drain proc when a usage-limit disable wins its first-writer window, and make that drain own the single enriched usage-limit notification.

## Dependencies

- **Depends on:** [sase-su.2](sase-su.2.md) ✓ · ⧖ 2026-08-24
- **Blocks:** [sase-su.5](sase-su.5.md) ◐ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-su.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-su.3/README.md) | [sase-su.3](sase-su.3.md) | 0 |
