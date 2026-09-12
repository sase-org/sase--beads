# Bead: sase-zs.2 — Make remote clone timeouts retryable instead of fatal

[Bead Pages](../README.md) / [sase-zs](README.md) / sase-zs.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0k6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0k6.md) · **Assignee:** `sase-zs.2` · **Size:** small
**Created:** 2026-09-12 09:44:50 EDT · **Closed:** 2026-09-12 10:26:55 EDT
**Plan:** [202609/github\_network\_resilience.md](https://github.com/sase-org/sase--plans/blob/main/202609/github_network_resilience.md)

## Description

clone-retry: close the hole where `SddGitCommandTimeout` bypasses the clone retry loop whenever no reference repo is in play, and give retries an escalating, deadline-aware timeout budget.

## Notes

[2026-09-12T14:26:55Z · sase-zs.2] Implemented retryable remote clone timeouts with escalating deadline-aware attempt budgets; verified with just test tests/sdd_store/test_sidecar_clone_retry.py and just check (scoped lane escalated to full suite and passed); epic-symbols reported no entries.

## Dependencies

- **Blocks:** [sase-zs.4](sase-zs.4.md) ✓ · ⧖ 2026-09-12
- **Blocks:** [sase-zs.7](sase-zs.7.md) ✓ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zs.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zs.2/README.md) | [sase-zs.2](sase-zs.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4ea8a15`](https://github.com/sase-org/sase/commit/4ea8a1531b366d644522ddd7795d6cc8cb878ea1) | fix(sdd): retry remote clone timeouts | [sase-zs.2](sase-zs.2.md) | 2026-09-12 10:28:26 EDT |
