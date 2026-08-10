# Bead: sase-il.7.1 — Complete the tale size contract in sase-core

[Bead Pages](../README.md) / [sase-il.7](sase-il.7.md) / sase-il.7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-il.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-il.land/README.md) · **Assignee:** `sase-il.7.1` · **Size:** medium
**Created:** 2026-08-10 10:54:41 EDT · **Closed:** 2026-08-10 12:07:56 EDT
**Plan:** [202608/finish\_tale\_size\_semantics.md](https://github.com/sase-org/sase--plans/blob/main/202608/finish_tale_size_semantics.md)

## Description

core-tale-size-contract: restrict tale `size` to xsmall/small/medium, add the launch-mode normalization the design specified, reduce the size/model field descriptions to pointers at the canonical size memory note, and cut a sase-core release.

## Notes

[2026-08-10T16:07:56Z · sase-il.7.1] Implemented core tale size contract in sase-core f2c28e7: authoring accepts only xsmall/small/medium, launch normalizes missing/large/xlarge tales to medium warnings, and schema descriptions point to sase/memory/sase_sizes.md. Added CI unblocker 86e4eb9 for Rust 1.97 clippy. Verified cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, and cargo test --workspace on final tree; release PR #104 CI checks passed, release v0.24.0 merged at 269928f, GitHub release exists, and PyPI exact/simple endpoints show sase-core-rs 0.24.0.

## Dependencies

- **Blocks:** [sase-il.7.2](sase-il.7.2.md) ◐ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-il.7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-il.7.1/README.md) | [sase-il.7.1](sase-il.7.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@f2c28e7`](https://github.com/sase-org/sase-core/commit/f2c28e7ce93b9671cf2fca5d006b9108d212419b) | feat(core)!: enforce tale size contract | [sase-il.7.1](sase-il.7.1.md) | 2026-08-10 11:06:11 EDT |
| sase-core | [`sase-core@86e4eb9`](https://github.com/sase-org/sase-core/commit/86e4eb9a053f0bc113dcce97aad38f9618d90c1a) | fix(core-py): allow plus-one binding signature | [sase-il.7.1](sase-il.7.1.md) | 2026-08-10 11:37:12 EDT |
