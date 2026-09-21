# Bead: sase-158.6.3 — Fix the update handlers, managed rows, and docs

[Bead Pages](../README.md) / [sase-158.6](sase-158.6.md) / sase-158.6.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-158.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-158.land.md) · **Assignee:** `sase-158.6.3` · **Size:** medium
**Created:** 2026-09-21 16:19:01 EDT
**Plan:** [202609/sase\_update\_live\_progress\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_update_live_progress_fixes.md)

## Description

handler-wiring-fixes: print stdout only after teardown in the live, mode-switch, and dry-run handlers. Stream managed uv output with normalized, parented package rows, declare trailing rows in execution order, and make interrupts single-shot. Pass argv to the log, dedupe RunUvFn, fix the docs, and add shared-terminal tests.

## Dependencies

- **Depends on:** [sase-158.6.2](sase-158.6.2.md) ◐ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-158.6.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-158.6.3/README.md) | [sase-158.6.3](sase-158.6.3.md) | 0 |
