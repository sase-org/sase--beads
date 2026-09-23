# Bead: sase-16z.3 — Probe and runner robustness fixes

[Bead Pages](../README.md) / [sase-16z](README.md) / sase-16z.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0q3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0q3.md) · **Assignee:** `sase-16z.3` · **Size:** medium
**Created:** 2026-09-23 11:06:12 EDT
**Plan:** [202609/usage\_window\_collection\_service\_tree.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_window_collection_service_tree.md)

## Description

probe-robustness: fix the runner's batch-deadline double-record, the probe TypeError re-run, the process-tree kill gap, the worker env allowlist, the 2 s agy/grok version timeouts, Muse's missed-mint blanking, and Codex's best-effort `account/read` poisoning the session. Each fix gets a regression test. This phase is pure Python and needs no core change.

## Dependencies

- **Blocks:** [sase-16z.4](sase-16z.4.md) ◐ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16z.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16z.3/README.md) | [sase-16z.3](sase-16z.3.md) | 0 |
