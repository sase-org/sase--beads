# Bead: sase-16z.6 — Dedicated \`usage\` scheduler routine that probes inline

[Bead Pages](../README.md) / [sase-16z](README.md) / sase-16z.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0q3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0q3.md) · **Assignee:** `sase-16z.6` · **Size:** medium
**Created:** 2026-09-23 11:06:15 EDT
**Plan:** [202609/usage\_window\_collection\_service\_tree.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_window_collection_service_tree.md)

## Description

usage-routine: move `usage_refresh` out of `checks` into a new 60 s `usage` routine whose job runs the admitted batch in-process under non-proc operation IDs. Store-based waiting replaces proc waits for joiners (CLI and Models panel). The TUI fallback runs only when the scheduler does not own collection, `u` toasts render real receipt reasons, and the tests and docs are updated to match.

## Dependencies

- **Depends on:** [sase-16z.5](sase-16z.5.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-16z.7](sase-16z.7.md) ◐ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16z.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16z.6/README.md) | [sase-16z.6](sase-16z.6.md) | 0 |
