# Bead: sase-126.1 — Align the source pin and published core requirement

[Bead Pages](../README.md) / [sase-126](README.md) / sase-126.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0mh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0mh.md) · **Assignee:** `sase-126.1` · **Size:** small
**Created:** 2026-09-17 15:12:10 EDT · **Closed:** 2026-09-17 16:05:54 EDT
**Plan:** [202609/restore\_actions\_ci.md](https://github.com/sase-org/sase--plans/blob/main/202609/restore_actions_ci.md)

## Description

core-contract: advance the Rust source pin and package floor to the verified release containing every required binding and behavioral fix, and validate the affected contracts.

## Notes

[2026-09-17T20:05:54Z · sase-126.1--1] Updated the core source pin and published package floor to 0.34.47; verified ratchet, source-built core install/contracts/bindings, exact-minimum Python 3.12 floor smoke, affected 73-test module set, just fix, Symvision, and just check.

## Dependencies

- **Blocks:** [sase-126.2](sase-126.2.md) ◐ · ⧖ 2026-09-17
- **Blocks:** [sase-126.3](sase-126.3.md) ✓ · ⧖ 2026-09-17
- **Blocks:** [sase-126.4](sase-126.4.md) ◐ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-126.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-126.1.md) | [sase-126.1](sase-126.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`02fc83e`](https://github.com/sase-org/sase/commit/02fc83e11ad3268bc29b0910ed2caaf921e3bb7f) | chore(core): ratchet core dependency floor | [sase-126.1](sase-126.1.md) | 2026-09-17 16:07:25 EDT |
