# Bead: sase-169.4 — Lock waiting and worker-count translation

[Bead Pages](../README.md) / [sase-169](README.md) / sase-169.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1i](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.1i.md) · **Assignee:** `sase-169.4` · **Size:** small
**Created:** 2026-09-22 10:18:03 EDT
**Plan:** [202609/fix\_tui\_screenshots\_never\_fail.md](https://github.com/sase-org/sase--plans/blob/main/202609/fix_tui_screenshots_never_fail.md)

## Description

invocation: wait (bounded) for the checkout-local maintenance lock instead of refusing at once. Translate `-n/--numprocesses` selector arguments into the governed `SASE_PYTEST_WORKERS` request instead of letting pytest reject them.

## Dependencies

- **Depends on:** [sase-169.2](sase-169.2.md) ◐ · ⧖ 2026-09-22
- **Blocks:** [sase-169.5](sase-169.5.md) ◐ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-169.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-169.4/README.md) | [sase-169.4](sase-169.4.md) | 0 |
