# Bead: sase-qw.2 — Registered errors and error-anchored launch logs

[Bead Pages](../README.md) / [sase-qw](README.md) / sase-qw.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07n](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07n.md) · **Assignee:** `sase-qw.2` · **Size:** medium
**Created:** 2026-08-19 09:29:49 EDT
**Plan:** [202608/last\_error\_log\_jump.md](https://github.com/sase-org/sase--plans/blob/main/202608/last_error_log_jump.md)

## Description

registry: stamp every launch-failure log entry with a stable error id, add the session-scoped registered-error pointer, make one helper both register the error and emit its toast so the chord hint can never appear without a target, and make `,L` select the registered error's log source.

## Dependencies

- **Depends on:** [sase-qw.1](sase-qw.1.md) ✓ · ⧖ 2026-08-19
- **Blocks:** [sase-qw.3](sase-qw.3.md) ◐ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qw.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qw.2/README.md) | [sase-qw.2](sase-qw.2.md) | 0 |
