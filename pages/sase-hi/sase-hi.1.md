# Bead: sase-hi.1 — Shared skill reference and directory contracts

[Bead Pages](../README.md) / [sase-hi](README.md) / sase-hi.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-hf.land.w2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hf.land.w2/README.md) · **Assignee:** `sase-hi.1` · **Size:** medium
**Created:** 2026-08-08 11:49:57 EDT · **Closed:** 2026-08-08 12:10:20 EDT
**Plan:** [202608/xprompt\_skill\_singular\_namespace.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_skill_singular_namespace.md)

## Description

core_skill_reference_contract: separate physical skill directories from singular xprompt references across the Rust catalog, bindings, editor, and gateway contracts.

## Notes

[2026-08-08T16:10:20Z · sase-hi.1] Implemented Rust core singular #skill/ contract while keeping physical skills/ source directories; verified cargo fmt --check, cargo clippy --workspace --all-targets --all-features -- -D warnings, and cargo test --workspace --all-features.

[2026-08-08T16:10:48Z · sase-hi.1] PROPOSED FOLLOW-UP: Fix invalid user file hook config — `research-highlights` is skipped because the user config layer contains unsupported field(s): filters.

[2026-08-08T16:12:22Z · sase-hi.1] verified cargo fmt --check, cargo clippy --workspace --all-targets --all-features -- -D warnings, and cargo test --workspace --all-features

## Dependencies

- **Blocks:** [sase-hi.2](sase-hi.2.md) ◐ · ⧖ 2026-08-08
- **Blocks:** [sase-hi.3](sase-hi.3.md) ◐ · ⧖ 2026-08-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-hi.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hi.1/README.md) | [sase-hi.1](sase-hi.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@8a0db59`](https://github.com/sase-org/sase-core/commit/8a0db5999a9f4dd3a64031cf31ca994151535fc8) | feat!: use singular skill xprompt references | [sase-hi.1](sase-hi.1.md) | 2026-08-08 12:26:12 EDT |
