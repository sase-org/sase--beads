# Bead: sase-rn.4 — Turn-bound sase final declaration channel and skill

[Bead Pages](../README.md) / [sase-rn](README.md) / sase-rn.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08y](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08y.md) · **Assignee:** `sase-rn.4` · **Size:** medium
**Created:** 2026-08-20 16:35:04 EDT · **Closed:** 2026-08-20 18:37:29 EDT
**Plan:** [202608/pluggable\_finalizers.md](https://github.com/sase-org/sase--plans/blob/main/202608/pluggable_finalizers.md)

## Description

declaration-channel: add `sase final context` and atomic `submit`, opaque host-issued repository obligations, nonce and digest validation, retained invalid-attempt diagnostics, the generated `/sase_final` source, and beta-only end-of-turn prompt instructions with demand-driven one-turn recovery and mechanical intentional-handoff exemption.

## Notes

[2026-08-20T22:34:35Z · sase-rn.4] PROPOSED FOLLOW-UP: Remove stale admin_center_config_hub feature flag definition — just check fails rule 7 because closed flag bead sase-rk still has a surviving definition.

[2026-08-20T22:37:29Z · sase-rn.4] Implemented final context/submit declaration channel, beta prompt nonce/recovery plumbing, and /sase_final source. Verified focused pytest, ruff, skill init --dry-run, git diff --check, and epic-symbols clean; just check passes fmt/keep-sorted/ruff/mypy but fails existing feature flag rule 7 for closed bead sase-rk/admin_center_config_hub, recorded as PROPOSED FOLLOW-UP.

[2026-08-20T22:38:59Z · sase-rn.4] Verified focused finalizer tests, touched-file ruff, skill dry-run, git diff --check, clean epic symbols; just check passed fmt/keep-sorted/ruff/mypy and failed only on unrelated closed-flag registry guard admin_center_config_hub.

## Dependencies

- **Depends on:** [sase-rn.3](sase-rn.3.md) ✓ · ⧖ 2026-08-20
- **Blocks:** [sase-rn.6](sase-rn.6.md) ◐ · ⧖ 2026-08-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rn.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rn.4/README.md) | [sase-rn.4](sase-rn.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f2b296c`](https://github.com/sase-org/sase/commit/f2b296c45cc8ec039249b9c525fca05cf437f390) | feat(finalizers): add final declaration channel | [sase-rn.4](sase-rn.4.md) | 2026-08-20 18:44:49 EDT |
