# Bead: sase-mc.1 — Add the Rust-owned temporary provider-disable state contract

[Bead Pages](../README.md) / [sase-mc](README.md) / sase-mc.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.02f](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.02f.md) · **Assignee:** `sase-mc.1` · **Size:** medium
**Created:** 2026-08-15 11:11:53 EDT · **Closed:** 2026-08-15 12:16:47 EDT
**Plan:** [202608/temporary\_provider\_disabling.md](https://github.com/sase-org/sase--plans/blob/main/202608/temporary_provider_disabling.md)

## Description

provider-disable-core: add a versioned, lock-bounded, atomic multi-provider disable store and PyO3 bindings in the linked sase-core repo, then add the strict Python facade and lock-free display peek in sase. Cover concurrent entries, replacement, exact expiry, until-cleared state, partial corruption cleanup, and binding parity.

## Notes

[2026-08-15T16:16:47Z · sase-mc.1] Implemented provider-disable Rust store/bindings plus Python facade and peek; verified linked core just check, just install, focused provider-disable pytest, and main just check scoped to 342 files.

[2026-08-15T16:18:17Z · sase-mc.1] Verified linked sase-core just check, main repo just install, focused provider-disable pytest, and main repo just check passed with scoped 342-file run.

## Dependencies

- **Blocks:** [sase-mc.2](sase-mc.2.md) ✓ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mc.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mc.1/README.md) | [sase-mc.1](sase-mc.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@9939f8f`](https://github.com/sase-org/sase-core/commit/9939f8f28ee3ab9a9c1a90f94f17fc58bd3d7c91) | feat(llm-provider): add provider-disable state store | [sase-mc.1](sase-mc.1.md) | 2026-08-15 12:19:57 EDT |
| sase | [`8902cb5`](https://github.com/sase-org/sase/commit/8902cb5e5eea51e8f795e7f6816a53142605f46c) | feat(llm-provider): add temporary provider-disable facade | [sase-mc.1](sase-mc.1.md) | 2026-08-15 12:22:29 EDT |
