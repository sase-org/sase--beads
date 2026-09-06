# Bead: sase-xe.9 — Durable follow subscriptions with family continuity

[Bead Pages](../README.md) / [sase-xe](README.md) / sase-xe.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0gq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0gq.md) · **Assignee:** `sase-xe.9` · **Size:** medium
**Created:** 2026-09-06 14:06:45 EDT · **Closed:** 2026-09-06 17:57:46 EDT
**Plan:** [202609/remote\_dispatch\_fleet.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_fleet.md)

## Description

follow-store: persist viewer-local follow records keyed by origin and logical agent/family identity, promote singleton follows to the family identity when a family forms, make explicit unfollow tombstones win over automatic re-creation, and implement the shared Focus/Fleet running-count calculations over authoritative summaries with unknown-host propagation.

## Notes

[2026-09-06T21:57:09Z · sase-xe.9] PROPOSED FOLLOW-UP: Make rust-lsp-install honor CARGO_TARGET_DIR or fail on copy errors — isolated-target verification built a fresh LSP binary while the helper copied from the default target path and initially left a stale venv binary.

[2026-09-06T21:57:46Z · sase-xe.9] Implemented durable follow-store rules and Python persistence; verified cargo test -p sase_core fleet_contract::tests::, validate_sase_core_rs plus focused pytest, xprompt LSP parity reproduction, and CARGO_TARGET_DIR=/tmp/sase-core-target-sase_28 just check.

## Dependencies

- **Blocks:** [sase-xe.11](sase-xe.11.md) ◐ · ⧖ 2026-09-06
- **Depends on:** [sase-xe.2](sase-xe.2.md) ✓ · ⧖ 2026-09-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.9/README.md) | [sase-xe.9](sase-xe.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fdfb4e2`](https://github.com/sase-org/sase/commit/fdfb4e238a386b5470a67025da8db1c30bc92e90) | feat(fleet): add durable follow store | [sase-xe.9](sase-xe.9.md) | 2026-09-06 17:59:43 EDT |
