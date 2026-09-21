# Bead: sase-157.5 — Fix the detached handoff started-path mismatch

[Bead Pages](../README.md) / [sase-157](README.md) / sase-157.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oj](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oj.md) · **Assignee:** `sase-157.5` · **Size:** medium
**Created:** 2026-09-21 06:25:48 EDT
**Plan:** [202609/macos\_portability.md](https://github.com/sase-org/sase--plans/blob/main/202609/macos_portability.md)

## Description

sudo-started-path: stop comparing a caller-supplied --started-path against one derived from a canonicalized --detach-dir, and correct the remaining sudo_runner cwd and sudo-order path expectations.

## Dependencies

- **Depends on:** [sase-157.4](sase-157.4.md) ✓ · ⧖ 2026-09-21
- **Blocks:** [sase-157.9](sase-157.9.md) ◐ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-157.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-157.5/README.md) | [sase-157.5](sase-157.5.md) | 0 |
