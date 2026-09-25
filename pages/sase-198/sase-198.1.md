# Bead: sase-198.1 — Rust queue contract accepts authored zero weight

[Bead Pages](../README.md) / [sase-198](README.md) / sase-198.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1n](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.1n.md) · **Assignee:** `sase-198.1` · **Size:** medium
**Created:** 2026-09-25 09:49:01 EDT · **Closed:** 2026-09-25 12:22:49 EDT
**Plan:** [202609/queue\_zero\_weight.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_zero_weight.md)

## Description

core-contract: in the linked sase-core repo, make the %queue parser accept an exactly zero weight literal, make the canonical formatter emit weight=0, update editor/LSP metadata, harden the legacy capacity=0 drain for zero-weight launches, and pin the existing zero-weight admission rules with tests.

## Dependencies

- **Blocks:** [sase-198.3](sase-198.3.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-198.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-198.1.md) | [sase-198.1](sase-198.1.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@c31b8cf`](https://github.com/sase-org/sase-core/commit/c31b8cf4bad8ea8c5b058a959bb69270ee2d5b30) | feat: Rust queue contract accepts authored zero weight (sase-198.1) | [sase-198.1](sase-198.1.md) | 2026-09-25 12:19:36 EDT |
