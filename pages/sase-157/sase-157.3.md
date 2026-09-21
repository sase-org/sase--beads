# Bead: sase-157.3 — Add an advisory macOS CI leg

[Bead Pages](../README.md) / [sase-157](README.md) / sase-157.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oj](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oj.md) · **Assignee:** `sase-157.3` · **Size:** small
**Created:** 2026-09-21 06:25:46 EDT · **Closed:** 2026-09-21 07:24:57 EDT
**Plan:** [202609/macos\_portability.md](https://github.com/sase-org/sase--plans/blob/main/202609/macos_portability.md)

## Description

macos-ci-advisory: turn rust-checks into an os matrix with a non-blocking macos-latest leg so every later phase gets real macOS signal without turning master red.

## Notes

[2026-09-21T11:24:57Z · sase-157.3] rust-checks is now an ubuntu/macos matrix with advisory macos leg (continue-on-error), per-OS rust-cache keys, pinned setup-python 3.12; verified: YAML parses, actionlint clean, ./scripts/check.sh all green on Linux

## Dependencies

- **Depends on:** [sase-157.2](sase-157.2.md) ✓ · ⧖ 2026-09-21
- **Blocks:** [sase-157.4](sase-157.4.md) ◐ · ⧖ 2026-09-21
- **Blocks:** [sase-157.6](sase-157.6.md) ✓ · ⧖ 2026-09-21
- **Blocks:** [sase-157.7](sase-157.7.md) ◐ · ⧖ 2026-09-21
- **Blocks:** [sase-157.8](sase-157.8.md) ◐ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-157.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-157.3/README.md) | [sase-157.3](sase-157.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@19274c0`](https://github.com/sase-org/sase-core/commit/19274c0e452411fc8714a9a4b2a72fd3f2f835a0) | ci: add advisory macOS leg to rust-checks matrix | [sase-157.3](sase-157.3.md) | 2026-09-21 07:37:23 EDT |
