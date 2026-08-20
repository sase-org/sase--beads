# Bead: sase-rn.1 — Rust finalizer protocol and resolution contract

[Bead Pages](../README.md) / [sase-rn](README.md) / sase-rn.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08y](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08y.md) · **Assignee:** `sase-rn.1` · **Size:** medium
**Created:** 2026-08-20 16:35:02 EDT · **Closed:** 2026-08-20 17:05:10 EDT
**Plan:** [202608/pluggable\_finalizers.md](https://github.com/sase-org/sase--plans/blob/main/202608/pluggable_finalizers.md)

## Description

core-protocol: add versioned provider, instance, selector, plan, context, submission, result, and diagnostic wires to sase-core; own stable selection/dependency ordering, canonical digests, envelope coverage checks, and aggregate outcomes there; expose focused PyO3 bindings and add `%final` to the shared editor directive contract; then publish the core release.

## Notes

[2026-08-20T21:05:10Z · sase-rn.1] Implemented finalizer protocol core wires, selection, digest, submission, and outcome modules, PyO3 bindings, and %final editor/LSP contract in sase-core; verified cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, cargo test --workspace, and no epic-symbol leftovers.

[2026-08-20T21:06:23Z · sase-rn.1] Verified cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, cargo test --workspace, and sase bead epic-symbols sase-rn.1 had no leftovers.

## Dependencies

- **Blocks:** [sase-rn.2](sase-rn.2.md) ◐ · ⧖ 2026-08-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rn.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rn.1/README.md) | [sase-rn.1](sase-rn.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@09576c3`](https://github.com/sase-org/sase-core/commit/09576c3acbfb8f3366f6c08dff6d4df2b1f3a134) | feat(finalizer): add shared finalizer protocol | [sase-rn.1](sase-rn.1.md) | 2026-08-20 17:07:38 EDT |
