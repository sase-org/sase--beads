# Bead: sase-1sb.2.1.2 — Persist trust and add human acknowledgment commands

[Bead Pages](../README.md) / [sase-1sb.2.1](sase-1sb.2.1.md) / sase-1sb.2.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1sb.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sb.2.md) · **Assignee:** `sase-1sb.2.1.2` · **Size:** medium
**Created:** 2026-11-11 20:34:38 EST · **Closed:** 2026-11-12 01:27:32 EST
**Plan:** [202611/local\_config\_digest\_trust.md](https://github.com/sase-org/sase--plans/blob/main/202611/local_config_digest_trust.md)

## Description

trust-approval: Implement the Rust-owned machine-local trust store and the
thin Python project-identity and filesystem adapters. Add sase config trust
allow/status/revoke with the human-only acknowledgment contract in this plan.
Trust must bind the reviewed digest to a host-resolved project identity;
reject stale approvals and all agent/monitor acknowledgment attempts. Add
atomicity, identity, failure and CLI tests. Document the trust commands and
store. This phase does not yet change runtime command loading.

## Notes

[2026-11-12T06:27:32Z · sase-1sb.2.1.2] Implemented the machine-local Rust trust store and PyO3 bindings, checkout/config identity and digest adapters, human-only trust allow/status/revoke CLI, completion metadata/snapshot, and docs. Verified Rust store/binding tests, 23 trust tests, 16 completion tests, core check, main check, and no remaining epic-symbol entries; the core-floor probe reports the new capabilities blocked_unpublished pending host-owned landing.

## Dependencies

- **Depends on:** [sase-1sb.2.1.1](sase-1sb.2.1.1.md) ✓ · ⧖ 2026-11-11
- **Blocks:** [sase-1sb.2.1.3](sase-1sb.2.1.3.md) ◐ · ⧖ 2026-11-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sb.2.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sb.2.1.2/README.md) | [sase-1sb.2.1.2](sase-1sb.2.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@233cb41`](https://github.com/sase-org/sase-core/commit/233cb41d6bb7186a711e75999394570e9ad9943e) | feat(config): persist digest-pinned local command trust | [sase-1sb.2.1.2](sase-1sb.2.1.2.md) | 2026-11-12 01:29:04 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1sb.2.1.1--1][1] | Check consumer phase for epic-symbol re-key | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sb.2.1.1.md

<!-- sase:referenced-by:end -->
