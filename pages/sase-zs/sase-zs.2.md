# Bead: sase-zs.2 — Make remote clone timeouts retryable instead of fatal

[Bead Pages](../README.md) / [sase-zs](README.md) / sase-zs.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0k6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0k6.md) · **Assignee:** `sase-zs.2` · **Size:** small
**Created:** 2026-09-12 09:44:50 EDT
**Plan:** [202609/github\_network\_resilience.md](https://github.com/sase-org/sase--plans/blob/main/202609/github_network_resilience.md)

## Description

clone-retry: close the hole where `SddGitCommandTimeout` bypasses the clone retry loop whenever no reference repo is in play, and give retries an escalating, deadline-aware timeout budget.

## Dependencies

- **Blocks:** [sase-zs.4](sase-zs.4.md) ◐ · ⧖ 2026-09-12
- **Blocks:** [sase-zs.7](sase-zs.7.md) ◐ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zs.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zs.2/README.md) | [sase-zs.2](sase-zs.2.md) | 0 |
