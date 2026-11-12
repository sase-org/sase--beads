# Bead: sase-1sb.2.1.3 — Enforce trust for merged config and file hooks

[Bead Pages](../README.md) / [sase-1sb.2.1](sase-1sb.2.1.md) / sase-1sb.2.1.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1sb.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sb.2.md) · **Assignee:** `sase-1sb.2.1.3` · **Size:** medium
**Created:** 2026-11-11 20:34:38 EST
**Plan:** [202611/local\_config\_digest\_trust.md](https://github.com/sase-org/sase--plans/blob/main/202611/local_config_digest_trust.md)

## Description

hook-enforcement: Create the mandatory local_config_command_trust sunset
flag using sase flag new, then filter local executable contributions before
merging and before the independent file-hook loader consumes raw layers.
Wire fresh trust checks into before/after commit hooks, explicit-project
rebase gates and file-hook execution. Keep raw inspection and feature-flag
bootstrap separate from runtime filtering. Preserve user/overlay commands,
non-command local values and the explicit flag-Off compatibility branch.
Add both-state and stale-cache/end-to-end no-execution regressions.

## Dependencies

- **Depends on:** [sase-1sb.2.1.2](sase-1sb.2.1.2.md) ✓ · ⧖ 2026-11-11
- **Blocks:** [sase-1sb.2.1.4](sase-1sb.2.1.4.md) ◐ · ⧖ 2026-11-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sb.2.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sb.2.1.3/README.md) | [sase-1sb.2.1.3](sase-1sb.2.1.3.md) | 0 |
