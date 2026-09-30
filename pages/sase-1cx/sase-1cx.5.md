# Bead: sase-1cx.5 — sase monitor start -J/--join and the joiner worker

[Bead Pages](../README.md) / [sase-1cx](README.md) / sase-1cx.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u3.md) · **Assignee:** `sase-1cx.5` · **Size:** large
**Created:** 2026-09-29 20:32:19 EDT
**Plan:** [202609/tool\_run\_escalation.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_run_escalation.md)

## Description

monitor-join: add `-J/--join RUN` to `sase monitor start`. It records the join atomically before the proc starts and releases it if the start fails. A hidden `sase tool _join` worker streams the run into the monitor log and mirrors its exit. Monitor stop and timeout, `sase tool stop`, and settlement all route through the join. `-f` is refused with `--join` in v1.

## Dependencies

- **Depends on:** [sase-1cx.3](sase-1cx.3.md) ✓ · ⧖ 2026-09-29
- **Depends on:** [sase-1cx.4](sase-1cx.4.md) ✓ · ⧖ 2026-09-29
- **Blocks:** [sase-1cx.7](sase-1cx.7.md) ◐ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cx.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1cx.5.md) | [sase-1cx.5](sase-1cx.5.md) | 0 |
