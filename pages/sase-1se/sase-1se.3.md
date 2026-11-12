# Bead: sase-1se.3 — Healer relaunches launcher rows that died before naming

[Bead Pages](../README.md) / [sase-1se](README.md) / sase-1se.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1bq](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1bq.md) · **Assignee:** `sase-1se.3` · **Size:** medium
**Created:** 2026-11-12 06:15:58 EST
**Plan:** [202611/auto\_restart\_update\_skew\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/auto_restart_update_skew_fixes.md)

## Description

launcher-relaunch: the healer detects failed rows whose runner died before assigning a name (ace-run bootstrap deaths), and relaunches them by resubmitting the row's raw_prompt.md through the existing launch machinery instead of deferring forever on `plan_agent_restart` name lookup.

## Dependencies

- **Depends on:** [sase-1se.2](sase-1se.2.md) ◐ · ⧖ 2026-11-12
- **Blocks:** [sase-1se.4](sase-1se.4.md) ◐ · ⧖ 2026-11-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1se.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1se.3/README.md) | [sase-1se.3](sase-1se.3.md) | 0 |
